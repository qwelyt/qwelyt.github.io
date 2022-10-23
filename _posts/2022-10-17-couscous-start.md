---
layout: post
title: couscous delivery!
tags: couscous pcb seeed
---
Got my board from Seeed Fusion today! Very excited to get started.

So, what is this? Well, Seeed Fusion had a competition. "Design a mechanical keyboard using ou Seeed XIAO mcu as the brains and we produce it for free, with all components." That's a radical way to market yourself. So I did what any DIYer would do. I learnt KiCAD and designed a board.

And now my boards have arrived! I can finally start working on them to get them operational.

An unfortunate part on my end is that I took to long to actually send in my design so some components are missing from my boards. I designed an analogue backlight circuit using 5v and GND. You control the RGBA channels using potentiometers and each channel has a SPST switch so you can turn that colour on or off. But Seeed Fusion didn't have neither the pots or the LEDs I needed at their place so they would have to order from overseas. And since I was late in my entry they wouldn't get their parts before the competition ended. So I removed those from the BOM and thought that I could perhaps fix those myself.  
Well, now that I have the boards that might not be so easy. The pots sure, those are just standard THT parts. Easypeasy. The LEDs though ... SMD things are small and might be quite hard to get right.

I will wait a bit on ordering the parts I need for backlight and just try to get the board up and running. My plan is to code the thing in Rust. I picked the XIAO rp2040 with this in mind. The rp2040 seems to have good support in Rust, and there is even a HAL just for the XIAO. Sweet!

Oh, and holy smokes those LEDs on the XIAO are bright. I thought I would be able to have the mcu on full display but if I can't turn the brightness of those LEDs down I will have to be covered up.

Some pics of the board
![Picture of two populated PCBs](https://media.discordapp.net/attachments/451377963863244811/1031503227444789338/PXL_20221017_094349441.jpg "couscous pcbs")  
![Close up of diodes](https://media.discordapp.net/attachments/451377963863244811/1031503337432039444/PXL_20221017_094405275.MP.jpg "Diodes not placed super neatly")
![Close up of backside, one switch leg missing solder](https://media.discordapp.net/attachments/451377963863244811/1031503337708859452/PXL_20221017_094435636.MP.jpg "Missing solder on SW36")

Some mistakes on the boards. Each of them has a switch leg that is not soldered. And the diodes could have been done neater. But aside from those I have no complaints!