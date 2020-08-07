# 3l.nl-jekyll
Luuk's bright, Luuk's orange

## Developing

```
bundle exec jekyll serve
```

## Optimize images

```
brew update
brew install imageoptim-cli
imageoptim --imagealpha '**/*.png'
imageoptim '**/*.jpg' '**/*.jpeg'
```

## Example post

```md
---
layout: post
title:  "Inception Movie"
tags: [ ehs, sports, family ]
image: assets/images/11.jpg
description: "My review of Inception movie. Actors, directing and more."
beforetoc: "Prism highlighter is a very powerful thing. In this article I'm going to show you what you can actually do with it, some tricks and tips while editing your post. Tocs is also enabled as you can see in summary."
toc: true
# # rating: 4.5
```

text

Image with caption:

{% include image.html file="kruispunt-2.jpeg" caption="Permanente staat van onze keuken..." %}

## Todo

- import from medium
- import from tumblr
- link to linkedin, twitter, etc?
