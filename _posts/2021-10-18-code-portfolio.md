---
title: A small code portfolio
layout: post
toc: true
comments: false
search_exclude: false
hide: true
categories: [code]
---


## What is this page?

### A potential employer asked me to demonstrate a few pieces of my code. 

I decided to do it here in my notebook, where am I comfortable and where other people who wish to might see it.

This notebook is generated with the [fastpages](https://github.com/fastai/fastpages) framework. Fastpages allows me to write my posts in Jupyter notebooks. That means I can include my code and the actual results it outputs, right on the page. Under the hood, fastpages converts `.ipynb` notebook files into markdown files, and passes those to the Jekyll static site generator. Jekyll is written in Ruby, which I don't know very well, but it was one of the first popular static site generators and it has strong integration with Github, so I've gotten pretty familiar with it over the years. I wrote a few custom modules on top of fastpages, in Liquid and HTML, but mostly left the site uncustomized. On the previous version of my website I spent a lot of time customizing JSX and not enough time posting. I now correct that trend.

The potential employer asked me for 4 things:
1) front-end (a short example in React works) 
2) back-end code (anything in Python)
3) ML modeling - non-DL, and 
4) a DL model. 

As a self-taught coder, looking back at old code can be an embarrassing experience from me. I haven't had a lot of feedback on my code, so I only realize how bad it was when I look at it with more experienced eyes. Nonetheless, it will be a good learning experience for me, so here goes. ## Front-end code

## Front-end code

An old friend asked me to design, develop and host a small website for their community herbalism group in Portland. They mostly organize through Instagram and Facebook, but wanted a flyer site at [https://plantainproject.org](plantainproject.org) to point people to. Especially donors.

I used the Gatsby framework, which was probably overkill for this use case but was a satisfying level of complexity to be a learning project for me. Mostly what I did was modify a template someone else had made, but I'm still pretty proud of the design decisions I made. 

They gave me only a logo (hand-drawn), a few photos, and a text manifesto. I converted the logo to SVG and colorized it, built a color palette and chose fonts around the logo design. Then I designed a layout with CSS Grid, which allowed me to control the pacing of the website using viewport height. 

![image of the website](/images/plantainproject-org.png)

I did this project before I really understood how to use Git, so the bulk of the project was done in one commit ("lump-based development"?). I know better now, but this does give the advantage of seeing [all the changes in one diff](https://github.com/deepfates/plantainproject-org/commit/8137e65aa0259114db48c6db52f328d83a19d6b3). I actually wrote this code in fall 2018, but didn't commit it to a git repo until 2020. :sweat_smile: 

Here's a small grid-based component, using CSS-in-JSX and `styled-components`, which was the fashion at the time. I haven't worked in React much over the last couple years, so who knows how much has changed.

![screenshot of a git diff](/images/react-component.png)

**Note: this is not the most recent project I have done in Gatsby and React, but the others were more complicated and suffered more from JS churn.**

## Back-end code

Because this website is built with `fastpages`, I am able to write literate programs in Jupyter notebooks and use them to modify the website itself. 

I decided to extract the posts I make on Twitter and post them on this site, where they serve as a live-log of my daily thoughts. In [Archive my tweets](/code/twitter/2021/08/13/tweet-archive.html) I walk through the process of scraping tweets with `twint`, downloading attached images and converting them to Markdown posts. These become "deepfates log" posts like [this day where I only tweeted once](/tweets/2021/10/10/tweets.html)

## Machine learning code

Please see my page [Sales Data Exploration](/canon/2021/09/08/sales-data-exploration.html) where I clean and analyze book rankings from Amazon. I go further still in [Minimum Distortion Embedding on book data](/canon/2021/09/09/MDE-books.html), reducing the dimensionality of the dataset and finding clusters, but I do use some deep learning embeddings as features in that notebook.

![a graph from the project](/images/reviewcount-salesrank.png)

## Deep learning code

I refer the reader to my project [Legiblate](https://deepfates.com/code/2020/10/12/legiblate.html), where I train an image classifier to judge the genre of a book by its cover. Or try the  **[Legiblate app](http://legiblate.herokuapp.com/)** yourself!

![Legiblate screenshot](/images/legiblate.png)
