---
title: "Your First Multicloud Environment"
date: 2020-05-03T12:10:37-04:00
subtitle: ""
tags: ["static website", "hugo", "s3", "cloudflare"]
thumbnail: "/images/container.jpeg"
readtime: "10 min"
published: false
---

## Objective
The goal of this post is to set up a personal static website that's cheap, scalable, and easy to set up using S3 and Cloudflare.

## Motivation
I saw [this post](https://hampton.pw/posts/shrinking-this-sites-docker-image/) on Hacker News and read a bunch of comments about how engineers love to over engineer things or adding complexity where it doesn't need to be. Reading these comments inspired me to share how my own blog is set up.  

The three main pieces of technology used to power this blog are:
1. [Hugo](https://gohugo.io/) to generate the static files
2. [S3](https://aws.amazon.com/s3/) to store the static files
3. [Cloudflare](https://cloudflare.com) to serve as my DNS and CDN provider.

Together these three things cost me at most $0.02/month in total hosting costs and I never worry about servers or downtime.
{{< figure src="/hosting_costs.png" alt="krishamoud.me hosting costs" width="100%" >}}

## Prerequisites
This post assumes the following:
1. You've [installed hugo locally](https://gohugo.io/getting-started/installing)
2. You have an [AWS account](https://aws.amazon.com/)
3. You have [npm](https://www.npmjs.com/) installed
4. You have the [AWS cli installed](https://aws.amazon.com/cli/)
5. You have $0.02/month to spend on hosting

## Step 1. Create a Hugo Site
I own the domain https://kris.sexy because I'm childish and had the spare money to buy it.  I still haven't done anything with it so I'll create a hugo site for that domain.

Typing this command into your terminal will generate a new hugo site in your current directory.
```bash
⇒  hugo new site kris.sexy
```

Create a new post
```bash
⇒  hugo new posts/hello-world.md
```

You can see your new site
