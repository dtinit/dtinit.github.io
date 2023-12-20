---
title: Building a more portable future for text-based social
tags: social
author: Chris Riley
thumbnail: /images/blog/Twitter Social Media.jpg
---

At DTI, we’re starting to dig into portability solutions for something we’ve been calling “text-based social media” – think Mastodon, Threads, Bluesky, and the-service-formerly-known-as-Twitter. In a social space, the problems are both technical and social problems, and the solutions must be as well.

## Text-based social media is so hot right now.

What does the phrase “social media” mean these days? The early evolution from MySpace to Facebook has since spawned branches of networks, each emphasizing different kinds of interaction and media. Born on Vine, today popular short-form video services include TikTok and Meta’s Instagram Reels and YouTube Shorts; on the other end of the technological spectrum, dozens of short-form-text systems have taken off in the space formerly owned by Twitter.

Mastodon, the German software nonprofit company and the eponymous decentralized network of Mastodon-powered “instances,” is growing fast; Bluesky, seeded with funds from Twitter, has added some of the most prolific former Twitter posters, and other entrants like T2.social (now [Pebble](https://pebble.is)) and Instagram Threads are staking their own distinct claims. (And, the broader “Fediverse” around the ActivityPub protocol includes a bevy of other services beyond just Mastodon!)

**Text-based social media is more relevant than ever,** and represents a significant chunk of work at DTI these days. We are co-sponsoring a [hackathon](https://www.inrupt.com/event/solid-hackathon/home) alongside [Inrupt](https://www.inrupt.com/), encouraging development at the intersection of the Solid protocol and social networks. Last week, we joined the [FediForum](https://fediforum.org/) and our CTO Lisa led a robust session on data migration. And this week we’re organizing a [virtual mini-conference](https://dtinit.org/events) bringing together Fediverse developers for further discussion about healthy federated data mobility.

## There’s more work to do, including on portability.

The space feels vibrant, and at the same time incomplete, because **users cannot currently transfer their existing posts among services**. This is a separate problem from protocol interoperability or federation. Those look at whether a post written today can be read by another user on a different service. The portability problem asks whether one user can choose to move their data from one service to another – and what, exactly, “their data” means in this context.

For 15 years, Twitter hasn’t just been a social site, but also a powerful platform for rapid dissemination of information, and misinformation. It’s not only for journalists sharing breaking news, it’s also used heavily by academics and researchers and activists. And these participants  don’t just share links to longer-form papers and reports published in other media, they thread together original concise analysis and key points in short-character form posts.

The original news and analysis shared by professionals on Twitter – and the audience commentary, equally if not more compelling – itself becomes the source of subsequent research and analysis. Tweets can be cited by their Web addresses; the same is true of successor services including Mastodon and Bluesky. **Papers and blog posts link directly to, or reference in footnotes, text-based social media posts that make key points of evidence.**

## Social graphs are important, but portability of posts themselves is an immediate gap.

The main focus of today’s newsletter is going to be portability of posts, because that’s where we see an opportunity to add value in the near term. This may be a bit of a surprise, because the conversations of value in social networks are usually focused on the social graph, the links connecting users to each other, and the network effects that arise from that connectivity. The best post in the world doesn’t carry any value if nobody is there to read it; and new users want to join a network with an active user community (even though [the Yogi Berra dynamic](https://quoteinvestigator.com/2014/08/29/too-crowded/) also pops up from time to time).

Within the Fediverse, the social graph portability problem has some real solutions, including well-engineered [automated migration of followers](https://tantek.com/2023/112/t2/account-migration-post-blog-archive-format) from one Mastodon instance to another. Outside the Mastodon universe, the solution space is a bit more tacked-on, but a number of tools to find Twitter connections on Bluesky have cropped up in particular, like the [Sky Follower Bridge](https://github.com/kawamataryo/sky-follower-bridge).

**Social graph portability is far from fully solved, but it has more momentum in text-based social than post portability.** Even where networks can be migrated or recreated, posts can’t. And this gap isn’t front of mind for many people. The important post isn’t the one we wrote from last year, unless it got a ton of engagement; what’s interesting is the next one to come, the viral one right now.

## What happens if it all just goes away?

Distributing functionality in a decentralized system across a range of smaller servers has a business model consequence: each operator, whether an organization or an individual, must continue to make the choice to support their server. Each one might find themselves in a position where they cannot keep it up, or, as happened with [the Financial Times](https://www.ft.com/content/8d995a24-d77c-4208-a3a6-603d8788ebcd), might just decide it’s not worth it.

What happens then? If a server shuts down, all the posts published on that server are gone.

For a lot of online activity, that might be ok. The URLs of most social media posts are not linked to by news articles or other outside pieces.** But the scholarly references, the posts cited by blog posts and academic papers?** The keen observations, the thoughtful commentary, those bits of diamond mixed into the oceans of social media coal? They go away, and their Web links point to servers that get shut down; they are gone, and can’t be found again.

Some general purpose resources have developed over the years to address a problem known as “[link rot](https://en.wikipedia.org/wiki/Link_rot)”; [Perma.cc](https://perma.cc/) and the [Internet Archive](https://archive.org/) are classic examples. While these add enormous value, they are archival tools, and aren’t designed to make the content available through another social media service. The data survives, but the engagement and dialogue do not. 

## We can rebuild them; we have the technology.

**Getting old posts into new networks is a solvable problem.** For example, posts could be imported into a user’s account with preserved timestamps, and not fed into display feeds presented to other users (as such a data dump could overwhelm the user experience) but could be viewable when an individual profile is viewed. While engagement data on the posts wouldn’t translate as cleanly in all cases, as account access isn’t universal, some facsimile might be possible.

And although the URL to access a post must change if its original server (and thus Web domain) becomes inaccessible, the original URL could be preserved as part of the metadata associated with a post. That requires a little adaptation, perhaps, as “historical URL” doesn’t necessarily have a use case in social services today! But it seems within the realm of the possible.

## Adoption and software optimization don’t just happen together.

The important part, as is so often the case with technology, isn’t coming up with *a* solution to the post portability problem, but coming up with *a* solution *together* so that there is mutual buy-in and sustainability in the approach. It’s the difference between long-term acceptance or abandonment. Heck, it’s even the difference between short-term adoption or a vacuum.

It’s a microcosm for social media itself, where the software and services must be usable enough, but extra benefits in usability are massively outweighed by the network graph of people who can be reached. Bluesky and Threads have both tried to tackle this problem through intentional recruiting of high-volume, high-interest posters; Mastodon has more organically brought communities together in blocks, like the infosec field.

It feels like the adoption curve is critical not only for social media, but also portability solutions. No matter how powerful or elegant the underlying technology is, if you can’t use it to get your data where you want it to be, it’s always going to be of limited utility compared to what it could accomplish. Recruiting high-value targets to be part of a portability solution adds value, as does collecting a field of linked organizations who together use a similar framework for their portability.

**This drive to not just build portability solutions, but build them together, is a core motivating force for us at DTI.** In the space of text-based social, we see deep alignment in philosophy – and we want to lean in.
