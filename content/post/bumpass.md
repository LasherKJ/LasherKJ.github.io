---
title: "Bumpass"
description: "The simplest navigation aid possible"
date: "2019-02-28"
aliases: ["about-us", "about-hugo", "contact"]
author: "Kevin Lasher"
draft: false
---


# The Bumpass - the simplest navigational device

The core idea of the Bumpass is also where the idea for the name came from: it's a bad compass. I wanted to make a navigation device as simple as possible while still being usefull. Across all iterations the story is the same: pick a destination and the Bumpass points you to it. Where a compass points north, the bumpass points to where you want to be. There is no map, there is no turn-by-turn, or traffic reports. It literally just points you in the right direction and the rest is up to you.

The Bumpass takes your location in latitude and longitude, and heading and compares that to the latitude and longitude of your destination. What it returns to you is a direction and distance left to travel. The distance and direction are calculated using the [Haversine Formula](https://en.wikipedia.org/wiki/Haversine_formula). 

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

Version 0 was a Raspberry Pi Zero with a GPS module that ran a python script. Tha script constantly took in data from the GPS module to get the device location and heading and compared it to a hardcoded coordinate. Using the Haversine formula it would return a distance and direction. The device was contained in a cardboard box with a plexiglass lid to protect the e-ink screen from UV damage. The device was powered by an external battery bank, when it was plugged in it would run the python script as soon as it booted, and when the device was within 10 feet of the hardcoded coordinates it would power down.

The largest stumbling block was that I had no way to set a latitude and longitude from the device. My only idea was to pass the information from my iPhone to the Raspberry Pi over bluetooth. In order to accomplish that I would need to manage the bluetooth from Raspbian and pass that my python script, and then create an interface on the iPhone somehow. For the time being, I had a cardboard box that pointed to my favorite mexican restaurant.

## Version 1

![Bumpass 1](/images/bumpass1.JPG)
**Specs**
| &nbsp;&nbsp;&nbsp;&nbsp; | &nbsp; |
| ------ | ------|
| hardware: | Raspberry Pi Zero |
| &nbsp; | Adafruit GPS module |
| &nbsp; | waveshare e-ink screen|
| &nbsp; | 3D printed case |
| &nbsp; | plexiglass |
| Languages: | Python |

Version 1 had two major updates: a dedicated case and a way to set the destination coordinates. The case was designed with [tinkerCAD](https://www.tinkercad.com/) and printed on an Ender 3 printer. 

In order to set the coordinates I skirted around using bluetooth by making a wildly inefficient system. I created the a single page website hosted on a google cloud server. The website was a google maps API where I could long-press on the map to set a destination. This would save the coordinates onto a text file on the server. When the python script started it would connect to my iPhone as a hotspot and navigate to https://\[ip\]/location to get the destination. 

## Version 2

**Specs**
| &nbsp;&nbsp;&nbsp;&nbsp; | &nbsp; |
| ------ | ------|
| hardware: | iPhone |
| Languages: | React Native |
| |Express|

Versions 0 and 1 had two major issues: hardware and scalability. With no built in power source, and no direct input, the bumpass was pretty unwieldy. On top of that, my system for setting the coordinates literally only worked for a userbase of one. If anyone else used my single page website it would overwrite the coordinates I set for myself. And using my phone as a hotspot to provide internet to the device drained my battery. 

In order to get around these issues, the entire system was translated to React Native and moved onto the iPhone. The Express library allowed for access to the users location and orientation. The google maps API was now built right into the app, so there was no need to navigate to a seperate website. 