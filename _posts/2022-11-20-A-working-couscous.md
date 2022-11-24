---
layout: post
title: A working couscous!
tags: couscous pcb seeed
---
And now a working couscous!

# Summary
![Working couscous](https://i.imgur.com/paZgc9f.jpg)

Unfortunately I did a screw up with the switches for the LEDs. I selected SPST-NO instead of SPST-toggle. This means that the LEDs won't work unless I bridge them. Due to this I have not bothered getting the LED modules or the potentiometers for the LEDs. But the idea works!

Anyhow, the actual keyboard. Works! A few bugs, as there always are, but working. Every key works, I have no problem typing on it (doing it now!). Source code over at [https://github.com/qwelyt/couscous](https://github.com/qwelyt/couscous)

# Software
This is the first time I actually wrote Rust code for anything real. I did last years Advent of Code in Rust which made me want to use it. And now I've written a keyboards firmware in it! That is pretty awesome to me. I will for sure prefer Rust over C when writing more things.

The most interesting thing to me is how many keys you can fit on so few pins. There 11 pins used. And there are 60 keys. Just by being a bit clever with how you design and scan the matrix you can get in a whole lotta keys.

There are still a few things that are strange in the code. I have ghosting for some keys, but on a row below it it does not exhibit the same behavior. So odd. I am guessing it is due to switching pin states in an odd fashion. The current implementation is very naïve. Writing a better way is high on my todo-list.

I also don't have all the keys mapped yet. I still have one key totally unmapped, which means I have a layer key and therefore 59 more keys to use! I have no worries about fitting everything I need on this board. And if I do find that not to my liking, I can always map keys differently and get even more options.

# Hardware
Well, firstly, the LED switches. HUGH miss on my part. NO-switches are no good in this case. So that's a bit of a bummer. But it's not vital to the keyboard so I'm not too worried about it. Would have been fun though. Next time I will have to make sure to really read the part description. Being tired, having a million tabs open, searching for parts ... Yeah there were bound to be problems. I'm happy it was on the least critical part though. The entire board works as intended, it's just my cool backlight that is missing. Lessons learnt.

It's quite wide. I should have done it a bit smaller. Maybe have the switches as close together as the pots. Mounting holes are fine. Have not printed a case for it but I'm thinking about that. It works great without on, but it can be nice. Easier for transportation if it has one.

The seeeduino-rp2040 was super easy to work with. Well, this is perhaps mostly because I choose to work with it in rust and there is a crate that exposs everything. Never the less, I *love* the inclusion of the neopixel. I don't have a probe to debug things, but colours can make become error messages! And the neopixel can show lots and lots of colours. This is how I debugged things before I got up the USB serial debug. Worked very well for my needs so I'm happy they included that.

The seeeduino does not have a whole lot of pins. This made me sceptical at first and I thought that I would in reality have to design something much much smaller than what I did. But with the help of those that actually know electrical engineering it was easy to forgo that predjudice. Just do duplex scanning and you can build to your hearts content, basically. Small does not mean limited! I usually build small keyboards, the latest design I have i 30 keys total. Really considering a seeeduno for this as well due to the small formfactor. A whole lot easier to fit it in than a proMicro.

# Conclusion
This was fun! Really enjoyed it. Never played with KiCAD, never used Rust for anything. Never ordered a PCB. But I will for sure do in the future. It was so much easier than I thought it would be.

Huge shout out to SeeedStudio for making this happen! It has, for me, really shown the viability of the seeeduino. If I need to build PCBs in the future I will for sure keep SeeedStudio in mind. Fast response, easy to upload files etc etc. They were great all around. Turnover rate between me uploading my designs and getting a respons was about a day. I was the slow one. And quite the huge stockpile of parts as well. I happened to choose parts they didn't have though, but a quick respons about them not having it and how long it would take to ship it to them was all that was needed. I just change parts to something they had on hand and production could begin. The LEDs and potentiometers were things they didn't have at hand. So those had to be axed from my BOM files. I can always order them myself and fix. But given my mess up with the buttons it will have to be for rev2.  
The only slow part was shipping, but I can't raelly fault them for that. That is on me for living far away. :)
