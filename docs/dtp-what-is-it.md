<br/>

## Data Transfer Project - What is it

A few years ago, several companies wanted to move the state of the art forward for data portability.  Wanting to move further together than they could separately, they started collaborating on an Open Source project that allowed them to make use of each other's contributions.  That project became the [https://github.com/google/data-transfer-project](Data Transfer Project) (DTP) and is now supported by a non-profit, the Data Transfer Initiative (DTI).

Today, a data exporter can run DTP on a server inside their service, and provide a higher quality and scalability of data portability of user content to other data platforms.  The Open Source (OS) project has common data models and a library of adapters to connect data objects to the services APIs that are providing or receiving those data objects.


### How does it affect me as a user?

If you're a person with content on Google, Meta or Apple, you may be able to port that content to other platforms. The ability to move data directly from one service to another is often housed alongside the features that allow data export, because data export is often used to achieve data portability when users download content that they then upload to a different platform.  These services listed below offer both exporting and direct service-to-service porting, depending on content-type - and because that availability may change over time as developer are constantly at work, we'll just list the umbrella data access/export/porting services here. 

* [Google Takeout](https://takeout.google.com/).
* [Apple Privacy](https://privacy.apple.com)
* [Meta's View Your Information](https://auth.meta.com/settings/vyi/)

If you do port your content from one service to another service, you may be using DTP without knowing it.  The goal of the DTP contributor community is to make data porting work better (more complete transfer, fewer steps, faster results) and that's often invisible.

### Who contributes?  Can I contribute?

The folks who run DTP and contribute adapters or core code to DTP are primarily services with large amounts of user-contributed content or data.  Users of these services come to the place where their content or data is stored and processed to ask for that data to be provided in a specific format or to a specific destination, whether that be for purposes of backup or experimentation or moving to a different service.

As a result, it's engineers at these services who have built the majority of DTP's functionality.  Because DTP is open source, they can benefit from each other's work.  A new adapter that can send data to a new destination can be used by all the exporters for whom sending to that destination makes sense. 

Open Source contributors are often "scratching their own itch" famously, and solving their own needs while supporting the Open Source project.  DTP solves the needs of data exporters (and data destinations) involved in mass data portability.  Thus, if you're not working on data portability at a data exporting platform, it may be hard to contribute to DTP!  Still, if you believe you have an angle, please elaborate on it (via [https://github.com/google/data-transfer-project/issues](github issues), most likely); the contributors are all friendly.

### What is the future for DTP?

DTP already provides great value where it's running and in use, but work continues.  Some of the work currently or recently in-progress includes:
* The ability to port music playlists from one service to another
* Transfers that get interrupted (e.g. reached quota limitations) can be restarted
* Handling of skippable errors - when an error occurs with one data object in the middle of a transfer, it need not prevent subsequent data objects from being transferred successfully

The maintainers and supporters of DTP also look forward to adding new adapters, adding more data sources and destinations to the ecosystem, as more companies make data portability a priority and a commitment.