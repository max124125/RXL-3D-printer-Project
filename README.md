**RXL (Rigid XL) 3D printer Project**



<p float="left">
  <img src="https://github.com/user-attachments/assets/db2507a0-97f1-4131-9a4e-040b31bc373f" width="420" />
  <img src="https://github.com/user-attachments/assets/8f677c62-449a-4d4f-bc55-940c2a2fa10f" width="350" /> 
</p>

What is the project:
To build a large format (350mm x 350mm x 410mm), enclosed, high speed, easily modable, 3D printer.

Justifications:
My current printers are a modified Ender 3 and a Voron 0.1 (Tiny-M Configuration).
With these printers I find that printing any large scale parts is impossible, many times my voron 0.1 has been too small to print a part, and then the slicing on the ender-3 gives a print time that is frustratingly long (and then will have subpar print quality anyway).
Additionally, the ender 3 build volume is good, but even this has been too small on several occasions (and unenclosed, when I wished to print ABS, or other enclosure based materials).

Design Goals:
 - Build Volume of 350mm x 350mm x 410mm, with room to move hotend over nozzle cleaner + purge shoot (similar to Bambu labs) and potentially other future features (tool changer area?).
 - Input shaper results of around 50K or above for both axes.
 - Travel speeds of over 700mm/s and general printing accels (at least) double that of the X1C(20k travel, 10k outer wall, etc.)
 - ABSOLUTE RELIABILITY (perfect first layers, minimal print artificats, rare failed prints, etc. (at least on par or better than the X1C).

Future features: 
 - Built-in side panel AMS
 - Tool changer


Inspirations for this project:  
-VzBot  
-Voron Trident  
-Monolith Gantry Mod (For Voron Trident & 2.4)  
-RatRig V-Core 4  

Frame Justifications:
By using 2040 braces (in the horizontal configuration) the misumi data shows that this is ~7x more rigid than a single 2020 yet only adds an additional 40mm in x and y for the frame. Additionally, 4040 extrusions in the corners of the printer are ~12x more rigid than a single 2020, and when paired with the horizontal 2040's adds no additional size to the printer.

Furthurmore, people had expressed issues in input shaper with taller Voron configurations, and as I wanted this printer to reach between 400-450mm, 4040 corners and 2040 cross braces were decided upon to stay on the conservative side.

Misumi data:
https://us.misumi-ec.com/pdf/fa/2010/p2433.pdf


Motion system choice justification:
A detailed breakdown of the choice is found in the "design justifications file". 
However, it sums down to the fact that the AWD CoreXY system has been well tested (VzBot, AWD Voron Mod, etc.), proven to work at ridiculous speeds (see VeZ3D's channel) even at larger build volumes (e.g. VzBot 330), and be of a simpler design than other systems (e.g. Hybrid Corexy).


Motion system update.   
<img src="https://github.com/user-attachments/assets/5099330e-b0f2-433d-8a4b-6bfe8298d6b4" width="500" />

Electronics system update.   
<img src="https://github.com/user-attachments/assets/15b6d163-4cd9-41d7-9158-ccc922d62c64" width="400" />


--------------------------------------------------------------------------------------------------------------------------------------
SPEED TRIALS: 

A large goal of this printer is to replace my ender 3. As such it is being used for the baseline speed test as the RXL is tested. 
The desired speed is to be sub 20mins for the benchy at good quality.
Other print settings (such as minimum layer time) will also be changed and this will be reflected in the quality rating and benchy time. 

Additional Notes on prints:  
Filament: Bambu labs PETG HF  
Tuning is done to increase quality and speed, but maintain other key attributes such as strength (i.e. 3 walls even when 1 would technically work and be much faster)

Printer heating and prepare time also will not be included. However, It is such for each printer when printing PETG Hf from bambu labs:  
Ender 3: [Heat time 3:50] [Prep time 20s].  
X1C: [Heat time 1:30] [Prep time 5m46s].  
RXL: [Heat time: 3:10] [Prep time 2m30s].  

|  Printer & Trial   | top Accel [mm/s2] | top speed [mm/s] | Motor Current [a] |  Benchy Time  |  Layer height   |    Rating    |     Notes    |
|       :-----:        |       :---:      |       :---:      |       :---:        |     :---:     |    :---:    |    :---:    |     :---:    |    
|    `Ender3 [NA]`  |        500       |        50        |        0.6         |     `2h2m`      |     0.2     |    `7.5/10`  |    Good quality, bad first layer and struggles with steep overhangs |
|     RXL [1]        |       1,500      |        175       |        0.5         |     59m42s    |     0.2     |   3.5/10   |  Slight layer shifting during diagonal travel moves, slight ringing, bad stringing, but otherwise an ok first ever print|
|      RXL [2]       |       **3,000**      |        **155**       |       **0.8**         |     52m32s    |     0.2     |    4.0/10  | Ok print, slight ringing, smoothing factor far too high, small blots on surface of print, stringing
|      RXL [3]       |       3,000      |        155       |       0.8         |     52m32s    |     0.2     |    5.0/10  | Decent print, bad stringing, slight surface defects, but much overall improved
|      `X1C [NA]`      |      10,000      |        500       |       1.2         |     `43m46s`    |     0.24     |   `8.5/10`  | Default config, good quality
|      RXL [4]       |       **4,000**      |        **185**       |       0.8         |     41m30s    |     **0.24**     |    6.5/10  | Switched to Orbiter, and changed filaments. Stringing and other surface defect massively improved, same with overhangs. Other slicer optomizations
|      RXL [5]       |       4,000      |        185       |       0.8         |     41m30s     |    0.24     |    7.5/10  | Tuning done for: Pressure advance, temperature, accel, etc. Only slight issue is top layer and very mild stringing
|      RXL [6]       |       4,000      |        225       |       0.8         |     36m48s     |    0.24     |    7.25/10  | With higher speeds, new issues on top layers and ringing
|      RXL [7]       |       4,000      |        225       |       0.8         |     ______    |    0.24     |    ___/10  | Input shaper tuned + nozzle wiper added

Current reliability/setup issues:   
-First layer height (Offset is tuned, however klicky probe results will sometimes vary, so new/more rigid setup needs to be tested)    
-Hotend wires interfere with belts and Klicky probe (solved, refined wire harness still needed though)  
-Z-axis belt holders are bending and can break (Front ones redesigned and much more rigid now, rear partialy rebuilt but still an issue)  
-No screen to help monitor printer (screen does not turn on, furthur testing needed)     
-Camera to view prints (Camera does not seem to work, more testing needed      
-Nozzle Cleaner and purge (All parts arrived, first iterations soon to be printed

