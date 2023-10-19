<br/>

## Data Transfer Project - Intro for Potential Contributors

If you believe your service or a service you contribute to could usefully run a DTP server, or participate as an exporter or importer in the DTP ecosystem, this document should help get you started. In particular, while this whole document explains how the pieces work together, some sections are key to some types of engineers involved in a DTP project:
 * Ops or release engineers -- [System components and interfaces](#system)
 * Frontend engineers -- [How to drive DTP from frontend ](#frontend)
 * Backend engineers -- [Extensions](#extensions)

### Data verticals

DTP currently supports a number of explicit data verticals: types of content that have different properties than other types of content.  Furthermore, DTP participants may support some data verticals but not all.  For example, a video hosting service may not have a way to intake static images and photos or a good place to put them, but still support importing videos.  As another example, a social media site might import and export social media posts, and it might also have a way to export photos -- but the social media site may not be able to import galleries of standalone images.

Current data verticals include:
 * Calendar
 * Contacts
 * Mail
 * Music
 * Photos
 * Social media posts
 * Tasks
 * Videos

If you choose to participate in DTP, you may choose to support one of these verticals to begin with, and expand to support others if and as appropriate.  DTP maintainers might be interested in discussing additional verticals but are focused on consumer use cases, not enterprise.

### Roles

In DTP, the data exporter service is the active role.  The data exporter service, usually at the request of a user, initiates authentication and authorization with the destination or importer service and then, if successful, begins sending data objects to the destination service.

Data exporter services run DTP as a server inside their environment.  For example, on a photo sharing service, a user with 1000 photos on the service is most likely to go to that service to find out what they can do with those photos and how to export them from the photo service.  When the service runs DTP, the service has options to export photos to any participant in DTP that supports importing (taking on the destination role) and also supports the photo data type.

<img title="DTP Architecture" alt="A boxes-and-arrows diagram of the exporter and importer roles and how they interact with their system components, including the DTP server with code contributed by both roles." src="/assets/DTP architecture.png"/>

Data importing services contribute code to DTP that knows how to call their intake APIs.  They also run an authentication service and may need UX to authorize and direct data transfers to their ultimate destination.

Most services operate in both roles, triggering DTP themselves when users setup a data transfer operation, but also having their importing API endpoints called by DTP code hosted by other exporters.

Some data destinations are only importers, and these are usually providing a backup service rather than a hosting service similar to the exporter.  One benefit to being an exporter in DTP is found in plugging into a set of backup services that people would like to transfer their data to in the form of data archives.

### <a name="security"></a>Security

DTP was designed with privacy and security in mind.  Some of the components relating to security are worth discussing just in a brief overview.

* OAuth is the default service used to authenticate and authorize the user on the remote system.  The destination service probably has different user accounts than the exporting service, and may need to enforce quotas or other access control.  Thus, the user probably authenticates once to the exporting service (or has a session), and again to an entirely different account on the destination service, where they also explicitly authorize the transfer.

* Keys are used to authorize any data transfer connection at all between two services, regardless of user authentication and authorization.  The exporter will need an API key for each destination service, saved in the Key Store accessible to DTP (see the [system description](#system) below).  A DTP participant may store and enable as few or as many keys as they find appropriate.

* Content storage security is not altered or affected by DTP.

* Transport security breaks down into a few different network communications.  Communication between DTP and the exporter's data APIs should be over HTTPs and properly authorized; furthermore this probably runs within the exporter's overall service.  Communication between DTP and any content destination MUST be encrypted -- this can be done in the destination's implementation of the Importer interface by simply calling HTTPS-secured APIs. More generally: any network connections involved in running DTP, even if they are within a service's boundaries, can and should be secured connections.

Beyond system security, it's always a good idea to set user expectations appropriately around what is being done with their data.  A good front-end exporter implementation, before triggering a data transfer job, will set expectations with the user about how much data is being transfered and where to.

### <a name="extensions"></a>Extensions

An *extension* in DTP is how a participant contributes code that knows how to authenticate or transfer data to or from their particular service.  The main extension involved in porting data is a [Transfer Extension](https://github.com/google/data-transfer-project/tree/master/extensions/data-transfer), implementing the [TransferExtension](https://github.com/google/data-transfer-project/blob/master/portability-spi-transfer/src/main/java/org/datatransferproject/spi/transfer/extension/TransferExtension.java) interface, including an Exporter, an Importer, or both.  Those Exporters and Importers can register to handle different data verticals and make any combination of API requests needed to initiate or react to a data transfer.

When a new participant contributes an extension to DTP that supports the Importer functionality, that code can potentially be called as soon as other participants deploy the new version with the new Importer.

Exporter functonality, on the other hand, starts to function when the DTP participant has deployed a DTP on a server connected into their own service, complete with the system components listed in the next section.


### <a name="system"></a>System components and interfaces

Besides DTP and the service providers extension within DTP, a few other system components must exist in the service environment.  These components, required to make DTP fully operational and make it available to users, are very much in the control of the service provider, and few assumptions have been made about whether they're hosted, standalone, or what software provides the service, so long as it can be used by the DTP extension for the purpose needed.  A provider operating DTP as an exporter will need:

* A content storage backend with an API for accessing content that's going to be ported - you may already have this.  This API will be called by the java code you write in your DTP extension objects implementing the TransferExtension,  Exporter and Importer interfaces.
* A key store, for storing the API keys of other systems (see [Security](#security) ).  This secure storage service will be called by the java code you write in your DTP extension objects implementing the [AppCredentialStore](https://github.com/google/data-transfer-project/blob/master/portability-spi-cloud/src/main/java/org/datatransferproject/spi/cloud/storage/AppCredentialStore.java) interface.
* A job store, to store information about data transfer jobs in progress.  This storage service will be called by the java code you write in your DTP extension objects implementing the [JobStore interface](https://github.com/google/data-transfer-project/blob/master/portability-spi-cloud/src/main/java/org/datatransferproject/spi/cloud/storage/JobStore.java).
* A frontend that can call DTP to create and check on transfer jobs.  The frontend interacts with DTP by calling a set of endpoints already built into DTP.

A provider acting as an importer, via their extension code in DTP, will need to have running in their service:
* An API for importing content objects - you may already have this.
* An OAuth endpoint (or similar) to authenticate the user and grant access to the import API on their behalf.

The DTP server itself runs a Jetty Servlet, and the project comes with Kubernetes and Docker configuration to reduce deployment overhead.

### <a name="frontend"></a>How to drive DTP from the frontend 

This section may be needed by frontend developers who are building access to DTP into Web pages, or other developers triggering DTP jobs from components such as automated scripts.

Note that DTP has a demo Web site that illustrates how to trigger DTP jobs, but [this Web site](https://github.com/google/data-transfer-project/tree/master/distributions/demo-server) is not run by anybody in production - it is used for testing, development and to illustrate use of DTP.

The endpoints are defined using a [Jersey TransportBinder](https://github.com/google/data-transfer-project/blob/master/extensions/transport/portability-transport-jettyrest/src/main/java/org/datatransferproject/transport/jettyrest/rest/JerseyTransportBinder.java), including endpoints to
* create transfer job
* reserve worker
* get reserved worker
* start transfer job
* get transfer job \[status\]


### Other things you need to know

**Access Keys in Development** -- DTP participants know that developers need API keys to test code in-progress, and many already have ways to get such API keys (e.g. Google has service accounts).  If the API key does not have sufficient privileges to do real tests (quota or other limits) the DTP maintainer community has folks that can help fix this.  Once a DTP participant is getting ready to deploy, some "real" API keys will be needed.

**DTP maintainer community** -- Ask DTI about joining the DTP maintainer chat channels.  Once an implementation is seriously underway, DTP participants may meet regularly to solve problems and keep changes coordinated, until the new extension or any refactoring required begins to settle down and the project moves into deployment phases.  Note that DTP maintainers sign a Contributor License Agreement - this is what allows each contributor to legally run all the code in DTP without license concerns.

**DTI's role** -- The Data Transfer Initiative is an independent non-profit working with and supported by corporate partners.  While DTI facilitates and supports work on DTP, especially for new folks getting started, partnership in DTI is not a requirement to participate in or run DTP or have access to DTP communities.



<br/>
