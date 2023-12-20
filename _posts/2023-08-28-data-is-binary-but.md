---
title:  Data is binary, but that doesn’t make portability simple.
tags: challenges
author: Chris Riley
excerpt: Data sometimes feels like the simplest thing in the world. It’s just a bunch of 1’s and 0’s, right? Often we treat all data the same. For portability, however, we cannot
thumbnail: /images/blog/Fractal Complexity Render.jpg
---

Data sometimes feels like the simplest thing in the world. It’s just a bunch of 1’s and 0’s, right?
Often we treat all data the same, whether we’re looking at the storage capacity of a new smartphone 
(do we really need 512GB?) or when Dropbox tells us we’re out of storage space yet again.

The metaphors we use double down on homogeneity too. How many times have you heard “Data is the new oil”? Or “money”? Fortunately such blunt comparisons have been widely debunked. But ideas are sticky. Like … oil.


## Portability is complex because data is complex.


My first article in this content series was about the [complex problem space of data portability](https://www.linkedin.com/pulse/complex-problem-space-data-portability-chris-riley/). One big thing missing from that narrative was the inherent complexity of data itself. When you want to actually *do things* with data, suddenly everything gets complicated, and the differences matter.


Those of us who have been using computers for decades have so many of these stories. Remember re-formatting disks to work in Windows or Mac, but never both? Remember opening a document written in Word Perfect in Word? (If anyone reading this remembers [“little-endian” and “big-endian”](https://en.wikipedia.org/wiki/Endianness#:~:text=Endianness%20is%20primarily%20expressed%20as,byte%20at%20the%20smallest%20address.) – join the club.)


Fortunately, the digital world has evolved, and a lot of these friction points have been smoothed over. Still, though, even services that do roughly the same things – think cloud-based photo archiving – don’t store or process the same kinds of data in the same ways. You can’t just grab a blob of data from one service and put it in another and assume it will work; a translation or adaptation will be needed. And that’s code that someone, somewhere, needs to write and host and pay for the compute cycles to run.


Now look at the problem space of data portability. (Forgive me, as this was in my last email, but I have to share [this Instagram Reel again](https://www.instagram.com/reel/Cv5XbLxAsQ_/?igshid=MzRlODBiNWFlZA%3D%3D).) To transfer a user’s data from one service to another, you have to find it, translate it, and make sure the recipient of the data can use it.


## Yes – I said “find it.”


I was thinking about this just in the context of DTI, a very new organization, and the systems we’ve set up to manage our own processes. (We don’t really have personal data other than employee data, so it’s a bit of an apples and oranges comparison, but bear with me.)


I keep my personal todo list in Asana; we’re using Miro to develop metrics and other visual exercises; we had tried out Trello briefly but now are using AirTable for project status and some management functions; we have a Google workspace account for email and documents; and we communicate over Slack. Oh, and employee data is separate; it’s with our payroll provider. We’re far from alone in having business data scattered across many servers.


Of course, the General Data Protection Regulation was adopted in 2016, and businesses who hold users’ personal data have had years to implement its portability and other data access obligations. It’s not that finding a user’s personal data can’t be done; just that it isn’t always as simple as going into a database and saying “give me all the records on user 24601.” In fact, there are companies like [DataGrail](https://www.datagrail.io/platform/) that include, as part of their business pitch, a function to “Detect personal data, no matter where it lives.”


## Once you find it, you need to figure out what to do with it.


Translating data formats is perhaps the raison d’etre of DTI as an organization, and the Data Transfer Project as a technology: we offer a coordination process to produce, and an open repository in which to store, software adapters that can bridge the semantic and syntactic gaps between import and export APIs of different services.


We implement portability not in raw blobs, but intentionally, with understanding and knowledge of each data type being moved. Our tech centers on a shared “data model” that articulates the core of the user’s experience to be transferred between services. It’s not hard to create *a* representation of data, or a way of structuring data for use; but it's hard to get several parties to *agree* on a shared representation of data to make portability meaningful.


One important observation here is that in the DTP approach, a shared data model doesn’t mean that the APIs themselves are aligned. We try to work with APIs as they come, and use adapter code to translate between the API and the data model. That leaves room for unilateral innovation and evolution at the service end and at the API, without inherently requiring changes to the shared data model – just the adapter.


Navigating privacy and data protection is worthwhile and necessary, but not trivial.


The final piece of this problem space (at least in this articulation) is making sure the recipient can use the data. It’s made easier in the DTP model because the user initiates the transaction; it’s thus functionally the same as if that user were uploading their data to the recipient. Where a user is moving their playlists from one streaming music service provider to another, for example, the use case is obviously parallel. But portability may not always be so clear.


I’m fond of saying that the original ethos of Silicon Valley was “collect all the data, store all the data forever, and figure out how to monetize it later.” We live in a very different world today, one in which we assume the existence of data protection laws which require an approach with some amount of data minimization (i.e. don’t collect data you don’t need) and secondary use limitation (i.e. collecting data for one purpose doesn’t authorize its reuse for something else).


All of these are solvable problems – some with code like DTP’s adapters, others with common sense expectation setting and consent signals from users. But building sustainable, user trusted portability solutions requires more work than meets the eye, particularly if you are stuck in a mindset – or operating under a regulatory regime – that treats all data the same.


## DTI in the News

* [The Future of Data Portability is Direct Data Transfers](https://techpolicy.press/the-future-of-data-portability-is-direct-data-transfers/) (by Delara Derakhshani and Zander Arnao)
