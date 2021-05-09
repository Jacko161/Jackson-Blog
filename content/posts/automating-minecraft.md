---
title: "Creating a Minecraft Server using Terraform"
date: 2021-05-09T10:55:37+10:00
tags: ["software-engineering", "automation", "blogging"]
categories: ["software-engineering", "automation", "blogging"]
draft: false
---

So once or twice a year my group of friends and I get the hankering to spin up a Minecraft server so we can play, when that happens we have a few options:
1. Pay for realms, it's pretty cheap and actually not a bad deal. But it's fire and forget, which is kinda boring.
2. Run the server on someone's computer, but when they leave they either need to leave the server running or we gotta stop playing.
3. Spin up an instance on a cloud provider and spin the server on that.


Usually we go with option 2 or 3, but over the weekend I started feeling the inkling to play again, so I decided to automated option 3 so I don't need to do as much next time. See https://github.com/Jacko161/minecraft-bootstrap

## How does it work?

The bootstrap project uses Terraform to create and manage some EC2 infrastructure, it will spin up an instance, create some security groups to allow traffic to the server and allow https egress (so we can install packages on the box). 

During the Terraform job we copy the boostrap-server.sh script over to the box and execute it, it will pull the required media, create the service and a service user and start the server, couldn't be easier!

## What's next?

The scripts need a little more work to handle automated backups of the world, shouldn't be too hard just need to archive the world data and push it to an S3 bucket so we can get to it later.
