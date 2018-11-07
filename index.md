
# Welcome to manual page of F1/10!
{:.no_toc}

This site will be the future place of reference for F1/10 race cars! But it is a work in progress for now, so place refer to [Car Assembly Page](http://f1tenth.org/car-assembly) to look at the pdf manual

<img src="f10cover.PNG" alt="hi" class="inline"/>

# Table of Contents
{:.no_toc}
1. The generated Toc will be an ordered list
{:toc}

---

## What you need to start

### Miscellaneous
(1) Laptop with Ubuntu Xenial 16.04.01 LTS installed. (Other versions of Ubuntu may work as well, but we can’t guarantee this.)

### The hardware kit
#### Mechanical
(1) Traxxas RC rally car (recommended model: Ford Fiesta ST)<br/>
Note: as of August 2018, this car is sold with a brushed motor by Traxxas. See link below for brushless motor.
(1) [Velineon 3351R/3500 brushless DC motor](​https://www.amazon.com/Traxxas-Velineon-Brushless-Motor-3500Kv/dp/B00XWTXOCC/ref=sr_1_5?s=toys-and-games&ie=UTF8&qid=1533078584&sr=1-5&keywords=3351r&dpID=412p2cEdtOL&preST=_SX342_QL70_&dpSrc=srch)<br/>
(1) laser-cut chassis on which you will mount everything<br/>
(1) LIDAR mount with (2) C-shaped brackets<br/>
(2) threaded 14mm M3 standoffs<br/>
(4) 19mm M3 standoffs<br/>
(8) 35mm M3 standoffs<br/>
(4) 45mm M3 standoffs<br/>
(35) 10mm M3 screws<br/>
(4) 20mm M3 screws<br/>
(4) 8mm round nylon spacers<br/>
(1) Roll of double-sided tape (for mounting USB hubs and optionally FOCbox)<br/>

[Back to Top](#table-of-contents)

#### Electrical
(1) power board (obtained from University of Pennsylvania team. This was designed at Penn, printed by ​ www.4pcb.com​ )<br/>
(1) Nvidia Jetson TX1 or TX2 with Wi-Fi antennas (included with the development board)<br/>
(1) Orbitty carrier board (for Jetson)<br/>
(1) Hokuyo 10LX or 30LX LIDAR<br/>
(1) Traxxas LiPo or NiMH battery (at least 9V)<br/>
(1) FOCbox or VESC 4.12 electronic speed controller<br/>
(1) USB hub (at least 6 ports)<br/>
(1) short (~1 ft) USB micro cable<br/>
(2) spools/strips of 22 AWG wire of different colors (preferably red and black)<br/>
(1) USB keyboard and mouse<br/>
(1) HDMI display<br/>
Optional: (1) HDMI dummy plug and (1) USB Wi-Fi adapter for connecting to the car via VNC
[Back to Top](#table-of-contents)

#### Tools
(1) Metric ruler<br/>
(1) Needle-nose pliers<br/>
(1) Wire strippers<br/>
(1) 2mm width or smaller flathead screwdriver<br/>
(1) 5/64 inch diameter hex driver key or small Phillips screwdriver (1) Hex socket driver or wrench (to hold standoffs in place)<br/>
(1) T3 Torx screwdriver<br/>
[Back to Top](#table-of-contents)

<img src="01whatYouNeedToStart/F10Materials.PNG" alt="hi" class="inline"/>



## Preparing and Assembling the Car


### Preparing the Car 

TODO: will fill out when the fourth Traxxas car arrives<br/>

Obtaining the Power Board<br/>
[1. Instructions on getting the power board from Penn,
2. and a link to files that you would send to a PCB company like 4PCB or PCBWay. Currently on github ​https://github.com/mlab-upenn/f1tenth-dev/tree/master/power-board-v2.0​ ]<br/>
 
A note on why we have a power board:​ The power board is used to provide a stable voltage source for the car and its peripherals since the battery voltage drops as the battery runs out. The board does not do any charging of the battery, so you will need a Traxxas EZ-Peak charger to charge it (you can find them on Traxxas' website). At present, there's no way to know the battery's charge level except by measuring it with a multimeter or the BLDC Tool as it runs, but we could think about adding a low voltage LED or seven-segment LCD display (to show the voltage) to the next iteration of the board. The LIPO protection module and green connectors are currently unused and are a legacy from previous F1/10 car iterations which used the Teensy microcontroller as a motor driver.<br/>
[Back to Top](#table-of-contents)


### Installing the Body Standoffs

Begin by installing four 45mm M3 standoffs into the holes of the main car body pictured below. Secure the standoffs to the bottom of the car using 10mm M3 screws, and use either nosepliers or a hex driver to hold the standoff in place while you turn the screw on the other side. Pay attention to where you install the standoffs since there are several mounting holes on the car's base. See the picture below for clarification.<br/>

Next, install two threaded 14mm M3 standoffs into the front holes in the car base, using the pliers or hex driver to thread the standoffs into the holes. Don't mount the chassis to the car yet since we still need to mount the Jetson and power board to the chassis.<br/>

<img src="02PreparingAndAssemblingTheCar/InstallingStandOffs.png" alt="hi" class="inline"/>

<img src="02PreparingAndAssemblingTheCar/InstallingStandOffs2.png" alt="hi" class="inline"/>
[Back to Top](#table-of-contents)


### Mounting the FOCbox to the Chassis
Feed the three motor wires for the FOCbox through the rectangular slot in the chassis as shown below.

<img src="02PreparingAndAssemblingTheCar/FOCBoxToChassis.png" alt="hi" class="inline"/>

Alternate method of securing the FOCbox if screws don’t fit​ : Some FOCboxes (the more recently-made ones) have smaller screw holes that won’t fit M3-size screws. If this is the case for your FOCbox, you can use a few pieces of double-sided tape to secure the FOCbox instead.<br/>

<img src="02PreparingAndAssemblingTheCar/AlternateFOCbox.png" alt="hi" class="inline"/>

[Back to Top](#table-of-contents)

### Installing the Chassis Standoffs
Mount eight 35mm M3 standoffs to the ​ glossy side​ of the black laser-cut chassis in the
positions shown below. Thread 10mm M3 screws through the drill holes and screw
them into the standoffs to secure them. (​ Important​ : If you do not mount the standoffs to
the glossy side, the power board won't fit since the screw holes will be misaligned.) <br/>

Note there are several drill holes in the chassis, so make sure you’re using the right
ones. In the image below, the 4 screws on the left(which is the back of the car) will
eventually hold the power board, so that’s a good way to see if they’re properly placed.
The 4 screws on the right (2 on each side of the oval cutout) will eventually hold the
Orbitty carrier attached to the Jetson.<br/>

<img src="02PreparingAndAssemblingTheCar/chasisstandoff1.png" alt="hi" class="inline"/>

Mount two more (19mm M3) standoffs to the front part of the chassis for the LIDAR, and
secure with 10mm screws. The top part of the chassis should look like the picture
below.

<img src="02PreparingAndAssemblingTheCar/chasisstandoff2.png" alt="hi" class="inline"/>

[Back to Top](#table-of-contents)


### Detaching the Jetson from the Development Board
When you purchase a Jetson, it is attached to a development board. In order to use it
on the car, you will need to unscrew the Jetson and its Wi-Fi antenna from the
development board.<br/>
Before you remove the antenna, you will need to remove the bottom plate from the
development board. Remove the four screws marked below and lift the development
board away from the plate.<br/>

<img src="02PreparingAndAssemblingTheCar/jetson1.png" alt="hi" class="inline"/>

Next, remove the Wi-Fi antenna by unscrewing the two screws marked below. Keep the
screws in a safe place, as you’ll use them in a bit to attach the antennas to standoffs. <br/>

<img src="02PreparingAndAssemblingTheCar/jetson2.png" alt="hi" class="inline"/>

Remove the two brass-colored nuts holding the antennas to the L-shaped bracket, and
then remove the two antennas from the bracket. It helps to use two pairs of pliers: one
to hold the rear nuts in place and another to unscrew the nuts on the end with the
antenna connectors.<br/>

<img src="02PreparingAndAssemblingTheCar/jetson3.png" alt="hi" class="inline"/>

Using a Phillips screwdriver, thread the two screws you saved earlier completely into
the bracket as pictured below. Attach two standoffs to the opposite ends of the screws
and hand-tighten them until they won’t turn anymore. Use the pliers to tighten the
standoffs more while you hold the head of the screw in place using the screwdriver.
Once you’ve done these steps, place the antennas and washers back into the bracket,
and tighten the brass nuts onto the threaded connectors again.<br/>

<img src="02PreparingAndAssemblingTheCar/jetson4.png" alt="hi" class="inline"/>

Unplug the Jetson’s fan and remove the Jetson from the development board by using a
T3 Torx screwdriver to unscrew the Jetson (the large silver heat sink), and then pull up
gently to detach it from the development board. Keep the Jetson in a safe place while
you attach the antennas to the power board.<br/>

<img src="02PreparingAndAssemblingTheCar/jetson5.png" alt="hi" class="inline"/>
[Back to Top](#table-of-contents)


### Mounting the Wi-Fi Antennas to the Power Board
Attach the two standoffs for the Wi-Fi antenna bracket to the power board, making sure
the antennas, when installed and extended, lie ​ over ​ the board and now away from it.
Install the two black antennas onto the threaded connectors if they aren’t already on.<br/>

<img src="02PreparingAndAssemblingTheCar/wifi1.png" alt="hi" class="inline"/>

Attach the two wires for the Jetson Wi-Fi antenna to the two gold-colored connectors
near the fan connector on the heat sink (the order of the wires doesn’t matter). This can
be a little tricky, so you might want to use a flathead screwdriver to ensure the
connections are tight. ​ Don’t press too hard​ , however as you can easily damage the
connectors if you use excessive force!

<img src="02PreparingAndAssemblingTheCar/wifi2.png" alt="hi" class="inline"/>
[Back to Top](#table-of-contents)

### Mounting the Power Board to the Chassis

Screw the power board onto its chassis standoffs using 10mm M3 screws. The screw
positions are indicated with arrows below.

<img src="02PreparingAndAssemblingTheCar/powerboard1.png" alt="hi" class="inline"/>

[Back to Top](#table-of-contents)


### Attaching the Orbitty to the Jetson
Attach the Orbitty to the Jetson by connecting the two long black ports and connect the Jetson’s
fan to the Orbitty’s fan connector as shown in the pictures below..

<img src="02PreparingAndAssemblingTheCar/orbittyjetson.png" alt="hi" class="inline"/>
[Back to Top](#table-of-contents)


### Connecting the Jetson and Power Board
Cut two 8-inch pieces of wire of different colors (preferably red and black), and strip
both ends to a short length (1/8 inch). Locate the green terminal block on the Jetson
and attach one end of one wire to the + ​ Vin​ terminal, and the other end to one of the
green 1 ​ 2V​ terminals on the power board. (Any of the 12 volt terminals are acceptable. To
attach, insert the stripped end into the terminal and screw the little screw tight with a
small flathead screwdriver.) Attach the other stripped wire to the G ​ ND​ terminal on the
Jetson and to the G ​ ND​ terminal on the corresponding terminal block on the power board.

<img src="02PreparingAndAssemblingTheCar/jetsonpowerboard.png" alt="hi" class="inline"/>

[Back to Top](#table-of-contents)

### Mounting the Jetson to the Chassis
Your kit comes with four white plastic standoffs; place these between the Jetson PCB
and heatsink (see picture) ​ before ​ threading the screws through. Otherwise, you risk
bending the Orbitty while screwing it in. Use 20mm screws to secure the Jetson to its
chassis standoffs.

<img src="02PreparingAndAssemblingTheCar/jetsonchassis.png" alt="hi" class="inline"/>

Ensure that when you mount the Jetson that the wires for neither the Wi-Fi antenna nor
the Jetson's power connections get pinched. It might help to tuck both sets of wires
underneath the power board. (Don't tuck them underneath the Jetson because they
might restrict airflow or obstruct the fan's blades.) Your configuration should now look
something like this:

<img src="02PreparingAndAssemblingTheCar/jetsonchassis2.png" alt="hi" class="inline"/>


[Back to Top](#table-of-contents)

### Mounting the Chassis to the Car Underbody
Place the chassis onto the five standoffs on the car base and align the chassis’ drill
holes with the car’s base standoffs you attached earlier as shown below. Use six 10mm
M3 screws to secure the chassis to the standoffs.

<img src="02PreparingAndAssemblingTheCar/chassisunderbody.png" alt="hi" class="inline"/>
[Back to Top](#table-of-contents)

### Mounting the LIDAR
The LIDAR should have two cords: one for power and another for either Ethernet or
USB. Cut the end of the power cord, leaving 1-2 feet of cable. Strip the end, cut away all
wires except for the blue and brown ones, and strip those two wires to 1/8 inch as
shown below.

<img src="02PreparingAndAssemblingTheCar/lidar1.png" alt="hi" class="inline"/>

Attach the LIDAR to the tree-shaped base using two (10LX) or four (30LX) screws, such
that the wires protruding from the LIDAR go towards the back of the car. (For the 30LX,
the two LEDs at the top of the LIDAR should face the front of the car.) Then mount the
C-shaped brackets to the black tree-shaped base as shown in the pictures below. ​ Note:
if the black mount does not fit in the holes of the C brackets, sand the inserts until they
do.
<img src="02PreparingAndAssemblingTheCar/lidar2.png" alt="hi" class="inline"/>

Mount the LIDAR to the car by fitting the two thick protruding parts of the mounting
brackets into the holes. The open part of the "C" in the brackets should face forward as
shown below.
<img src="02PreparingAndAssemblingTheCar/lidar3.png" alt="hi" class="inline"/>

If you completed the previous steps correctly, two of the holes on the narrow end of the
LIDAR base should match up with the two 19mm standoffs you mounted earlier. Wind
the power and USB cords of the LIDAR around its base so that there is just enough
available to plug into the power board and Jetson, with a little bit of slack so that it is not
too tight. Tuck both cords under the LIDAR mounting plate between the two silverstandoffs, and secure the LIDAR base to the standoffs on the chassis using two 10mm
M3 screws.
<img src="02PreparingAndAssemblingTheCar/lidar4.png" alt="hi" class="inline"/>
[Back to Top](#table-of-contents)


### Mounting the USB Hubs
Attack two pieces of double-sided tape to a USB hub. Place the hub onto the empty space of
the chassis directly below the Jetson and to the right of the power board as shown. If your hub
has power buttons, make sure all of them are turned on.<br/> 

<img src="02PreparingAndAssemblingTheCar/usb1.png" alt="hi" class="inline"/>

If you need more USB ports (required if your LiDAR uses USB), you can stack a second hub
onto the top of the first. Again, use double-sided tape to secure the second hub and make sure
all power buttons are on.<br/>

Plug the first USB hub into the Orbitty board. If you’re using a second hub, use the white micro
USB adapter that comes with the Jetson to plug in the second hub.

<img src="02PreparingAndAssemblingTheCar/usb2.png" alt="hi" class="inline"/>


### Connecting the LIDAR

Attach the LIDAR's power cable to a free 12V terminal block on the power board. The brown wire should go to the 12V terminal, and the blue wire should go to the corresponding GND terminal. The side of the LIDAR has a pinout as well if you forget.

<img src="02PreparingAndAssemblingTheCar/Connecting the LIDAR.png" alt="hi" class="inline"/>

If the LIDAR has an Ethernet cable, attach it to the Ethernet port on the Jetson. If it has a USB cable, plug it into the USB hub. Route any excess cables behind the USB hubs as shown. <br/>

<img src="Connecting the LIDAR.png" alt="hi" class="inline"/>


### Connecting the FOCbox

Pass the 3 round FOCbox wires through the rectangular slot in the plastic chassis, then connect the 3 circular bullet connectors to the three motor wires. (The order in which you connect the wires kinda doesn’t matter (electrically speaking). If you run the car and it goes backwards when it should go forwards, you can swap any two of the three wires.) Connect the 3-wire servo ribbon cable as well, making sure the colors match up. <br/>

<img src="Connecting the LIDAR.png" alt="hi" class="inline"/>

If your micro USB cable is thin enough, thread it through the rectangular wire slot and around the FOCbox to the USB connector as shown below, or route it around the rear end of the chassis if it isn’t. Plug the cable into the FOCbox’s USB connector and into a free port on your USB hub. Tie the USB cable up using a cable tie, and tuck all of the wires underneath the chassis. You can also use this time to plug in the LIDAR (if it is USB), the external Wi-FI adapter, and the receiver for the F710 gamepad.

<img src="Connecting the LIDAR.png" alt="hi" class="inline"/>


### Connecting the Car to the Battery

Connect the battery to the FOCbox using the battery connector. ​Make sure that red is aligned with red and black is aligned with black - otherwise things will get hot and dicey. ​Then connect the FOCbox to the power board using the white port shown in the picture below. <br/>

<img src="Connecting the LIDAR.png" alt="hi" class="inline"/>

At this point, your car should be assembled, the Jetson lights should flash when you flip the power switch, and the car is ready to run!  <br/>

Note: At present, there's no way to know the battery's charge level except by measuring it with a multimeter as it runs. You might consider adding a low voltage LED or seven-segment LCD display (to show the voltage). <br/>



### Tuning the FOCbox’s PID Gains

In this section we use the words FOCbox and VESC interchangeably.

Important Safety Tips<br/>

- Make sure you hold on to the car while testing the motor to prevent it from flying off the stand. <br/>
- Make sure there are no objects (or people) in the vicinity of the wheels while testing.<br/>
- It’s a good idea to use a fully-charged LiPO battery instead of a power supply to ensure the motor has enough current to spin up.<br/>

1. Put your car on an elevated stand so that its wheels can turn without it going anywhere. If you don’t have an RC car stand, you can use the box that came with your Jetson.<br/>

2. Connect the host laptop to the FOCbox using a USB cable.<br/>

3. Download bldc tool from JetsonHacks (​https://github.com/jetsonhacks/installBLDC​),
following his instructions for installation.<br/>

4. Open BLDC Tool and click the “Connect” button at the top right of the window to connect
to the VESC.
- If you get the error “Device not found”, try running the command ​lsusb​ in a
terminal. You should see an entry for “STMicroelectronics STMF407” or something similar. If you don’t, try unplugging and plugging in the USB cable on both ends. If the problem doesn’t go away, try rebooting the Jetson.<br/>
<img src="Connecting the LIDAR.png" alt="hi" class="inline"/>
- If you are using a VESC 4.12 (including a FOCbox), ensure the firmware version is 2.18.
<img src="Connecting the LIDAR.png" alt="hi" class="inline"/>

5. Disable keyboard control by clicking the “KB Ctrl” button at the lower right. This will prevent your keyboard’s arrow keys from controlling the motor and is important to prevent damage to the car from it moving unexpectedly.
<img src="Connecting the LIDAR.png" alt="hi" class="inline"/>

6. Start plotting the realtime RPM data by clicking the “Realtime Data” tab, and checking the “Activate sampling” checkbox at the bottom left of the window. Click the “RPM” tab above the graph.
- We will keep referring to this plot of the motor’s RPM as we tune the PID gains. Out goal is to get the motor to spin up as quickly as possible when we set it to a certain RPM. We also don’t want the motor to cog (not spin) or overshoot the target speed if possible.
<img src="Connecting the LIDAR.png" alt="hi" class="inline"/>

7. Test the motor first (without PID speed control) by setting the “Duty Cycle” to 0.20. This will spin the motor up to approximately 16,000 - 17,000 RPM. Let this run for a few seconds, and then press the “Release Motor” button at the bottom right to stop it.
- Observe the RPM graph. If the motor is spinning backwards (the RPM is negative), try reversing two of the connections from the VESC to the motor. (It doesn’t matter which wires you reverse.)
- If the wheels don’t spin and the motor makes no noise, check to make sure all connections to the motor are tight.
- If the wheels don’t spin and the motor does, ensure the motor’s gear is attached correctly to the gearbox at the back of the car. Spin both front wheels with your hand to verify that the gear is making good contact. You should feel some resistance when turning the wheels.
- If the motor doesn’t spin and makes a humming or hissing sound, you might need to replace the motor. If this doesn’t work, try replacing the VESC.
<img src="Connecting the LIDAR.png" alt="hi" class="inline"/>

8. Click the “Motor Configuration” tab at the top and the “Advanced” tab on the left. Set Ki and Kd to 0.00000, and set Kp to 0.00001. Click the “Write Configuration” button at the bottom, go back to the data plotting tab and run the car at 3000 RPM.
- You will notice that the car won’t even make it close, as it only goes up to around 1200 RPM. (High steady-state error.)
- Try turning Kp up to 0.00002, 0.00004, and 0.00008. (Don’t forget to write the configuration each time.) The motor will start to cog out at higher Kp values.
<img src="Connecting the LIDAR.png" alt="hi" class="inline"/>

9. Set Kp back to 0.00002, and set Ki to 0.00002, and run the car at 3000 RPM again. Notice how the car slowly reaches the 3000 RPM target. (This is because adding Ki helps to eliminate steady-state error.)
- Keep increasing Ki; set it to 0.00005 and then double that value a few times until the car is able to reach 3000 RPM without overshooting or cogging out.<br/>

10. Now, try increasing the speed to 6000 RPM.<br/>
- The motor might cog out and overshoot. If it does, try halving Kp.<br/>

11. Increase the speed to 10,000 RPM and then 20,000 RPM. ​Make sure you hold the car!
- If the motor cogs out and overshoots, halve Kp until it doesn’t.<br/>
- It may also help to halve Ki if halving Kp doesn’t work.<br/>
- If done correctly, the motor should not overshoot to more than 2 times the set<br/>
RPM. (That is, if the RPM is set to 15,000, its peak value should not exceed 30,000.)



### LiPo (Lithium Polymer) Battery Safety

LiPO batteries allow your car to run for a long time, but they are not something to play with or joke about. They store a large amount of energy in a small space and can damage your car and cause a fire if used improperly. With this in mind, here are some safety tips for using them with the car.<br/>

- When charging batteries, always monitor them and place them in a fireproof bag on a non-flammable surface clear of any other objects.<br/>
- Do not leave a LIPO battery connected to the car when you’re not using it. The battery will discharge and its voltage will drop to a level too low to charge it safely again.<br/>
- Unplug the battery from the car immediately if you notice any popping sounds, bloating of the battery, burning smell, or smoke.<br/>
- Never short the battery leads.<br/>
- Do not plug the battery in backwards. This will damage the VESC and power board (and
likely the Jetson as well) and could cause a short circuit.<br/>

See ​this video​ and ​this video​ for examples of what might happen if you don’t take care of your batteries. Be safe and don’t let these happen to you!<br/>


# Basic software install

## On Your Laptop

### Supported Versions 

You will need to install the OS Ubuntu Xenial 16.04.01 and ROS Kinetic. <b/r>
Could other combinations work? Sure.<b/r>
Will we support them? Nope.<b/r>


## Install ROS

Go to ROS.org and follow the instructions there to install the version of ROS referenced above.
<img src="Connecting the LIDAR.png" alt="hi" class="inline"/>

## On Jetson

On a high level, these are the things that need to be installed on the Jetson.<b/r>
1. Linux GUI<b/r>
2. Jetpack 3.2 flash<b/r>
3. A re-flash of the Connect Tech Orbitty<b/r>
4. ROS Kinetic<b/r>

### Connect terminals to the Jetson (aka “the device”)

(These instructions are also in the Jeston’s Quick Start Guide under “Force USB Recovery Mode”. Refer to it to see all the buttons, ports and whatnot.)<b/r>

Connect a display to the Jetson via HDMI port<b/r>

Connect a USB keyboard<b/r>

Connect the Jetson to your host PC via the USB micro-B plug Plug to power<b/r>

The Jetson should power on. If it doesn’t, push the ON button. Login: nvidia
Password: nvidia<b/r>
<img src="Connecting the LIDAR.png" alt="hi" class="inline"/>

### Install Linux
Run
$ cat NVIDIA-INSTALLER/README.txt

And run the instructions that are in that file to install Ubuntu Linux. Note that TX1 comes with 14.04 LTS and TX2 comes with 16.04 LTS. There may be an additional step for TX1 if the course is using 16.04 LTS.<b/r>

### Flash the Jetpack
NOTE: you will need some 14GB of free space on the host computer for this step.<b/r>

Now that we have the GUI, we want to flash the Jetson with Nvidia’s Jetpack 3.2.<b/r>

To do this, we need a host computer that is running Linux 14.04 (it seems 16.04 also works - try it if that’s what you have). The Jetpack is first downloaded onto the host computer and then transferred by micro USB cable over to the Jetson. Follow these instructions: https://developer.nvidia.com/embedded/jetpack<b/r>

What if you don’t have a Linux 14.04 computer laying around? (most of us don’t). See ​Appendix A​ of this doc for an amazing set of instructions by Klein Yuan which details how to use a virtual machine with a Mac to do the flash. Steps would probably work similarly for a PC that is running Virtual Box.<b/r>

### Re-flash the Orbitty

After the Jetson has been flashed with Jetpack, we will actually need to re-flash it with the Connect Tech Orbitty firmware. Otherwise on the TX2 there can be issues with the USB 3.0 not working on the Orbitty carrier board. A great link to instructions is from NVIDIA-Jetson: https://github.com/NVIDIA-Jetson/jetson-trashformers/wiki/JetsonTM-Flashing-and-Setup-Guide-f or-a-Connect-Tech-Carrier-Board​. ​Note that each time you flash all of the files<b/r> will essentially be deleted from your Jetson​. So make sure to save any work you may have already done and upload it.
     
### Install ROS

Lastly, we will want to install ROS Kinetic. Jetson Hacks on Github has scripts to install ROS Kinetic.
- Here for TX2: ​https://github.com/jetsonhacks/installROSTX2​.
- And here for TX1: ​https://github.com/jetsonhacks/installROSTX1​.



### Markdown
{:.no_toc}

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes
{:.no_toc}

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/hanmingz/f1tenthmanual/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

[Back to Top](#table-of-contents)

## Support or Contact
Contributors to this [Manual](http://f1tenth.org/car-assembly):
Houssam Abbas - Assistant Professor, Oregon State University
Jack Harkins - University of Pennsylvania
Chris Kao - University of Pennsylvania
Matthew O’Kelly - University of Pennsylvania
Sheil Sarda - University of Pennsylvania

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

