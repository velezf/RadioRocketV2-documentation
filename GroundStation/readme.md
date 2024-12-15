## The Ground Station
### Introduction
The overall intent of this part of the Radio Rocket project is to build the N3VEM Radio Rocket ground station but over a series of increasingly complex “sprints” or ~2 week blocks of work. Each sprint were accomplished spending only a couple hours a day on the project over the 2 weeks. The N3VEM ground station uses a single board computer (SBC) alongside a Software Defined Radio (SDR) to collect the APRS data. It also uses LoRa breakout boards attached to the single board computer for rocket telemetry. Both radio systems run on the single board computer inside a DIY housing to hold all the hardware.  

The full project is here:https://github.com/N3VEM/RadioRocketV2 
And N3VEM’s blog here: https://n3vem.com/blog/radiorocket/ 

KC3ZTQ provided this additional documentation on the N3VEM build from the perspective of a complete Noob. KC3ZTQ did already have a Technician License (KC3ZTQ) and a NAR L1 Certification (120953). 

The project does not require extensive presvious expereince. If you've never done anything with single board computers (SBC) or Software Defined Radios (SDR) that is OK. If you have limited to no experience with Linux, command line, and all of the software packages used in the Radio Rocket that is OK. Similarly, only a little experience with “arduino like” components, soldering, or in rocket electronics beyond basic commercially available altimeters is suffcient.  

### Bill of Materials for the Ground Station
* [Libre Computer LePotato Single Board Computer](https://libre.computer/products/aml-s905x-cc/) -
* [Adafruit Feather 32u4 RFM96 LoRa Radio - 433MHz - RadioFruit](https://www.adafruit.com/product/3079) OR [Adafruit Feather M0 RFM96 LoRa Radio - 433MHz - RadioFruit](https://www.adafruit.com/product/3179)
    * The M0 version is a little more powerful, but either should work fine for you.    
* [uFL SMT antenna connector for above](https://www.adafruit.com/product/1661)
* [uFL to SMA jumper](https://www.adafruit.com/product/851)
* [SMA RF Jumpers](https://amzn.to/3jMf6Mw)
* [SMA right angle adapters](https://amzn.to/3leU6hK)
* (2) [Antennas](https://amzn.to/3XjlWXB)
* [RTL-SDR Dongle](https://www.rtl-sdr.com/buy-rtl-sdr-dvb-t-dongles/)
* [USB jumper cable for above](https://amzn.to/3Ims2Ct)
* [Battery 'Shoe'](https://amzn.to/3RLUsIW) for the LePotato. I call it a 'shoe' because it goes on the bottom of the board instead of the top, like a traditional 'HAT' would.
* [A pretty power button](https://amzn.to/3ljC0LD)
* Assorted LEDs - colors to your own preferance.
* [Misc. wires and jumpers](https://amzn.to/3jJmsjX). The type used in breadboarding would work fine.
* [Some strip boards](https://amzn.to/3RPnB5S)
* [Micro USB data cables](https://amzn.to/3lr9zv7)
* [USB bulkhead jumper](https://amzn.to/3HS609b) optional, and there are wildly cheaper versions of this - but this is what I used because I had one that was taken out of a peice of commercial equipment.
* RJ45 Bulkhead Connector. The one's I used came out of a peice of commercial equipment, but if you search you'll find lots of options.
* [standoffs](https://www.adafruit.com/product/3299)
* [12/24v to 5v DC-DC Converter](https://amzn.to/3YBZTMW)
* [Barrel Jack](https://amzn.to/3DXKkHn)
* Zip Ties, Zip Tie Mounts
* [Enclosure](https://amzn.to/3HPVTBr)

# Sprint 1 -Demonstrate Commerical Off The Shelf APRS TX/RX Capability

Purpose: Before getting overly committed to the project you may want to confirm you can handle the basics of APRS. You may slso want to create a positive control for the in rocket APRS tracker and ground station. This build is a mid way step to the SDR APRS radio using Direwolf and YAAC or PinpointAPRS. 

## Bill of Materials:
### Hardware
* Baofeng UV-5R (I had an old UV-5R+ in my case)
* Old Android Phone ( I bought a $30 Kyocera DuraForce Pro 2 E6920 64GB off ebay)
* BTECH APRS-K1 Cable (https://www.amazon.com/dp/B01LMIBAZW) 
* Baofeng CHIRP programming cable
### Software
* APRSdroid installed on phone
* CHIRP programming software
* Access to APRS.Fi on another device

## Physical Construction
This sprint requires no construction as all the parts are plug and play. The BTECH cable needs to be securely plugged into both devices. 
Software Configuration
CHIRP - There are a lot of uses for CHIRP, with many guides available. The only required step I encountered was to use CHIRP to configure the Baofeng VOX settings to be more granular than stock. I made each step of the VOX one unit step (ie. 1=1, 2=2,3=3…). 
APRSdroid settings: Again many guides available. Depending on your application the settings will vary. My goal was to transmit and receive APRS packets.Settings are in “preferences”. I used: 
              * -Connection Preferences: Connection Protocol = Audio (AFSK) 
                                                        * Audio Output = Music 
                                                        * No other boxes checked
                                                        * Frame Sync Prefix= 300
## Looking Forward to Sprint 2
While fiddling around with settings and getting this to work I ordered all the parts for an Alpha build of the ground station. Parts listed in sprint 2. 

## Discussion
There is a lot of documentation of APRSdroid use with Baofeng radios. At this point this is mostly fiddling around with software settings on the radio and the APRSdroid app to get this to work. The end goal for me was to see my packets on APRS.Fi. The ground station should replicate this capability in a SDR with additional capability.

# Sprint 2 - Ground Station - Alpha Build
N3VEM blog post relevant to this sprint
* https://n3vem.com/blog/RadioRocketGroundStationAPRS/
* https://n3vem.com/blog/ground-station-v2/

## Purpose
My goal here was to get familiar with single board computers (SBC) and get an APRS SDR radio running on one. I plan to worry about the LoRa radio in a second sprint. At this point this should also give me a DIY ground station that can receive APRS data from commercially available rocket e-bay ready electronics like AltusMetrum TeleMetrum.  


## Bill of Materials -N3VEM part list on github and small parts not previously mentioned
### Hardware
* Libre Computer Le Potato AML-S905X-CC SBC Complete Starter Kit 
* SanDisk Ultra 32GB Micro SD SDHC Memory Flash Card (5 Pack)
* Bingfu SMA Female Bulkhead Mount to SMA Male RG316 Antenna Extension Cable 12 inch 30cm 2-Pack 
* HYS NA-701 Walkie Talkie Antenna Dual Band 2meter 70cm Two Way Radio Replacement Antenna with SMA Male Connector (two of these)
* V4 R828D RTL2832U 1PPM TCXO HF Bias Tee SMA Software Defined Radio with Dipole Antenna Kit
* Amazon Basics Wired Keyboard
* Verbatim Wired USB Computer Mouse 
* Monitor with HDMI input 
### Software
* Le Potato OS
* Recommended distros by Libre 
* I ended up using Ubuntu Desktop not Armbian as it didn't seem recommended by Libre for the board. I choose desktop so if I bailed on this project I was left with a full Linux distro to play with 
* Software to Flash the SD Cards
* Requirements:  Write Verification Process,Cross Platform Stability, Protection Against Writing to System Drives
* I used balenaEtcher on MacOS
* Direwolf - recommend to build from source 
* https://github.com/wb2osz/direwolf 
* APRS Software
* I choose Xastir http://xastir.org/index.php/Main_Page 

## Physical Construction
This alpha build does not involve the final enclosure so things are spread out across the desk in the “prototyping mode”. Most everything is traditional plug and play: ethernet for WAN, MicroUSB for power, microSD as pops in the bottom of the Le Potato like a SSD, HDMI for display, and USB peripherals. My kit came with a PWM fan, I plugged this into GPIO Pin 33 (first time using those). I used the header map from libre to find that. The SDR dongle plugs into usb and gets a SMA extender and antenna attached. 

## Software Install
There was a surprising amount of work to get this thing stood up. Most of this sprint was spent reading about best practices with linux distro fresh installs and SBC. The best advice I can give is to flash multiple microSD cards to start and frequently back up (by copy flashing with balenaEtcher) at reasonable checkpoints. 

## Flashing SD Card
First I downloaded balenaEthcer on my Mac
Then I downloaded the ubuntu desktop imagine from Libre distro server
Then i flashed the unzipped .img file to several labeled microSD cards
Insert one into SBC 
Turn on SBC

## Ubuntu Setup
Follow on screen instruction to completion
Find the terminal app: run suggested distro updates from Libre
I ran generally suggested stuff like sudo apt-get update && sudo apt-get upgrade
“Snapshot” micro SD
I ran the PWM Fan setup to get familiar with GPIO usage as it came with my kit
https://hub.libre.computer/t/how-to-read-and-control-pwm-fan-speed-on-aml-s905x-cc/541 
There is where I learned where to plug the 4th wire into (pin33)
“Snapshot” micro SD

## Direwolf Initial Install with its build dependencies 
There seemed to be instructions from this everywhere. They all seemed different. I found the “User Guide” in the github repo for Direwolf and followed the linux install instructions. There are a lot of dependencies that also need to be installed. The process is laid out in the User Guide Document, the Raspberry-Pi-APRS document, and the Raspberry-Pi-SDR-IGate document. You need to read and understand all 3 of these documents. 
* Documents Here: https://github.com/wb2osz/direwolf/tree/master/doc 
* I did the install and build first. I did not touch the direwolf.conf file
* I made a new directory in home/user and added a copy of original direwolf.conf just in case
* “Snapshot” micro SD
* run it `rtl_fm -f 144.39M - | direwolf -c sdr.conf -r 24000 -D 1 -`

## RTL-SDR initial command line tools install
* Follow the instructions in Raspberry-Pi-SDR-IGate.pdf (direwolf github docs) per N3VEM blog
* I made a copy of sd.conf in the same copy directory I mentioned above
* “Snapshot” micro SD

## Remote Login
* Setup some flavor of remote login to run headless
* In my case I used VNC as it works natively on my main Mac. This is in sharing settings in Ubuntu 
* “Snapshot” micro SD 

## YAAC Program
Install directions here: https://themodernham.com/aprs-on-linux-with-yaac-yet-another-aprs-client-and-direwolf/
I did have to install 
This gave me the APRS mapping capability on my SBC as all RX i-gate work is being done via direwolf.

## Node Red
Install directions here: https://nodered.org/docs/getting-started/raspberrypi

## Software Configuration 
## RTL-SDR
In user home I configured the sdr.conf file per https://www.instructables.com/Build-an-Amateur-Radio-APRS-RX-Only-IGate-Using-a-/ and his blog https://qso365.co.uk/2017/02/a-guide-to-setting-up-an-aprs-receive-only-igate-using-a-raspberry-pi-and-an-rtl-sdr-dongle/ 
This is also covered in https://github.com/wb2osz/direwolf/blob/master/doc/Raspberry-Pi-SDR-IGate.pdf

## Direwolf 
I didn’t actually edit configure direwolf at all
* https://themodernham.com/ultimate-direwolf-tnc-installation-guide-for-windows-and-linux/#linux-install
* I did make sure it had permissions as outlined in the blog above. 
  Started here: 
`sudo usermod -a -G dialout YOURUSER
sudo usermod -aG pulse-access YOURUSER
sudo usermod -aG audio YOURUSER
sudo usermod -aG plugdev YOURUSER`

## Crontab
* I made a script to run the start command below and placed it in my home directory
* I then added this to the crontab -e to run every 1 minute
  
## Run It 
I ran this per the Raspberry-Pi-SDR-IGate.pdf instructions
`rtl_fm -f 144.39M - | direwolf -c sdr.conf -r 24000 -D 1 -`
I used my radio/droid from Sprint 1 to confirm the iGate was working. 

## Looking Forward to Sprint 3
This entire setup was setup and run spread across the desk. At this point I ordered all the parts for the LoRa ground station,the parts for the LoRa Rocket, and the materials to move the ground station into the project box. 

# Sprint 3 Project Box Build - APRS Radio Into Project Box and LoRa Ground Station build
 All the hardware parts for this part of the project are listed above. I would expect alot of user specific customization on the project box depending on your specfic use of the project. For example, I added some extra ports to the box so I didnt always need to use it headless. I also added a fancy SPDT switch. You also need two LoRa radios to fully test the them, so I partially built the Teensy LoRa radio but did wire in the sensors yet. 

 ## Extra tools for Project Box
 * I found this stepped drill bit helpful: https://www.amazon.com/dp/B089T8HJHF?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1
   I used it to drill all the SMA connectors, 12v power, and USB holes.
 * I used a No43 Drill bit for the M2.5 nylon mounting hardware : https://www.amazon.com/gp/product/B0849LDH5P/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1
 * Running the Ground Station LoRa from Serial I needed this: https://www.amazon.com/dp/B013G4EAEI?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1
 * I powered my Libre Le Potato from the transformer with one of these: https://www.amazon.com/gp/product/B0BZWMWVDT/ref=ppx_yo_dt_b_asin_title_o04_s00?ie=UTF8&th=1

## Adafruit Feather M0 RFM96 LoRa Radio - 433MHz Build 
I didnt do anything to this beside solder the uFL SMT Antenna Connector on and solder stackable headers on. I powered it with the microUSB to USB-A above into the Le Potato. 

## Arduino IDE 
I used these sites and N3VEM sketches. I started with basics like blinking LEDs and then printing to serial and then there Hello World LoRa to LoRa messages. 
* https://learn.adafruit.com/adafruit-feather-m0-radio-with-lora-radio-module/setup#https-slash-slash-adafruit-dot-github-dot-io-slash-arduino-board-index-slash-package-adafruit-index-dot-json-2612538
* https://github.com/adafruit/Adafruit-Feather-M0-RFM-LoRa-PCB/blob/master/Adafruit%20Feather%20M0%20RFM9x%20Pinout.pdf

I added the boards to my IDE from these: 
* https://www.pjrc.com/teensy/td_download.html
* https://adafruit.github.io/arduino-board-index/package_adafruit_index.json for the feather

