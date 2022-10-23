---
layout: project
title: docker-stuff
tag: docker
repo: https://github.com/qwelyt/docker-stuff
---
Run everything in docker

Abusing software is always fun. To get used to using docker I created this repo. I just wanted to learn how to use docker. Then I saw a talk by Jess Frazelle (https://github.com/jessfraz) about running X application in docker. So of course I had to try that. For some reason I couldn't get her containers to run the way I wanted, so I did my own. And here we are.

This repo also made me realize that I can use GitHub Actions to do things for me. Before I built all the images locally on my computer. Then I had a image that did't finish in 48h (cq-editor). Now, that is a tad long for me to have to wait before I can use my computer for something else. This prompted the migration to using GitHub Actions. And now all images can be built with them and they are published to DockerHub for easy fetching.

There is really no reason for doing this. Kinda. It's easier going back in time with versions and all that, but other than that really, it is just making life more complicated for yourself. That won't stop me from keep doing it though ...