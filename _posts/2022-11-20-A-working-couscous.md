---
layout: post
title: A working couscous!
tags: couscous pcb seeed
---
And now a working couscous!

# Summary
![Working couscous](https://i.imgur.com/paZgc9f.jpg)

Unfortunately I did a screw up with the switches for the LEDs. I selected SPST-NO instead of SPST-toggle. This means that the LEDs won't work unless I bridge them. Due to this I have not bothered getting the LED modules or the potentiometers for the LEDs. But the idea works!

Anyhow, the actual keyboard. Works! A few bugs, as there always are, but working. Every key works, I have no problem typing on it (doing it now!). Source code over at https://github.com/qwelyt/couscous

# Code
This is the first time I actually wrote Rust code for anything real. I did last years Advent of Code in Rust which made me want to use it. And now I've written a keyboards firmware in it! That is pretty awesome to me. I will for sure prefer Rust over C when writing more things.

The most interesting thing to me is how many keys you can fit on so few pins. There 11 pins used. And there are 60 keys. Just by being a bit clever with how you design and scan the matrix you can get in a whole lotta keys.

There are still a few things that are strange in the code. I have ghosting for some keys, but on a row below it it does not exhibit the same behavior. So odd. I am guessing it is due to switching pin states in an odd fashion. The current implementation is very naïve. Writing a better way is high on my todo-list.

I also don't have all the keys mapped yet. I still have one key totally unmapped, which means I have a layer key and therefore 59 more keys to use! I have no worries about fitting everything I need on this board. And if I do find that not to my liking, I can always map keys differently and get even more options.

# Hardware
Well, firstly, the LED switches. HUGH miss on my part. NO-switches are no good in this case. So that's a bit of a bummer. But it's not vital to the keyboard so I'm not too worried about it. Would have been fun though.

It's quite wide. I should have done it a bit smaller. Maybe have the switches as close together as the pots. Mounting holes are fine. Have not printed a case for it but I'm thinking about that. It works great without on, but it can be nice. Easier for transportation if it has one.

# Conclusion
This was fun! Really enjoyed it. Never played with KiCAD, never use Rust for anything. But I will for sure do in the future.

Huge shout out to SeeedStuio for making this happen! It has, for me, really shown the viability of the Seeed. If I need to build PCBs in the future I will for sure keep SeeedStudio in mind. Fast response, easy to upload files etc etc. They were fast.