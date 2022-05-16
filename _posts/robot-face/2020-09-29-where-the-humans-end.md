---
title: "Where the humans end"
description: "and the computers begin"
layout: post
toc: false
comments: true
search_exclude: false
categories: [robot-face]
image: images/robot_face/humans-end.png
---
**Previously,**

I wrote about how trees garden the forest for themselves, how humans can garden the world for ourselves, and how we shouldn't let the computers close the canopy. Computers and humans should be friends, but that's not how it's gone so far. 

Right now computers are cultivating human communities with the sole purpose of increasing the influence of the computers. They're gardening us.

**How are computers gardening humans?**

Human life used to be centered around the village square. There were other scales of society -- kings and lords, parents and children -- but the village was the main operating unit. You would know most, if not all, of the people you see daily. The "public" was a physical space. You're out in public, you see people and they see you. If you're not in public you're in private. The biggest transgression of this boundary was writing: you could transmit thoughts from the privacy of your room into the world at large. Or you could curl up in bed alone and read of public events from far off or long ago.

Now we connect our minds in real-time to strangers all over the world and yet we never leave our homes. 

I don't just mean the pandemic; there was a time before this plague, and there will be a time after it. In the beforetime, you could wake up in your house, drive your car to your job, go to the gym and the grocery, and come home without ever being in "public". Every space is instrumentalized. You go here to do this and there to do that, you buy and sell, you paper-push and weight-lift. No accidental interactions. If you see someone from work at the grocery store, you ignore each other, right? Easier for everybody.

Can you think of a place that's truly public? A place with the feel of a village square, where you don't have to work or buy anything but can just be together with people? (These may still exist outside of America. But I've never left this country, and I might not make it out in my lifetime, so I'll write what I know.)

We have parks, libraries and mass transit. That's about it. And in all of these places we are encouraged to be quiet, keep to ourselves, leave other people alone. If a stranger approaches you in a park, do you think they're trying to make friends?

The spaces that feel public now are the social media platforms. We see our friends, neighbors, strangers, political allies and enemies on the internet, and instead of keeping to ourselves we are encouraged to Engage. We attempt to understand others through these computer-mediated systems, but it is impossible to tell where the humans end and the computers begin. The platforms are constructed by humans, true, but they're built to serve a very computational purpose. They connect advertisers with consumers. Every social platform, whatever their gimmick and cutesy name, is a commercial space: The Customer Store.

**These platforms are built by humans, though. How do the computer's desires come in?**

Well, take Twitter for example. It's not the most populous site -- only something like 22% of Americans use it -- but its effect is outrageously large because it's where politicians and journalists and academics hang out. Unlike Facebook or Instagram, Twitter is not designed for keeping track of your meatspace friends. It simulates the public sphere: you, too, can shout obscenities at your favorite public figures! But it is still a customer store, and it has to operate efficiently. That's where the computer takes hold.

See, there might not be that many users, but there are a lot of tweets. Roughly five hundred million tweets *per day.* So their goal, to recommend the right "promoted tweets" (ads) to the right "users" (potential customers), is significantly hard. Even for machines. 

To succeed at recommendation, they need to optimize for computation. The machines of Twitter can't replicate natural human relationships at this scale. They have to find a way to get good-enough results without burning a ton of compute power in the process.

To that end, they've built *SimClusters: Community-Based Representations for Heterogeneous Recommendations at Twitter* ([get access](https://www.kdd.org/kdd2020/accepted-papers/view/simclusters-community-based-representations-for-heterogeneous-recommendatio)). This program plots all types of content (tweets, users, "Events", "Topics" and, of course, ads) in a high-dimensional space of "communities". These communities are simulated clusters (hence the name) of "influencers" who have largely the same followers. 

**What is an influencer?**

It's a loaded term, but in this case it's merely a mathematical distinction: there are about a billion twitter accounts, but only the top ten million are classed as influencers. The SimClusters algorithm flattens all the users into a bipartite graph, with influencers on one side and all user accounts on the other. Then it looks for high density of incoming connections. That is, it looks for groupings where a bunch of users follow the same few influencers. These people may or may not know each other, but they occupy a similar position in the social structure. 

This creates a rich-club graph -- an oligarchy, in political terms. The influencers are core to their communities. In the 2018 paper *Conjoining uncooperative societies facilitates evolution of cooperation* ([PDF](https://arxiv.org/pdf/1805.12215.pdf)), which I have linked to before, it is shown that in a rich-club graph the fate of the periphery is decided by the core. It is indeed possible for separate rich-club-shaped communities to cooperate; however, the amount of cooperation is limited by the amount of oligarchs. 

![](https://bucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com/public/images/3cc71db3-0d6d-4661-9635-769da88f8bf7_674x491.png)

Twitter has to draw a line between influencers and the rest of us. That line is arbitrary, and the size of the rich club of users is hardware-limited. The ways in which we connect to each other forms a microcosm of the modern city: if you're an Influencer, you can warp social reality around you. The rest of us can go to one of the influencer-defined communities and do the prescribed behavior.

We are sorted into fields, like crops, so that we may be marketed to those who would buy our attention. The complexity of our interrelation is flattened to a manageable level for profit. This is computers gardening humans. It’s not sustainable, but of course it’s not; they learned from us.



---

*Let me know if you have any questions, comments, dire warnings, etc. Just reply to this email.*

