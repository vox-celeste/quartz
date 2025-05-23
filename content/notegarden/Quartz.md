---
title: Quartz
draft: false
tags:
  - pkm
---
Quartz is a [[static site generator]] written by Jacky Zhao that builds a website out of an [[Obsidian MD]] database. It's particularly suited for [[digital garden|digital gardening]] and personal knowledge bases.

There are so many SSGs out there, pretty much all of which can work as digital gardens, but I chose Quartz (after [[tools that don't work for me|futzing around]] with many others…) because it’s designed to let you use Obsidian as a frictionless CMS, while offering more customizability (and less of a price tag) than Obsidian’s Publish offering. I really like being able to work with plain .md files within a powerful editor that I can customize and make visually appealing. I don’t like writing in ugly programs. Note-taking can be tedious; I need a carrot on the proverbial stick.

So far my experience with Quartz has been mostly positive, though I echo these sentiments (keeping in mind as well my past experiences trying to get Hugo to work for me):

> *there is this huge disconnect to me with SSG's. I come to them to get away from the complexity. The promise of using simple markdown, devolves pretty quickly into doing MORE work up front to learn the inner workings of some open source project to do "development" to work around deficiencies. […] IMO an SSG is really only as good as the base core features and styling easy path work for your needs; unless you are willing to be a developer.* ([Witch Doctor](https://witchdoctor.com/webdevelopment/quartz-ssg-with-obsidian.html))

I continue to entertain interest in setting up a [Kiki](https://tomo-dashi.itch.io/kiki) instance, though I’m unsure whether it would be a good fit for this specific project.

***

See the official [documentation](https://quartz.jzhao.xyz) for how to start your own Quartz instance. You will need a hosting provider. This site is being served via Github Pages. I may self-host in the future.

NTS: `npx quartz sync` will push changes to this site.

Resources that have helped me:

* [Obsidian and Quartz for Static Site Generation - Witch Doctor](https://witchdoctor.com/webdevelopment/quartz-ssg-with-obsidian.html)
* [This tutorial video](https://www.youtube.com/watch?v=6s6DT1yN4dw) by Nicole van der Hoeven. I followed this tutorial pretty much exactly for my initial setup but would like to make some changes now that I have a better understanding of how it all works.

## to-do

* Change the Obsidian vault itself to contain just the content folder, not the entire Quartz directory. (BACK CONTENT UP FIRST)
* Figure out what’s causing my links to appear broken on the SSG (many of those links work fine in Obsidian)
* Minor visual customization (favicon, colours)
* Figure out wtf the issues are with my front matter
