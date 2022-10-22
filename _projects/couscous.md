---
layout: project
title: couscous
tag_name: couscous
repo: https://github.com/qwelyt/couscous
---
couscous is a keyboard using the Seeed XIAO rp2040 micro controller. It has 60 keys in a 5x6  duplex matrix. It is a mono-split design with skews halves.

The project started when Seeed Fusion held their mechanical keyboard competition ([https://www.seeedstudio.com/seeed-fusion-diy-xiao-mechanical-keyboard-contest.html](https://www.seeedstudio.com/seeed-fusion-diy-xiao-mechanical-keyboard-contest.html)) and I thought "hey, why not".

My goal was to push this tiny little mcu board to the max. I wanted to show that just because it has a tiny footprint it doesn't mean you can't build big projects with it.

Now, the mcu has 11 pins I (you might be able to use more, but *I* am not good enough for that) can use for the matrix. 11 pins means a 5x6 matrix to get the max number of pins. That's 30 keys. And couscous has 60 keys. How? Enter the Duplex Matrix. If you reverse the polarity of the pins when you scan for changes, you get *double* the amount of possible pins. 5x6x2. Read more about the (real) duplex matrix here [https://kbd.news/The-Japanese-duplex-matrix-1391.html](https://kbd.news/The-Japanese-duplex-matrix-1391.html)
