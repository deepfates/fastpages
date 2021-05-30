---
title: "Learning loops"
description: "and rehydrated memories"
layout: post
toc: false
comments: true
search_exclude: false
categories: [robot-face]
---
**Previously,**

I wrote about the [learning curve](https://robotface.substack.com/p/seasons-change) that artificial intelligence models use in their training, and how we can apply it to our own studies. The cyclical learning rate is raised and lowered regularly to alternate between exploring possible actions and exploiting known methods.

Another important hyperparameter in machine learning is the training time. The fewer hours it takes to train your model, the more often you can experiment with it. And deep learning models — like neural nets —are one of the few things left that can take a long time to compute. 

**How long does it take to train a neural net?**

It’s highly variable. I’ve trained [image classifiers](http://legiblate.herokuapp.com/) in less than a minute, [language models](https://twitter.com/deepfates/status/1137040032571637760) for eight or ten hours, [art-generating models](https://twitter.com/deepfates/status/1332775712089104389) for days on end.

And training speed makes a real difference in the creative process: if it takes less than five minutes to train or generate, I will sit and play with it for hours. If it takes a day to train I will fuss over it for a week, fiddling with its knobs every day and leaving it to run. The three-day training run for the art generator, though… Imagine someone was running a vacuum cleaner in the next room. Not a big vacuum — but for three days. I haven’t tried a second experiment.

With machine learning you can speed up training time by reducing the complexity of your neural net or reducing the amount of training data you give it. Either way, you often trade performance for training speed. (But not always! For instance, one state of the art practice for image classifiers is “progressive resizing”, where you train the net first on very small, lo-res versions of your images, and then finetune it on progressively larger versions. This can be both better-quality and faster than training from scratch on the full-size pictures.)

However you do it, speeding up the learning process gives you faster feedback and more freedom for creativity and exploration. 

**How can we apply this to a human learning process?**

One way to speed up your learning process is to review your previous thoughts at regular intervals, like a neural net testing its accuracy after every epoch. The chronological Feed of social media is not conducive to revisiting past thoughts, though. The platforms may offer little “On this day” or “Memories” features, but they’re meant to be tantalizing, not revelatory. They don’t offer insights into the development of your thoughts over time.

I’ve been using a browser extension called Thread Helper to augment this capability in myself. Thread Helper replaces the distracting “What’s Happening” panel with a list of your tweets that changes *in real time* as you type in the “Compose Tweet” box. It surfaces thoughts from long ago for me to thread together and re-interpret in the moment. Instead of being faced with a barrage of ephemeral events and news stories, I am surrounded by my past selves and the thoughts they found it important to write down.

[![](https://bucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com/public/images/f52dffa1-3e62-4290-83c2-96f8cb2c465c_1920x972.png)
 a.image2.image-link.image2-737-1456 {
 padding-bottom: 50.61813186813187%;
 padding-bottom: min(50.61813186813187%, 737px);
 width: 100%;
 height: 0;
 }
 a.image2.image-link.image2-737-1456 img {
 max-width: 1456px;
 max-height: 737px;
 }](https://cdn.substack.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Ff52dffa1-3e62-4290-83c2-96f8cb2c465c_1920x972.png) I’ve been using it for a month now and it’s changed Twitter from a toy into a powerful tool. This interface is a tool for writing and thinking, rather than mindless scrolling. I could use this as my only note-taking system: threading different ideas together, expressing thoughts in small re-usable nuggets and composing them into larger essays. The power of threaded thought is just beginning to take off; for more on that, read *[The Spreading of Threading](https://aaronzlewis.com/blog/2019/05/01/spreading-threading/)* by Aaron Z. Lewis.

Thread Helper makes Twitter into a [digital garden](https://robotface.substack.com/p/digital-gardens). One of the creators of Thread Helper made this analogy explicit:

[![Twitter avatar for @ExGenesis](https://cdn.substack.com/image/twitter_name/w_36/ExGenesis.jpg)xiq, druid of loom @ExGenesisThreadHelper works as a pump that redirects the flow of attention from the present to irrigate the past. You'll take better care of your garden, and others will pass by it more often. 

🧵6/17 ![Image](https://pbs.substack.com/media/ElbyIX_XgAABFIQ.jpg)October 28th 2020

28 Likes](https://twitter.com/ExGenesis/status/1321517547372580866)If the ground is tilted toward the present, Thread Helper pumps your attention back up to the past. It helps to grow your old thoughts into threads and tangles, rather than letting them dry up. It hydrates your memory.

In many ways the Thread Helper panel works like the Drawer from the [Artifacts design fiction](https://robotface.substack.com/p/see-and-point) I wrote about last season: *it brings the information to you*. It increases the speed between having a thought and connecting it into the rest of your knowledge. It shortens your feedback loop, speeding up the learning process.

This is an actual augmentation of intelligence — artificial recall, if you will. I recommend you give [Thread Helper](https://threadhelper.com/) a try. Let me know how it works out for you.

Thanks for reading,

 — Max



---

