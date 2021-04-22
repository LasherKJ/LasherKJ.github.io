---
title: "Nobrolla API Documentation"
description: "Documentation for the Nobrolla Video API"
date: "2021-04-22"
aliases: ["API", "Documentation", "Nobrolla"]
author: "Kevin Lasher"
draft: false
---

![ScreenShot](/images/nobrollaDocs/screenShot.png)


One of our projects in development at Nobrolla Video was an artificial intelligence based video processing / monitoring system. We planned for two different models: one being a server located on-site and the other being a cloud-hosted SaaS. In order to minimize code sets, both would be reached through the same RESTful API, the only difference from an engineering perspective was the endpoint. 

I was tasked with writing the documentation for our API, and in the process help shape it. Through creating the documentation and tutorials for use-cases I was able to find where we had missing features, inconsistencies, etc. 

## Developing the documentation

The website was written in [Hugo](https://gohugo.io/) (Like this one is), because I was searching for a quick way to get a text-heavy website off the ground. Hugo content is really just markdown, so it was easy enough to get started.

## Hosting the website 

For the time being [docs.nobrolla.com](https://docs.nobrolla.com) is still up. It is hosted on [Aerobatic](https://www.aerobatic.com/), a command-line tool and hosting service. The source code was hosted on bitbucket, and using bitbucket pipelines any commits to the master branch triggered aerobatic-cli commands and updated the production website.

## Source Code

The source code has been migrated to my [personal github](https://github.com/LasherKJ/Nobrolla_Documentation) as the project has been shuttered.

