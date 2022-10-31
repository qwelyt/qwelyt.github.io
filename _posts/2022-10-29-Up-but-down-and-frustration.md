---
layout: post
title: Up! But down. And frustration
tags: couscous pcb seeed
---
I have a working rust environment and can finally actually flash my board.

So I finally got the time to actually start coding the thing. And the first thing to do before coding is setting up your environment. Bugger me this is not the easiest when using a new mcu, a language you are not used to, and wanting to do things yourself.

I had a lot of problems just trying to get a blinky working (still can't!). Let alone actually starting to get a keyboard working. But at least now I can actually start coding for the thing. I am fortunate enough to frequent the same discord server as another user that has coded a keyboard using rust, and on a rp2040! A pico was used in that case, but just swap the crate and fix the pins and you are good to go.

So anyway. I tried to get the [seeeduino-xiao-rp2040](https://github.com/rp-rs/rp-hal/tree/main/boards/seeeduino-xiao-rp2040) blinky example. I can build that project when cloning the code, but not when I copy the code to my project. That's annoying indeed. I think that repo would benefit from having examples in different projects. That way a user has a much easier time getting up and running.

So what about that other one with a rp2040-project? You can find that one [here](https://github.com/dnaq/srt400-pico). dnaq is really helpful for us not as bright individuals. I've gotten lots of help before when I did AoC in rust. dnaq really helped getting runnable rust-code.

I cloned dnaqs code and just swapped the mcu-crate out to the seeeduino one, and that seems to work without issue!

Now I just need to get something working. I created a simple blinky but that didn't work. Once again dnaq to the rescue with suggestions on how to fix them. I had a big scare that I managed to brick one of my boards last night. I flashed my firmware, went outside, came back, and it did't work. *"Okay, fine, lets just flash a new version*. Except, now the board is not found in `lsusb` anymore. Nothing I do seems to work. Turns out writing code an 2AM is a stupid idea. I, in all likelihood, mistook the R and B button. Sleepy and reading text for ants is not a great combo. Tried it again this night (with tips from dnaq) and it showed up in `lsusb` ready to be mounted and flashed.

My first task is to get blinky working. Then I can start looking at how to code them.

Or actually, I think my first task right now is "Go to sleep you dumdum" as I stayed up waaaay to late last night and its soon midnight. But progress **has** been made! I can flash the board! I can run code on it (I think). We'll see how long it takes to actually code this. I have thoughts about writing it all in an arduino-sketch and then porting that to Rust. Or I can allow dnaq too guide me and do it correctly the first time.


Sorry about any spelling mistake. I'm almost falling asleep in front of my screen.


// This post had *a lot* of spelling mistakes and have since been corrected. Pro-tip: Don't try to code or write posts when you are half asleep. -- qwelyt 2022-10-31
