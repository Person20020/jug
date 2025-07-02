---
title: "Jug"
author: "Person20020"
description: "A 6x3 column staggard split keyboard with a large thumb cluster."
created_at: "2025-05-20"
---

# Jug -- Split Keyboard

# June 20: Made KLE and printed a test plate

This project I started a while ago for hackboard, but I redid the entire thing several times and never finished. I'm restarting from scratch again and today I made an approximate keyboard layout and printed out a plate to see how the layout felt.

![image](https://hc-cdn.hel1.your-objectstorage.com/s/v3/2643e10cbda55e5d2e8c6ef37833265cd2a4edf8_2025-06-20-174422_hyprshot.png)
![image](https://hc-cdn.hel1.your-objectstorage.com/s/v3/5c6605ba4cab3cd64b7ed8c7a86b3efc1f46fb6e_2025-06-20-205038_hyprshot.png)

When I was making it for hackboard I had originally thought I would make a 4x6 board with a medium sized thumb cluster (4 keys and changed to 5 later) but I'm now going to make it with 6 thumb keys and the main part will be 3x6 instead. 

The first plate I printed as a test (from hackboard) looked like this (I hadn't finished the thumb cluster layout):

![image](https://hc-cdn.hel1.your-objectstorage.com/s/v3/0139f3690ddbe36f40d188fcc14e3f1750829226_pxl_20250621_083207450.jpg)

But this is the one I printed out today:

![new plate](https://hc-cdn.hel1.your-objectstorage.com/s/v3/52266f05e3fe6c224cef0ff07329d9b8bb969a0d_pxl_20250621_073441890.jpg)
![new plate](https://hc-cdn.hel1.your-objectstorage.com/s/v3/b3d44ab2918a6a452d823c06dfe4918e23875dc7_pxl_20250621_081221467.jpg)
![new plate](https://hc-cdn.hel1.your-objectstorage.com/s/v3/ab54ee7ca0a71c367f77d42eed73e16d28e3dd0d_pxl_20250621_211057485.jpg)
![new plate](https://hc-cdn.hel1.your-objectstorage.com/s/v3/c3cae31343435a0c0ffc140d2485da4101c46def_pxl_20250621_211103860.jpg)

After printing it out and looking at the layout, I also decided I won't include an encoder because it sticks up way too much. I will probably put the interconnect where the encoder is. (I was going to use 4p4c but the connectors look kind of large. Maybe USB A. I have found double sided USB A cables on aliexpress and that shouldn't be confusing because only host should have USB A so it should be clear that it is for a different purpose.)

The stagger from hte middle finger to pointer finger and ring finger to pinky finger is a bit too large so I will reduce it a bit. I also found that the farthest out key on the thumb cluster is rather hard to reach so I might remove that as well. It should make the keyboard more compact which will be nice.

Here is a comparison between the new keyboard and my Lily58:

![comparison between lily58 and jug](https://hc-cdn.hel1.your-objectstorage.com/s/v3/47cb4e23a40940c16bc155723fa8da53ee418776_pxl_20250621_212531253.jpg)

I also spent a bunch of time troubleshooting why Fusion wouldn't export and it seems like it was because my virtual machine wasn't able to fully connect to the internet because something was wrong with the DNS. I just changed it to cloudflare in Windows and it seems be fixed.

I'm not fully set on my keyboard's name but I think jug makes sense because it looks kind of like a jug/pitcher with a long spout like this:

![img of pitcher](https://hc-cdn.hel1.your-objectstorage.com/s/v3/4ea8e022e9f243995328247715630d2cc912e4f6_image.png)

**Total time spent: 5hr**


# June 28: Modified KLE + redesigned plate

Today I modified the KLE to change the key stagger, removed one thumb key, and redid the thumb row. I moved the whole thumb cluster about 1/2 keys over. I changed all of the thumb keys to be 1u (I had one key that would be 1.25 before). I also removed the spot for the encoder and made a small recess so I could put the rp2040 pro micro and see how the spacing would be.

![plate in fusion](https://hc-cdn.hel1.your-objectstorage.com/s/v3/89cf4dd681bb73c5fa6609b62379bf5b2d0f953a_2025-06-28-195927_hyprshot.png)
![printed plate on bed](https://hc-cdn.hel1.your-objectstorage.com/s/v3/a95f3ac676d22f57611a032f118cd616f272341b_pxl_20250629_052041428.jpg)
![with keycaps](https://hc-cdn.hel1.your-objectstorage.com/s/v3/661b96ce62655ccb0d784d8118e140044efd67b2_pxl_20250629_053504968.jpg)
![next to lily58](https://hc-cdn.hel1.your-objectstorage.com/s/v3/b140afafa6a3dd0455cc909937580e7521dcfd78_pxl_20250629_053500502.jpg)

I then did a test print to feel the spacing of the keys. The main part of the keyboard feels good now. The part of the thumb cluster that is under the main part of the board is pretty good but the thumb keys that are farthest out I think would be better if it was rotated more.

**Total time spent: 4hr**


# June 28-second: adjusted thumb cluster + first pcb design

I adjusted the thumb cluster by rotating the end keys more so that they are angled like the big key on the lily58. The layout feels really good now. I next started working on the pcb layout. I did the main layout but I'm not sure yet if I want to use RGB or not. I think I'll probably at least add a few leds for caps lock/num lock. I also printed out 2 1.5u keys to see how they look and I'll be using that in my design.

![new more angled thumb](https://hc-cdn.hel1.your-objectstorage.com/s/v3/89cf4dd681bb73c5fa6609b62379bf5b2d0f953a_2025-06-28-195927_hyprshot.png)

After doing the test print (the placement is good) I started working on the pcb. I made the whole pcb for the left side.

![first pcb](https://hc-cdn.hel1.your-objectstorage.com/s/v3/1d3a0bec7fdb8e6fe4cd328c2ea630da9e1a1393_image.png)

**Total time spent: 3hr**

# June 29: Made reversible footprint for plated hotswap + work on pcb

I decided I want to make the pcb reversible so I made a footprint for hotswap sockets that can also be used to solder the switches in place. It is based on the plated ScottoKeebs footprints but should work flipped as well. I also decided I won't add rgb because routing would be especially annoying with the reversible footprints taking up so much extra space.

![reversible plated hotswap footprints](https://hc-cdn.hel1.your-objectstorage.com/s/v3/d9a9f987365a7da81d42bbe5f050b490f2493385_image.png)

I also made a diode footprint with the silkscreen on both sides and the model showing on both sides.

![double sided diode](https://hc-cdn.hel1.your-objectstorage.com/s/v3/6e27afa3c5b4721d8b6da75fdd61bfc3dc759cf5_image.png)

After making the footprints I redid the pcb again. I was a bit confused about how the reversible footprint I found for the mcu works but it seems like you just solder the jumpers on the side that the mcu faces. (the side that the side of the mcu with the components faces.)

![routed pcb](https://hc-cdn.hel1.your-objectstorage.com/s/v3/a37978ee6ea85cdec7c61eac6d9ab034e80d7def_image.png)

There were some errors on the mcu footprint but I think that it is just because the jumpers have a gap between them that doesn't have solder mask and it thinks it will cause a short. I can't figure out how to get rid of the errors but it should be fine.

**Total time spent: 5hr**

# June 29: Made USB A interconnect reversible

I had forgotten that I wouldn't be able to reverse the USB A connector for the interconnect so I spent a while fixing that. I used the same method with solder jumpers as for the mcu and it was really confusing. As I understand it this should work to make rotating the connector (flipping the side of the board it is on) work.

![reversible usb schematic](https://hackclub.slack.com/archives/C016DEDUL87/p1751254254578749?thread_ts=1751254251.071539&cid=C016DEDUL87)

After figuring out that I also added holes for standoffs to pass through to support the plate.

**Total time spent: 4hr**

# July 1: Added indicator leds and worked on firmware

Today I added indicator leds. They are small 1206 smd leds so that hey can fit under the plate and diffuse through. There will be two leds per side (one red and one blue). One on each side will be an indicator for either caps lock or num lock and the other will be to indicate whether i'm in the colemak or qwerty layer.

![final pcb](https://hc-cdn.hel1.your-objectstorage.com/s/v3/27b83bfb77431ea42e1dc3f9bdc5fdb5d1429f0e_image.png)

Yesterday I was working on my case but Fusion crashed and I lost all of my progress because the internet had just gone out.

The other thing I did today was work on firmware. I did all of my layers and am almost done. I will be adding vial support later but I'll do that after finishing the basic firmware.

**Total time spent: 5hr**

# July 1: Worked on firmware + added silkscreen to pcb

I added my logo + text to show which side to solder the jumpers for the mcu. I also learned that AliExpress won't ship to me anymore so I have switched from the RP2040 Pro Micro to the RP 2040 Zero. I made a reversible footprint for the MCU since I couldn't find one online.

![reversible rp2040 zero footprint](https://hc-cdn.hel1.your-objectstorage.com/s/v3/8ab68bc7371f2f2122046717d7462f960bb29a2d_image.png)

I also worked on the firmware and finished the keyboard.json and added the indicators for which layer you are in.