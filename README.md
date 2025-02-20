**RXL (Rigid XL) 3D printer Project**

What is the project:
To build a large format (350mm x 350mm x 450mm), enclosed, high speed, easily modable, 3D printer.

Justifications:
My current printers are a modified Ender 3 and a Voron 0.1 (Tiny-M Configuration).
With these printers I find that printing any large scale parts is impossible, many times my voron 0.1 has been too small to print a part, and then the slicing on the ender-3 gives a print time that is frustratingly long (and then will have subpar print quality anyway).
Additionally, the ender 3 build volume is good, but even this has been too small on several occasions (and unenclosed, on the rare case I needed to print ABS).

Design Goals:
 - Build Volume of 350mm x 350mm x 450mm, with room to move hotend over nozzle cleaner + purge shoot (similar to Bambu labs) and potentially other future features (tool changer area?).
 - Input shaper results of around 50K or above for both axes.
 - Travel speeds of over 700mm/s and general printing accels (at least) double that of the X1C(20k travel, 10k outer wall, etc.)
 - ABSOLUTE RELIABILITY (perfect first layers, minimal print artificats, rare failed prints, etc. (at least on par or better than the X1C).

Inspirations for this project:
-VzBot
-Voron Trident
-Monolith Gantry Mod (For Voron Trident & 2.4)
-RatRig V-Core 4

Frame Justifications:

https://us.misumi-ec.com/pdf/fa/2010/p2433.pdf
..... (to do)

Motion system choice justification:

Bed slinger (eg. Cr-10 [Max]): With bed slingers, speed becomes a major issue as their build volume increases. 
With a 350mm bed (especially a 3/8" MIC6 one or glass) the motors will have to accelerate far more weight around compared to any of the other motion systems mentioned here. 
Additionally, with taller parts that have thin walls (wich I will print quite a bit), Z-wobble becomes a major issues, and speeds will have to be signifgantly reduced at higher z heights.
Lastly, this design is also the least efficient in terms of space taken up, and will become majorly impractile to enclose, compared to other designs.

Cross Gantry (eg. Annex K3): This system is very rigid and has alot of good features, however, I believe it flourishes at smaller build volumes. With a 350mm bed the 4 motors will have 
to move 2 400mm long linear rails along with there 450mm suppports as opposed to the 1 linear rail and support needed in a corexy system. This could be counteracted by using the 8 motor setup, but thats very expensive, and I don't want to. 
Additionally, this system has one major feature I dislike, wich is the limited accessibility to the print head and print bed. As opposed to other designs (like the Voron 0) this design sourrounds the print head and bed (at z=0) 
making viewing of the print difficult, along with making hotend or nozzle changes far more annoying. And having worked on printers that have this limited accesibility, this was a major point against for this motion system.

Hybrid Corexy: (eg. V-Core 4 HYBRID) This system showed the most promise for my use case, and was a close contender for first position. The choice against it is mainly due to the added complexity to setup and run. 
An additional set of belts and idlers adds more moving mass, but also becomes much harder to tension and sync. 
If all 4 belts and motors are not tensioned and synced perfectly at all times, print artificates and random step losses can occur (the occasional step loss being due 
to the 4 belt tensioning issue is not confirmed, but I believe highly likely, see 247 Printing video on V-core 4 speed testing) 
Additionally, this system may be more of a benefit for even larger scale printers (>500mm) where the x axis gantry signifigantly outweighs the print head, (wich is not the case for my design, Hotend: 380g? X-axis 350g?)  

AWD Corexy (eg. VZbot): This system has been much more thouroughly tested due to it being a common upgrade in the Voron, VzBot, and RatRig printer family's. 
I also was very much inspiried by the Monolith gantry for this system, as it had a lot of the features I was looking at: the simplified motion system to use very minimal idlers, a majorly shortened belt length, double sheer bearings, 
and it reduces moments as much as arguably possible in a corexy system.
Additionally, I had seen other AWD systems (mainly the VzBot 330) hit ludicrous speeds, accels and input shaper graphs, even with its larger bed sizes. 
As such, I was confident in the abilities of this motion system, and it is the chossen one for this project.

Polar (Polar-3D):
No

Scara/Markforge/etc.
I don't believe these systems are at all built for speed.
Additionally, they are niche enough that I wouldn't have the community support for help and reasearch that other systems do.


