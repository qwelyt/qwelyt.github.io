---
layout: post
title: Working duplex matrix!
tags: couscous pcb seeed
---
A working POC of my duplex matrix! In rust!

Wooooo! I *just* got this working. But it **wooorks**! It's a really simple test really. I make use of the neopixel that is on the xiao to make it easier for me to test. Lots of colours in the same led so simple to get lots of data into it.

Full code can be found here https://github.com/qwelyt/couscous/blob/e6329efceba72f70873f93c6cf267ccd8ebec83e/firmware/couscous/src/main.rs

The thing is actually really simple.
```rs
loop {
        pin5.into_pull_down_input();
        pin6.into_push_pull_output();
        pin6.set_high().unwrap();

        let blu = pin5.is_high().unwrap();
        pin6.set_low().unwrap();

        pin6.into_pull_down_input();
        pin5.into_push_pull_output();
        pin5.set_high().unwrap();
        let gre = pin6.is_high().unwrap();
        pin5.set_low().unwrap();


        if blu && gre {
            ws.write(brightness(once(wheel(192)), 32)).unwrap();
        } else if blu {
            ws.write(brightness(once(wheel(128)), 32)).unwrap();
        } else if gre {
            ws.write(brightness(once(wheel(64)), 32)).unwrap();
        } else {
            ws.write(brightness(once(wheel(255)), 32)).unwrap();
        }
        delay.delay_ms(200);
    }
```
As you can see, pin5 and pin6 scan in one direction first, and in the other direction right after. And based on that we change colour of the neopixel (`ws`). 

Super exited about this actually. It means that what I want to do *is* possible. 60 keys on 11 pins. That kind of blows me away. The next step is either to code the full matrix scanning, or moving this example to `rtic`. Using real time interrupts can be nicer going forward, but I've always beaten my own path before. We'll see. Very nice to see it actually working.

![Nothing pressed](https://i.imgur.com/HpuY52I.png)
![sw1 pressed](https://i.imgur.com/TR3HFmB.png)
![sw2 pressed](https://i.imgur.com/oI7LIqd.png)
![sw1 and sw2 pressed](https://i.imgur.com/q4gyV9e.png)
