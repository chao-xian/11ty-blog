---

title: Low-tech is the new school
---

I was inspired by [Low-Tech Magazine's website design](https://solar.lowtechmagazine.com/2018/09/how-to-build-a-lowtech-website.html) and specifically their approach to how they treat images.

![Image before being processed in original colours](cold-cold-heart.jpg)

![Image after being processed, now sepia tone and dithered](https://5ddbe51130eb310008f18753--focused-williams-e06a20.netlify.com/low-tech/cold-cold-heart.jpg)

I love the look and feel being reminiscent of early 90s desktop publishing (school newsletter during the first "computer club"). Especially the grainy, dot matrix feel of the images fitting into that approach. Great design.

I wrote a plugin for Jekyll that can do the same!

This involved:

* reading up on [ImageMagick](https://imagemagick.org)
* installing [rmagick](https://github.com/rmagick/rmagick) (but the release candidate version as [support for ImageMagick 7 isn't there yet](https://github.com/rmagick/rmagick/issues/256))
* hacking together a script
* [writing a Jekyll plugin that takes all your images and generates dithered, slightly sepia toned versions](https://github.com/chao-xian/chao-xian.github.io/blob/master/_plugins/process_images.rb)
* [deploying a version of my blog to Netlify](https://5ddbe51130eb310008f18753--focused-williams-e06a20.netlify.com), as Github Pages won't have ImageMagick or even allow rmagick to be installed

You can see the results at the beginning of this post.

The downside to the plugin approach however is that Jekyll site builds now take around 30 seconds!

This makes running the trusty old `be jekyll s --livereload` command pretty useless.

Another surprising thing is that the processed image has ended up 3x times the filesize as the original. I must be doing something wrong with the conversion.

So... I may take a different approach to this.