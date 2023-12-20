---
title: A framework for trusted, safe third-party data transfers
tags: trust
author: Chris Riley
excerpt: At DTI, we're looking to build a framework to establish trust between data hosts and recipients, keeping users safe and empowered at the same time.
thumbnail: /images/blog/Hands stock illustration.jpg
---

DTI is a small organization tasked with a big mission: building a healthy data portability ecosystem. Most of our work is collaborative in nature – identifying what we can do alongside other organizations, including of course our partners, but also other organizations both large and small, from industry and civil society.

One of those collaborative efforts that we’re starting now focuses on ensuring that direct data transfers between services – whether through [our own open-source technology platform DTP](https://dtinit.org/documentation) or some other mechanism – don’t pose undue and avoidable risk for users. Our intended output is a framework to establish trust between data hosts and recipients, keeping users safe and empowered at the same time.

The history of data portability is in users downloading data from the host and uploading it to their chosen destination; but its future lies in direct transfers between source and destination. Direct transfer makes data portability more accessible, both by reducing technical literacy barriers and by removing the need for users to download large quantities of data over residential or mobile internet connections, and to devices that may have limited storage or functionality.

And legislation increasingly reflects that advantage. The Digital Markets Act, an important EU law with [frequent](https://dtinit.org/blog/2023/06/06/complex-problem-space) [mention](https://dtinit.org/blog/2023/10/24/global-developments) in this blog, incorporates third parties in its Article 6(9), the data portability obligation imposed on designated gatekeepers:

> *The gatekeeper shall provide end users and third parties authorised by an end user, at their request and free of charge, with effective portability of data provided by the end user or generated through the activity of the end user in the context of the use of the relevant core platform service, including by providing, free of charge, tools to facilitate the effective exercise of such data portability, and including by the provision of continuous and real-time access to such data.*

But there is some inherent risk in transferring personal data directly to third parties, in that the data recipient may not be able to (or may not even intend to) keep the data and data subject safe. This may seem to introduce a tension, in that the user has asked the host to transfer the user’s data to the specified recipient, and exploring the risk of transfer contemplates the possibility of the data host saying “no”. However, there are scenarios – such as where the recipient has not been honest with the user about their future actions – where blocking the transfer request is the right thing to do, and where it is necessary for user safety.

Reasonable safeguards can establish a foundation of trust to minimize this risk. And in contrast to what might seem to be misalignment in an individual transaction, building trust supports and grows data portability by helping people feel that the systems for engineering data transfers keep the process safe – without undermining their ability to exercise conscious choice and control over personal data.

## A foundation of trust is valuable.

Where direct transfers are executed by a server running DTP, we have confidence in user safety in the transaction, because we know our partners. Our architecture typically incorporates code provided by the data recipient (in the form of an adapter to translate to, and call, the recipient’s import API) into DTP software when it is run by the data host. While DTP is open-source and thus the tools can be adapted and run by anyone, taking part in the architecture as we have set it up includes agreeing to a set of principles (as articulated in [the 2018 Data Transfer Project Overview paper](https://dtinit.org/assets/dtp-overview.pdf)) that lay a foundation of trust.

But there’s no generalized agreement or framework for establishing trust in direct data transfers. We envision a shared set of commitments for would-be data recipients (or “third parties,” where the user and the data host are the first and second parties) in some context in which they can carry force. These would include things along the lines of “don’t hide from your users what you’re doing with their data.” There’s no way to guarantee fully against harm, but safeguards can be designed that help minimize risk, while maximizing user empowerment in data portability.

## This feels like, but is different from, data protection and privacy.

In jurisdictions with adequate data protection law, these sorts of commitments should be easy to agree to, because all data processors are required to be responsible and transparent. But not every jurisdiction has such laws. And users will request transfers that cross jurisdictions (absent the introduction of greater harm in the form of internet segmentation!). Furthermore, even within a jurisdiction with strong protection rules, while the arm of the law may be long it does not often move quickly; [law is not self-executing](https://dtinit.org/blog/2023/08/01/law-isnt-code).

Direct data transfers reduce friction in data portability; they also thus reduce friction of potentially harmful or simply inadvertent data transfers. Having more levers to enforce good behavior up front prevents some amount of irreversible harm – because data once shared can’t readily (if ever) be un-shared.

For many people reading this, I expect the proposal is starting to sound like a “trust framework” from the privacy universe. In many different contexts over many years, industry participants have gathered together and built shared trust frameworks, voluntary commitments to specific practices that will help promote privacy and good user outcomes. While these can lead to significant benefits, voluntary commitments can also be seen as distractions to delay or avoid regulation.

Here, however, the obligation to transfer data to third parties is already law (in some places). The envisioned framework isn’t trying to create a new norm or an obligation *per se*. Rather, it’s motivated by the open-textured nature of laws like the DMA, which leave some implementation questions for designated gatekeepers to take the first steps. A shared framework wouldn’t undermine the relevant law in any way, but rather would strengthen it.

## Security and trust are better built together.

Direct data transfers begin with the data host’s Application Programming Interfaces, or APIs. Wherever such APIs provide access to personal data – as portability APIs must – they are authenticated to ensure that the request for access is authorized. In addition to authentication, API access policies typically include other requirements and limitations on the rate and other terms of access. To transfer data through APIs, organizations must exchange API keys, and make various commitments to do so.

Similarly here, an *ad hoc* solution is possible. Each data exporter could adopt its own framework for security and privacy commitments that must be made by third parties requesting user data transfer to establish trust. However, a shared framework is preferable – it encourages greater neutrality and consistent application of review, as well as more efficient and effective external stakeholder participation in development. Additionally, data recipients would face an easier path to data access, needing only demonstrate adherence to a single framework to satisfy multiple participating data hosts.

## So let’s build something.

At DTI, we are starting to talk to a range of key stakeholders about this problem, including data hosts as well as organizations like [CODE](https://www.codepolicy.org/) working on data portability and user empowerment. We anticipate that there may be multiple efforts in this vein, including efforts we’re not aware of, so our first step is to engage with a lot of different perspectives, and identify any useful resources that already exist. Then we can determine whether there’s a path forward to develop a shared framework and what that path looks like.

We’re early in this process. We’ll provide periodic updates in this format, and in the meantime, if you’re interested in working on this with us, [send us an email](mailto:secpriv@dtinit.org)!
