---
title: Symbol GAN unscii
layout: post
toc: false
badges: false
image: /images/symbol_gan_unscii/131.jpg
categories: [synthetic-media]
---

My first experiment with trying to generate new language glyphs. I used the [unscii](http://viznut.fi/unscii/) font because it has glyphs for most of the Unicode characters.
      
Unfortunately, since it's a bitmap font suitable for ASCII terminals, the end result is very pixelated is hard to imagine as letters. It also tended toward
mode collapse, as the generator figured out it could fool the discriminator with a very faint grid of dots in a gridlike pattern.

{% include video_small.html url="/images/unscii-gan.mp4" %}

## Samples
<div style="display: flex; flex-flow: wrap; gap: 2rem">
<img src="/images/symbol_gan_unscii/131.jpg" alt="generated image"> <img src="/images/symbol_gan_unscii/140.jpg" alt="generated image"> <img src="/images/symbol_gan_unscii/130.jpg" alt="generated image"> <img src="/images/symbol_gan_unscii/136.jpg" alt="generated image"> <img src="/images/symbol_gan_unscii/132.jpg" alt="generated image"> <img src="/images/symbol_gan_unscii/133.jpg" alt="generated image"> <img src="/images/symbol_gan_unscii/135.jpg" alt="generated image"> <img src="/images/symbol_gan_unscii/139.jpg" alt="generated image"> <img src="/images/symbol_gan_unscii/138.jpg" alt="generated image"> <img src="/images/symbol_gan_unscii/134.jpg" alt="generated image"> <img src="/images/symbol_gan_unscii/137.jpg" alt="generated image">
</div>
            
