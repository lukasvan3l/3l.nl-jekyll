---
layout: post
title: FabricJS + OpentypeJS for Hallmark
image: assets/images/hallmark-1.png
tags: [ development, en ]
---

Recently we helped Hallmark Netherlands to rebuild their custom card editor into a version that’s designed mobile first. It’s gradually being rolled out, at the time of this writing you can see it in action with [this card](https://nl.hallmark.be/kaarten/verjaardag-vrouw/best-verkocht-v/hallmark/hooray-on-your-birthday-3288693.aspx).

{% include image.html file="hallmark-1.png" caption="Mobile friendly card editing — now at a Hallmark near you!" %}

Together with designers from Fabrique we built a card editor that is specifically built for mobile use. The new editor has as little clutter as possible, and has a “focus mode” that helps you edit one aspect of the card at a time. This new UI was what Hallmark was aiming for, but we also managed some technical benefits.

## Pixel-perfect printing
One of the technical challenges was to get the rendering on screen exactly the same as the rendering by the printer at the end of the process.

The core of the problem was that the server and the client had a completely different way of rendering a card. The server used Adobe InDesign to generate a printable PDF of a card. The browser took the same input XML and rendered it on-screen using custom Canvas2D.

Unfortunately, the text rendering was sometimes off by a fraction of a millimeter. In some cases this ended up in words breaking off differently, and you’d get really weird cards.

{% include image.html file="hallmark-2.jpeg" caption="whoops…" %}

Our hypothesis was that if we could use the same text rendering on the server and client, we could fix this quite easily.

## Enter opentype.js
Our first step was to have the server render the card using NodeJS. This way we could use the same code & libraries as in the browser, and minimize differences. Unfortunately, the rendering of fonts was still different. Which isn’t very surprising by the way, even different browsers render fonts differently.

After a bunch of experiments, we found a unified way of drawing text that isn’t dependent on the platform it’s running on. Opentype.js is a library that can generate vectors based on a font file. Our first successful experiment rendered the vectors in the browser and sent those to the server. Worked like a charm, because the server didn’t get any text, only vectors. And it doesn’t interpret vectors, it just draws them.

The downside is that those vectors can become pretty big. If you write an A5 card full of text in a curly font, you’ll get a couple of Mb’s of vectors. Luckily it also worked to send the text to the server and use opentype.js on the server to render the text.

## Wanna see?
For a demo, head on over to [https://q42.github.io/fabricjs-opentypejs-demo/](https://q42.github.io/fabricjs-opentypejs-demo/). It works just like a normal fabric.js instance, but underneath it’s rendering vectors.

{% include image.html file="hallmark-3.png" caption="You’re not looking at letters, you’ll looking at vectors!" %}

This demo has the essence of the card editor in it: [Fabric.js](http://fabricjs.com/) for the interactive card editor, and Opentype.js for the font rendering. If you want to snoop around behind the scenes, check out the code on [https://github.com/Q42/fabricjs-opentypejs-demo/](https://github.com/Q42/fabricjs-opentypejs-demo/).

These libraries, glued together with Vue.js, allowed us to really keep our codebase lean & mean. We only had to develop the specific user interactions we wanted. Fabric.js did all the ground work for rendering and interactive controls like panning, resizing, etc. When Hallmark’s own development team took over for long-term maintenance, there was a lean architecture that they could easily continue working on. Win-win-win!