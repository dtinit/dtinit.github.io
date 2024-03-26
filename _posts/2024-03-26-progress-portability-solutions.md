---
title: Progress towards real world portability solutions
tags: tools
author: Chris Riley
excerpt: "We are celebrating a milestone on our work to build a DTP-powered music playlist transfer tool - code from both Apple and Google is now in the DTP repo."
thumbnail: /images/blog/turntable.jpg
---

The phrase “data portability” can make the average non-techie, non-policy listener’s eyes glaze over. Even if the values involved are universal, the mechanics of moving data are technical, and few people want the details. But when I’m in a cab from an airport traveling for work or talking to one of my in-laws about what I do, I can always get their attention with a good example. And most often, I tell them about music playlists.

Playlists are an investment. We put time into making them, but more than that, we put emotion into them. And we’ve been making playlists for different services for decades. We live in a time of healthy competition among music services. Yet I’ve talked to a number of people who feel locked in to a single music service or even unable to try a different service because of their playlists. This is a solvable problem.

There are some third party solutions for it, in some cases. I will point interested readers to our new [Portability Map tool](https://portmap.dtinit.org/), where we endeavor to be comprehensive, and provide information and links to some of these tools - and we’re always eager to add more, so let us know if there’s anything we’re missing! But users need more than what the market today is offering.

Central to the origin story for DTI is the [open source Data Transfer Project](https://github.com/google/data-transfer-project) - a code base that reflects the collaborations of companies towards a family of direct data portability tools. Some of the entries in the Portability Map are for DTP-powered tools, including in particular several photo transfer tools, built and tested and available to billions of internet users today.

One of the newest DTP-powered efforts is coming close to fruition, after months of investment by two of our industry partners. Portability engineers working at Google and Apple have been working together to develop, test, and ship a music playlist transfer tool between Apple Music and YouTube Music. And we’ve reached a major milestone in that both companies are now sharing their work in the open source DTP repository.

Navigating large code bases isn’t for the faint of heart, so let me give a few shortcuts. The DTP model connects service endpoints through individual extensions to and from a shared data model. The codebase has a [shared folder for these extensions](https://github.com/google/data-transfer-project/tree/master/extensions/data-transfer). A few clicks into that file tree will lead to Apple’s recently posted [music importer code](https://github.com/google/data-transfer-project/tree/master/extensions/data-transfer/portability-data-transfer-apple/src/main/java/org/datatransferproject/datatransfer/apple/music) and Google’s [importer and exporter tools](https://github.com/google/data-transfer-project/tree/master/extensions/data-transfer/portability-data-transfer-google/src/main/java/org/datatransferproject/datatransfer/google/music). This new DTP-powered music playlist transfer tool has been under development for months. At DTI, we’re extremely pleased by, and thankful for, the extensive collaboration and contributions.

The DTP model is powerful. It produces shared code for smooth and effective server to server transfer. In the context of playlists, that means accurate matches between tracks (i.e. not just matching the artist name and song name, but striving for the same song version) and generally high reliability and trust in the transaction. It also means storing and representing the shared data model for music playlists in a public repository, which helps lower burdens on new services that want to be recipients of, or senders of, music playlist data.

But, the portability world has grown in recent years. The Digital Markets Act, recently enforceable in the European Union, has contributed to this. In the post-DMA data portability era, designated gatekeepers have developed and continue to make available interfaces that allow companies to approach them directly and establish bespoke transfer mechanisms, not reliant on a shared data model or open source code base.

These third-party interfaces add substantial value to the ecosystem. There is no silver bullet for data portability, now or in the future. The post-DMA world will have more of all of these approaches: shared principles, shared standards, shared transfer tools, and bespoke mechanisms.

DTP as a technology continues to have its unique utility, and because of that DTI as an organization will continue to invest in it, alongside our partners. It will continue to power many transfers between DTI partners, and will continue to provide easy entry points for the verticals in DTP, particularly photos and, soon, playlists. The future of DTP remains as a core tool in the transfer toolkit, and for its use cases, it will be best-of-class for user experience. But developing, testing, and deploying new tools, while ensuring a high level of fidelity of data, in complex systems that involve multiple parties, takes time, and that’s unlikely to change, particularly as portability offerings grow and diversify.

DTI as an organization is built to serve a mission: “Empower people by building a vibrant ecosystem for simple and secure data transfers.” That means doing more than just investing in DTP. That’s why we built the Portability Map, why we’ll continue our work on [trust models](https://dtinit.org/trust), why we contribute to standards with the W3C, and why we’re supporting the fediverse ecosystem, among other activities.

Today we’re celebrating a step forward for DTP as we work alongside our partners at Apple and Google to deliver new world-class tools to help people. We do so in the context of our, and their, other efforts, many of which will get more airtime in the weeks and months to come. But I believe the most durable progress will come from the most user-friendly solutions, and for that reason in particular, we are excited for this progress.

And, we’re always open to collaborating with more music streaming services, so please reach out if you’re interested!
