9/18/23
Forked design: Adding my upgraded parts to mount a new Voron V0 OLED display controller, Raspberry Pi, and an SKR Mini E3 V3 control board to run Klipper firmware.

The SeeMeCNC Eris, released in 2016, was a ready to print out of the box mini delta printer made with injection molded parts and custom extruder hotend parts almost entirely US-made. They even sold these printers at retail stores like Microcenter! 

I loved this printer, but it had some major issues: 

    The ATMEGA2560 based Rambo Mini board with Repetier limits a delta printers speed and precision
    The HE280 based PCB on the effector used an accelerometer to detect nozzle probes for auto-calibration. It was a very advanced idea for 2016, but with modern firmware, delta-calibration techniques are way more reliable. For this mod, I have stuck with Manual Delta Calibration in Klipper and it's been super reliable for first layers. 
    The stock hotend and single 3010 fan was lacking. It used a bowden tube to a steel heatbreak (partially all metal) that attached the hotend to the effector PCB, the heater cartridge was a power resistor (about 20W), the single 3010 fan sucked air past the heatsync and it was also the part cooling with a shroud. The original print head did not have adequate heating and cooling.
    The Eris had no LCD controller. It had a light up logo on front which I think was supposed to be an addressable LED, but all the control was done through MatterControl (Matterhackers) so it wasn't really portable without a PC attached. 

Parts Needed and Instructions (links to vendors and files)

    Original SeeMeCNC Eris - I have not found these on ebay but there are a few still floating around or collecting dust on a shelf.
    BTT SKR Mini E3 V3 control board - It's about the same footprint as the Rambo Mini but has way more power and IO. A SKR Pico would work as well but the connectors are on the edge which might interfere with the case. You will also want an external microSD connector pass through one of the holes and stuck to the outside of the case, this helps flash board firmware from Klipper.
    SKR Mini Mounting Bracket - by w0nd4bra this bracket barely fits where the Rambo Mini use to slot in. I checked for clearance and marked and drilled two holes for M3x8 screws and used heat set inserts to fasten it to the shelf. You might want to use VHB tape instead. It will interfere with the corner screw bosses, you might have to sand that away. See the pictures for how I mounted it. 
    Raspberry Pi 3B or equivalent - These are still hard to get, you can also use the BTT Pi V1.2, the mount I designed will fit standard a Pi 3/4B, you will need to glue and heat insert the standoffs. It clips into the frame of the LCD mount backside. It provides a pass-through hole for the USB cable.
    Voron V0.2 Mini OLED Display Controller (designed by Timmit99)- This controller works with Klipper with a short USB cable to the Pi (I cut the micro USB side and soldered it to a dupont connector). You will need to print the Voron V0.2 display faceplate, knob, and diffuser (or hotglue like I used) using M2x10 self-tapping screws to mount into my custom Eris LCD mount. The LCD mount should slot right into the base like the original Eris logo. 
    E3D Revo Micro 12V kit - The Revo was the smallest, lightest, easiest hotend for the Eris. The top and base mount with M3x8 screws into the plastic. The Revo wires slip through the back side cut out. I initially worked with Hotends.com to come up with a custom mount for their J-head Farmer hotend but it was too heavy. The E3D Revo comes with a 5V fan which needs a step-down converter I just soldered into the existing whip fan connections. The current design you will need to sand down the fan shroud to not interfere with the 3010 blowers (see picture). I would also highly recommend using capricorn XS tube to reduce the long bowden issues like retraction, I can get away with 4mm retractions with this setup. Also check if you have the original EZstruder, you really want the latest SeeMeCNC EZR extruder it honestly works great as is. 
    GDSTime 3010 12V Blower Fans - These part cooling fans really make a huge difference in the performance of the Eris. My effector mount base and top has M2 x 10 screw points for mounting them and a duct that blows down on to the part (I found no need for a nozzle)
    I used the existing whip but removed the original connectors and soldered them to a 8-pin GX16 connector (Use this guide for wiring) mounted to a hole I drilled in the case, I soldered and crimped the other side of the whip to the components on the effector side. This allows you to easily remove the whole assembly for troubleshooting and travel. You will need JST-XH crimps connectors for the BTT board and maybe some dupont 2.54 pitch connectors and crimpers.

Basically if you've build a Voron V0.1/0.2 you can handle this mod. It is basically a Voron V0 delta but not nearly as rigid or fast. 

Please comment or message me and I will publish the Klipper config files needed for the Eris. 

The printing results are incredible considering the age and plastic shell of this delta. It is limited to 500mm/s2 accels and 125mm/s rapids, which is quite slow for modern standards but you can't beat the portability and looks of this little printer. 

If you have an Eris and want to do this mod, please message me I will try to help you with whatever I can. STEP files included if you need to modify something, I can provide Fusion 360 files if needed (they're too messy to publish).

Pulled files from my Printables repo:
https://www.printables.com/model/581542-seemecnc-eris-voron-v0-inspired-upgrade-kit