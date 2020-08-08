---
layout: post
title: Corona-proof Magic the Gathering
image: assets/images/mtg-3.jpg
# show_feature_image: true
tags: [ development, hobby, en ]
---

I have an idea for a neat little app. The feature would be to take a picture every x seconds. But it has a few very specific usecases. So let me first tell you how I got the idea. Hopefully you'll appreciate my genius a little more then :)

## Birth of the idea
It all started this April. My monthly game of [Magic the Gathering](https://en.wikipedia.org/wiki/Magic:_The_Gathering) (Magic for short) was cancelled because of COVID-19. But that didn't stop our fearless Wizard (middle guy in the drawing below!). He concocted an ingenius plan to still be able to play from the sanctuary of our own homes.

{% include image.html file="mtg-3.jpg" caption="Our fearless crew" %}

A few days before the event, we each found a moving box on our doorstep. It contained everything we needed, including a manual how to set it all up. We would be needing a laptop and a mobile phone on a charger. The box was decorated with lines and text as well. 

{% include image.html file="mtg-4.jpg" caption="The box was richly decorated with helpful texts :)" %}

And voila, this is the end result:

{% include image.html file="mtg-1.jpg" caption="The corona-proof magic setup" %}

It works like this. Every player has two video feeds into a Google Hangout. One is from the phone mounted above the cards in front of them, the other is of the laptop aimed at the players face. This way you can see your oponents, but you can also take a close look at their part of the battlefield.

And it worked surprisingly well! The only downside was that the resolution of the Google Hangout was not well enough to be able to read the cards. So I ended up opening a new browser window for each card that was put on the table, and pointing it at the specific card on [Scryfall](https://scryfall.com/). Owh, and after 2 hours of playing some of our phones turned themselves off because of excessive heat :) It worked for a night, but there was definitely room for improvement!

{% include image.html file="mtg-2.jpg" caption="By now we're playing IRL again, thank heavens :)" %}

## The pitch

I want to create a mobile app that takes a high-res image every few seconds, and uploads it. You can send the URL to your image to whoever you want to view your feed. That's it.

The viewer would be desktop first website, and all it needs is to view a single image fullscreen, zoomable, and reload it when it changes. Of course, when the image changes every x seconds, the area you're zoomed into should be maintained. That sounds like a nice job for [Micr.io](https://micr.io). You can throw a huge image at Micrio and it gets tiled, stored, and viewers only download the tiles that are in their viewport. So it might even me possible to first send the tiles that are in viewers viewports, and the rest of the tiles later in a background thread. Talk about premature optimization...

## Other usecases

Of course an app like this can be used in other scenario's as well. I mean, how often are people going to play Magic during a lockdown... But there's one other usecase that I think is really interesting.

> There's just no digital equivalent for a whiteboard marker

At Q42 we love working with post-its and whiteboards. There's just no digital equivalent for a whiteboard marker to just draw some lines and get your point accross. But when we're working for international customers, we're not going to be sitting in the same room very often. In that case we do these sessions via Google Hangouts. And if we need a whiteboard, we point a camera at it. But of course all the small scribbles are not readable for the remote joiners. Enter an app that facilitates high-res image sharing instead of low-res low-latency.

## Get to work!

This app is so small it might be quicker to just build it, instead of writing a blogpost about it :) But I'm thinking of making a shiny app out of it during [W00tcamp](https://w00t.camp), Q42's yearly hackathon in November. Take some time to flesh out the usecases, create a native app for it that is friendly on your phone's battery and data plan... Now I've got something to look forward to!

~~Or, of course, I could check the appstore if someone else has already built this marvellous idea...~~
