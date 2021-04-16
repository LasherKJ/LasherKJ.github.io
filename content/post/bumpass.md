---
title: "Bumpass"
description: "The simplest navigation aid possible"
date: "2019-02-28"
aliases: ["about-us", "about-hugo", "contact"]
author: "Kevin Lasher"
draft: false
---


# The Bumpass - the simplest navigational device

The core idea of the Bumpass is also where the idea for the name came from: it's a bad compass. I wanted to make a navigation device as simple as possible while still being usefull. Across all iterations the story is the same: pick a destination and the bumpass points you to it. Where a compass points north, the bumpass points to where you want to be. There is no map, there is no turn-by-turn, or traffic reports. It literally just points you in the right direction and the rest is up to you.

The bumpass takes your location in latitude and longitude, and heading and compares that to the latitude and longitude of your destination. What it returns to you is a direction and distance left to travel. 

## History

The Bumpass was born out of what we called a "Top Gear Special" at one of my previous jobs. Our boss was going on vacation and we had no projects coming down the pipeline. Our boss didn't want to: A) pay us to do nothing while she went on vacation, B) force us all to take a vacation at the same time. So instead we were all given a small budget and told we had two weeks to learn a new skill and build something. Much like BBC's "Top Gear", these were goofy, slapdash projects thrown together quickly and then just as quickly shelved.

Except I kept coming back to the Bumpass. Every year or so when I had a little more free time than usual I would pick it up and it would morph into a new form, but never quite reaching what I would call a finished state

## Version 0 

![Bumpass 0](/images/bumpass0.JPG)
**Specs**
| &nbsp;&nbsp;&nbsp;&nbsp; | &nbsp; |
| ------ | ------|
| hardware: | Raspberry Pi Zero |
| &nbsp; | Adafruit GPS module |
| &nbsp; | waveshare e-ink screen|
| &nbsp; | cardboard & plexiglass |
| Languages: | Python |


The very first form of the Bumpass was a rush job. Any time I had a bug that was just outside my reach or couldn't come up with a way to implement a solution it was set easiest to just ignore it. I only had two weeks and this was more about trying new things than making a finished project. 

The first problem was trigonometry. Well actually the problem was me and that I'm bad at trigonometry. 
