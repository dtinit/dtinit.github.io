---
logo: dark
---
# The Federated Data Transfer Miniconference: A Summary

On September 27-28, 2023, DTI hosted its first Federated Data Transfer Miniconference online. This event brought together dozens of Fediverse developers with guests from established Indieweb projects and large tech companies alike to discuss the state of play of tooling and policy allowing users to move accounts and personal data, between servers within the Fediverse. While protocol interoperability addresses many compatibility challenges through the shared use of ActivityPub, the larger Fediverse is bigger than ActivityPub and the process of moving between servers and services presents a set of distinctly human challenges.

Below is a summary of the day’s events. DTI has chosen to publish this summary in the interest of transparency. Within it are a number of observations and conclusions held by some or many of the participants, but no formal exercise was conducted to gauge consensus or otherwise aligned output. Consequently, statements in the report do not universally reflect the positions of DTI or any other organization or individual. This document is meant as our best effort to capture the tenor and substance of the discussion as a whole.

The team at DTI is immensely grateful for the contributions of participants in this exercise and the wisdom that the collective group will provide for any future efforts, including by DTI and other parties, to build more features and functionality of data transfer within the Fediverse.

As an additional note, many of the challenges discussed at this event and reflected in this report are broader than the context of data portability  that prompted them. Trust and safety challenges within the Fediverse, in particular, are not solved universally through any mechanisms that might be built to address them within the context of data transfers; furthermore, such concerns are not specific in any way to the Fediverse, but rather reflective of challenges facing the internet at large. That said, they are of equal and specific importance in the context at hand, and thus feature substantially in the report below.

**In brief**:  Over the course of discussion, the participants gravitated heavily towards trust and safety challenges that can arise from data transfers, and in particular the risks faced by servers allowing data import who may not have adequate (or any) moderation capacity to mitigate harm. 

As a baseline, the ability of users to migrate their data between federated services is desirable, but any naive approach to this goal is a loaded gun. On the other hand, data transfer tooling can and should be significantly improved, to the benefit of users, site managers and the overall ecosystem, by finding a rough consensus on an overall structure that includes usable signals to support trust in the integrity and safety of the transaction and the data at hand. 

Importing arbitrary user data presents real social, financial and legal risks to site owners and moderators that demand robust, usable network- and community-aware tools to help those administrators uphold community norms and meet legal responsibilities. Without those tools, this effort will not just undermine our goals of an open, participatory ecosystem, but will actively foster a future of walled gardens.

--- 

## The Setup  

Over the course of two half-days we put six big topics in front of our guests: 

**The Purpose Of A System Is What It Does (and for whom, and to whom)**

> For whom are we building? Who are we empowering? Who might be harmed by this work? Who are the audiences whose needs we must meet as we build import and export tools? What do we value in that migration; who is afflicted by the failure or absence of these tools, and what can be done to address the needs of individuals of all backgrounds?

**Bright Lines And Guardrails: Moderation Standards, Moderator Health And Sustainability** 

> What constitutes a just and fair system, in this context? What safety guardrails are necessary? What kinds of tools and support mechanisms do we need in order to make migration sustainable and viable to both ends of the relationship?

**Lawyers, Guns And Money: Real-Life Consequences, Fears And Responsibilities Of Instance Ownership**

> What are the real-life risks and consequences to operating an instance of a Fediverse service, and how do they intersect with the idea of user data migration?

**Community Safety, Norms And Expectations Around Data Migration**

> We’re trying to build tools that empower citizens, and allow communities to engage in self-protection. What community norms and standards should we support in this, and how can we understand and meet user expectations?

**Dreaming Big**

> In 3 years, we’ve won. Tools down, pack it up, we’ve achieved overwhelming success. What does that look like? What have we built, and how is the world different because we built it?

**Minimum Viable, Minimum Credible**

> What do we do next? What do we have to ship to demonstrate that we have not just a viable process, but a safe, credible, responsible process, and more importantly that there is a safe, credible and responsible group of people stewarding the development of this process?

The rest of this report is the details of those discussions.

--- 

## The Purpose Of A System Is What It Does (and for whom, and to whom).

For whom are we building? 

This question quickly became an exploration of constituencies and their particular needs, particularly for audiences that might be described as "on the margins of circumstance", meaning those people who are structurally marginalized in their larger context.

While we didn’t (and likely can’t) create an exhaustive list of those constituencies, that does not exempt us from a moral obligation to make the attempt. To that end, there were recurring themes brought up around what qualities those audiences might share.

Among those were the stories of people in situations of legal or situational precarity. This can include homelessness, domestic violence, migrancy or any other situation where the social resources that emerge from physical and social stability are unavailable. Technical/data migrations are frequently - and often urgently - directly connected to human migrations, and these needs should be well-explored and understood to be a set of baseline expectations rather than aspirational goals.

In addition to migration between spaces, another topic of discussion was migration between identities. This is an equally and perhaps more difficult space, emerging from the fact that most of the structural support for freedom and safety are anchored in a bedrock of unique and state-sanctioned identity. This is an incredibly complex area - what kinds of transitions between what kinds of identities and identity-markers are possible, not to mention, when and where and under what circumstances they are permissible or safe, is something that any data transfer work will at a minimum need to admit are real problems that exist, and that it is possible that any simplifying assumptions we might make can result in a real loss of agency and real-world harm for those people they affect.

A related and recurring note was that any sort of inherent technical competency on the user’s part - roughly defined as "can make the computer do the thing, whether the computer makes that easy or not" - is not a permissible barrier to success, particularly in light of that precarity. This was a wide-ranging discussion, where competency might include language barriers, accessibility and discoverability affordances at both ends of any transaction, as well as an exploration of what revealed preferences might look like through different interaction mediums - not just mobile and desktop, but how services might collaborate in the discovery of user need and intention through their interactions. 

Participants also noted that learning from revealed preferences was limiting, given expectations around interoperability, that "informed consent" is an important bar to clear given that the bar here historically has been "basically nothing works". It was observed sarcastically that in terms of utility, we want to make this better for people whose current benchmark is the shitpost, the screenshot taken in one service and paste into another. It won’t be hard to do more, but there’s a lot of work between "more" and "better."

Hearteningly, developer ergonomics - while understood to be important for development and adoption - were not the driving force of this part of the conversation. The general consensus was that understanding and bringing humility to the exploration of the complex interplay of evolving user needs, identities, safety and risks particularly on the margins, is of the highest priority.

## Bright Lines And Guardrails: Moderation Standards, Moderator Health And Sustainability

"Migration", of course, is not "export". A migration is departure, a transit, and an arrival, often to new communities with different norms, standards, cultures and rules. A successful migration isn’t just about leaving with all your stuff, but about the safe arrival in the new environment. Starting from that point, the conversation quickly became about asymmetries of resources and scale. 

There were a few points that the discussion seemed to agree about early.

Historically, few open source projects invest heavily in user safety up front and - almost invariably - the safety tooling involved is isolated or islanded, even when built into distributed services. A common, well-worn story dating back to the earliest days of networked computing is about open, shared services born without access controls or guardrails, and the discovery of how difficult or impossible it is to retrofit security into systems born without security in mind. The importance of building in a flexible, adaptable approach to user and moderator safety from the very beginning was widely agreed to be crucial. 

Starting from that shared understanding that scalable safety and moderation support is the least people should expect from responsible federated systems, the next part of the discussion quickly became the classic information security discussion: "What’s Your Threat Model".

This part of the conversation opened with the now-classic Parable Of The Nazi Bar:

> "You have to nip it in the bud immediately. These guys come in and it's always a nice, polite one. And you serve them because you don't want to cause a scene. And then they become a regular and after awhile they bring a friend. And that dude is cool too. And then THEY bring friends and the friends bring friends and they stop being cool and then you realize, oh shit, this is a Nazi bar now. And it's too late because they're entrenched and if you try to kick them out, they cause a PROBLEM. So you have to shut them down. [...] "yeah, you have to ignore their reasonable arguments because their end goal is to be terrible, awful people."

One challenge at the intersection of migration and moderation is that inbound community members are bringing their histories - text, photos, videos, and relationships - with them, and depending on the import mechanisms might be retroactively slotting all of those into the instance’s historical record. The phrases "Surprise Nazi Bar" and "Retroactive Nazi Bar" described different expressions of this problem, and - stretching the metaphor a bit - that stakeholders include the bar owner, the bartender, the patrons and the street outside.

This conversation also made it clear that automation that can share information and actions between instances is going to be crucial for any instance or community that grows past some size, or that admits histories beyond some size. It just won’t be possible for a moderation team to make informed judgements about imports of any scale, or appearing with any frequency, without automation that shares local standards, notes from the origin community and instances, and other data and metadata to help facilitate moderation at the importing step.

Because so many of these questions revolved around the size, resources and capabilities of the communities involved, it was also noted that we would do well to define what a "small" or "large" community is, without constraining ourselves to serve only communities meeting those terms, nor can we be dogmatic about what constitutes membership or uniqueness - people can be in different places, and even be different people while they’re there.

As well, one participant noted (paraphrased):

> "There are specific use cases that people certainly care about; for example on the Fediverse, people want to be able to move from one server to another and bring all of their content and relationships with them, where Mastodon, for example, lets you bring relationships but not content to a new server. 

> From a developer perspective this makes sense because taking your content with you and putting it on a new server is technically forging messages. [...] technically you want to do some kind of complicated derefrencing, etc etc, but users don’t really care about that by and large. From a user perspective, it’s like, this is my stuff that I posted, I am going to stake a claim and say "Heyy you have to trust me that when I say I said something, I truly said it". 

> Ultimately when you are doing DNS-based and person-based trust the user expectation is to wing it and not worry about mathematical proofs. On centralized social media the trusted entity is the company: when I’m posting on Facebook you are trusting that Facebook wouldn’t let me back-edit something I wrote years ago to make myself look smarter. That trust (earned or not) goes away in decentralized contexts."

One key insight from this conversation was that it is far easier to automate malicious content and actions than it is to curate the good. As a result, without building effective and usable filtering, tracing and auditing tools (e.g. "X posts from this user, which all come from import Y, have been flagged") it’s clear that any moderation process, any moderator, can be trivially overwhelmed. The psychological cost of solitary, unsupported moderation is just too high.

On the other hand, tools designed to foster a combination of reciprocal trust relationships between motivated communities and assistive tooling might dramatically mitigate that cost. But it’s clear both that these tools need to be carefully considered from the outset, and that export/import implemented in its most naive form risks amounting to little more than an existential attack surface.

One call to action in this session was that the portability of moderation data, in addition to user data, was going to be necessary if the larger Fediverse was to create some sort of scalable, mutualist "immune system" in the face of scaled, distributed bad actors. Some hypothetical machine learning tools were discussed, but the consensus reached was that given how much human nuance is necessary to safety and moderation at any level, their utility in this space is - charitably - unproven.

## Lawyers, Guns And Money. What are the Real-Life Consequences, Fears And Responsibilities Of Instance Ownership?

These conversations covered both the complexities of legal responsibilities and how quickly - and dramatically - those legal burdens (and potentially costs and risks) could change or escalate. Examples given included the DMCA, the UK’s Online Safety Bill and other pieces of legislation aimed at large and small providers alike; one participant identifies the Online Safety Bill in particular as making no distinction between giant, well-funded and much smaller providers specifically because OnlyFans employs less than fifty people, and the legislative trends now seem have taken into account that small shops can have outsized impact in any social computing field. Much of the discussion was around the nature of these threats; again, this was very much a What’s Your Threat Model conversation, both on a practical and social level. 

This is a particularly relevant question, considering how likely it is that very few people starting up their own instances of any social network realize that they are becoming a hosting or service provider, and that they may well now be constrained in jurisdictions that they’ve never visited by laws they don’t even realize exist.

This poses a series of high stakes and mostly unknown risks for instance owners and operators in the context of user migration, particularly in light of historically federated systems that have assumed both truth and good intent in user interactions, which has not proven to be a foundation of safety for participants and operators of those systems. More specifically, one point made repeatedly was that the mere existence of these risks is inherently inequitable and undemocratic. Given that importing information to a device you host is to some degree sanctioning that content, certainly vulnerable populations - or really any group that might find themselves at odds with state authority - might reasonably decide that if the cost of participation in the Fediverse is risking a conversation with the Actual Feds, that it just can’t be worth allowing that. 

This conversation came back to the importance of transparency and tool-assisted support for decision making around imports, particularly around nuance, flexibility and intent. Several people observed that mere legal compliance is not a substitute for structural responsibility or accountability, and that weaponizing both compliance and noncompliance is not difficult. Functioning community-safety-focused import/export tooling will need to both let community moderators establish their own defaults - e.g. no image/video imports, keyword matching - while also providing communities with visibility into high-level trends and the ability to take reasonable actions based on what they see. 

As with the previous session, the discussion also ranged into the importance of shared moderation information and trust signals as tools for making these risks bearable, which was immediately - and correctly - regarded as a big, difficult set of social and conversations, a huge can of worms - "what is a trustworthy signal, in fact what is trust and what is a signal", "how can this trust model be itself trustworthy", "what does remediation mean", "how can it be subverted by one or more malicious actors". The only consensus to this point was that these are all really hard, fundamental questions about human relationships that we need to be opinionated about, that we can’t ignore without accidentally building tools of oppression and marginalization.

Both the high level and granular details around tools emphasized a larger issue about informed choice and clear action that isn’t a mere technical point but that felt necessary to the larger questions of user data migration and safety: that service owners need a reliable source of information about what risks their communities might incur, at what sizes and in what jurisdictions, and what if anything they can decide to do with that information to secure themselves and their communities. 

## Community Safety, Norms And Expectations Around Data Migration.

This was the most wide-ranging discussion we had, one that spent a lot of time oscillating between high-minded ideals and the boots-on-the-ground realities of modern community. 

Key observations include:

- "Interoperability" is not "consensus", and cannot require consensus.
- "It works the way it should" does not mean the same thing to any two people.
- Community expectations are enabled and empowered by technology, but not decided or driven by them. These are human problems first. 
- There is a lot of historical precedent here that we should understand and leverage rather than trying to build our own ideas from scratch.

The most important work we can do here is taking cues from successful, long-running communities of creators - Ravelry, LiveJournal, DeviantArt, there are many others - in which a great deal of community durability comes from established reputation. Though most (all?) of those forums don’t have meaningful federation or data portability goals, they are also heavily self-policing because the reputational weight of a long-running account can’t be easily rebuilt or sockpuppeted. 

On the topic of commerce and commercial support, there are inherent conflicts between migration and sustainability, in communities of this type. The discussion acknowledged that people whose livelihoods depend on the agency they have, and the support they get from their hosting sites, will necessarily be affected by the work we are proposing to do here, even if they aren’t aware this work is happening. The possibility of an emergent set of community norms around migration will necessitate new norms inside the Fediverse and out about money. 

Fediverse is historically noncommercial/not-for-profit in its foundations, but doesn’t seem adverse to artistic self-promotion. Likewise, successful artist-supporting services typically support themselves with a fractional cut of the artists’ work. Some suggested that, since moderation work frequently needs to be financially supported, what we might call a "creator’s migration" could increase the costs and viability of healthy moderation.

This context was described as enabling the internet as not just a third space, but "a third space as critical infrastructure", "a third space of connected third spaces;" the frame took root and led to further discussion. At the risk of over-rotating on something possibly superficial, the notion of "threes" extended to many of the metaphors used in this part of the discussion: the "three-body problem" of exporting service, importing service and the migrant moving between them, and the "third shift" of maintenance and moderation work were also discussed. Again, possibly superficial, but asking questions of this general shape - "who is the unrecognized intermediary in this, what is in between or outside these two things that we have not acknowledged" was a reliable tool for interrogating ourselves and the impact of our proposals in these discussions.
Dreaming big: In 3 years, we’ve won. 

Let’s imagine that in three years we’re back here, and we agree to the world is done; down tools and pack it up, we win, we’ve achieved overwhelming success. What does that look like? What have we built, and how is the world different because we built it? 

There was a lot of optimism in this part of the conference, and a lot of different visions for what success might look like, and what it might mean.

Success, to some, meant "a collection of open standards, widely available and useful for all". Being able to move yourself around the social graph without anxiety, bringing your work, your art, your context and your relationships with it; in a perfect victory, this is just a few clicks away from seamless and frictionless, as painless as possible. 

For others, it meant community safety becoming not just an expected norm, but a competitive advantage - that governance, maintenance and shared purpose and common ideologies can become meaningful reasons to choose some new host service as a destination. 

One fascinating notion of success was both fundamentally technical and verged on the mystical, the idea of having real control over your own name - that unlike losing the email address of the company you’d worked for, that "user agency" in this context meant not losing control of the means of communication, rather moving it to a new home. A fascinating rebuttal to that - again, at the intersection of the technical fundamentals and the near-spiritual, was that migration to communities with different norms and filters would grant the concrete opportunity to curate who they wanted to be, and where, and when. That in contrast to algorithmic attacks on the psyche that reinforce historical behavior, that the freedom to change your name, your habits, the world as you experience it, can be given you. 

Above the notion of migration, even just export-and-analyze might be able to show people things about themselves that they’d never seen. Utilities that let you do or learn something about yourself, the idea that people might be able to know themselves as well as marketers claim to could be a profound avenue of self-discovery and growth. 

As well, in this increasingly toxic, increasingly artificially generated world, some means of establishing provenance, some set of relationships that have a shot at describing relationships as true and meaningful, the vision of communities of mutually supportive communities, each able to enjoy some shared ideas of consensus, safety, provenance and veracity that are supported by nuanced moderation and effective tooling, was inspiring.
Minimum viable, minimum credible.

So, what do we need to deliver? What is the minimum viable product for Fediverse data transfer that looks credible, what is the minimum viable credibility that makes the product worth investing in? What do we have to ship, in order to demonstrate that we have not just a viable process, but a safe, credible, responsible process?

The first question in this discussion was the first question of the summit: For who? Who are we doing this work for, and are they in this conversation? We need to elaborate that, first and foremost. The classic Silicon Valley idea of the MVP should be avoided here - we aren’t trying to demonstrate just functionality in this, but safety and trustworthiness as well.

The next question is to elaborate what is going on now, across both activitypub and non-activitypub services. Even between Mastodon/Activitipub instances, there is a fair bit of daylight between current user migration flows and the "export your account" button.

One longstanding assumption about portability is that the way to achieve it is to "get the big players in the room and get them to agree"; it is likely that this is an anti-pattern, both in the large (because of the incentives at the big-player level) and because of what we might call adoption-credibility. Tools that support larger players are likely to be challenging for small projects to leverage easily. One speaker mentioned that "if you’re not getting engineers saying that something is too simple, that couldn’t possibly work, then it’s not minimum enough."

Some concrete steps forward identified over the course of discussion include:

- Listing a set of high-value targets for Federated Portability (very small, this is an NxN problem) and enlisting the participation of these services in building transfer tools;
- Analyzing where and how each of current Fediverse services’ export/import tools currently work, and in which respects they are lacking;
- Collectively developing a baseline acceptable degree of safety and transparency for both individual migrants, communities and their moderators;
- Building more modular tools for migrating data across different formats, at any level of meaningful scale and impact; and
- Developing drop-in import/filter tools to assist moderators in accepting imports by allowing them to be analyzed and filtered/rejected based on specific criteria.

## Thank You

The Fediverse has a deep bench, and everyone at DTI is grateful to the participants who gave us their time to share their expertise, experience, passion and optimism at our little first-time conference. We hope we’ve done your contributions justice in this too-brief summary, and we hope to do your passion and optimism justice as we all work to build out and build on everything we’ve learned together.
