# occultation-how-to-guide
How to do Occultation observations using modern equipment. A practical step-by-step guide for setting up software and equipment to perform occultations observations.

This guide focuses on using modern, generic CMOS astronomy cameras for occultations, using modern SharpCap software. It is intended primarily to help beginners get set up to be able to start doing occultation observations, using their existing astronomy gear at low or no cost. It is not a comprehensive guide to everything to do with occultations.


# What are Occultations?
An occultation occurs when one celestial body moves in front of another, blocking (occulting) its light. In a solar eclipse the moon occults the sun.

When an asteroid occults a star it briefly blocks the light. By accurately measuring the time of the disappearance and reappearance the position and size of the asteroid can be determined, and sometimes much more.

Asteroid occultations provide the most accurate measurements of asteroid position and size of any method, and can discover rings, moons around asteroids and atmospheres.

# Quick Start
If you just want to jump into the step-by-step instructions for the minimum software setup required go here: https://github.com/labstercam/occultation-how-to-guide/blob/main/README.md#getting-started---step-by-step

For information on how to set up SharpCap for occultations go here: https://github.com/labstercam/occultation-how-to-guide/blob/main/SharpCap.md

For tips on target finding go here: https://github.com/labstercam/occultation-how-to-guide/blob/main/Target%20Finding.md

For resources include comprehensive guides see Resources https://github.com/labstercam/occultation-how-to-guide/blob/main/README.md#resources


# What Equipment is Needed?
If you do astrophotography or planetary imaging you likely already have all the gear needed, just need to add accurate timing.

Just start with what you have and upgrade later if you want.

- Telescope of any type. Sweet spot is 8-12", but smaller scopes are useful for mobile observations, and larger scopes can go deeper
- Astronomy camera. MONO planetary cameras are ideal (very sensitive and cheap). Almost any astronomy camera can be used
- Mount. GOTO tracking mount with PC control is ideal, but a simple motorised tracking mount, non-tracking mount of dobsonian can be used
- Windows PC with Windows 10/11. Low spec is OK, 10 GB of free disk space minimum
- Accurate timing

  
## Telescope Details
The ideal focal length range is 400-1,000 mm for good image scale and a FOV that makes it easy to plate solve and find targets. 

Longer focal lengths will work but at some point computer control and platesolving will be essential. Very long focal lengths (2,000+ mm) will start to cause problems with large star sizes.

A focal reducer can be used to get a more favourable focal length and to improve the signal to noise ratio. Image quality is not important. Even the cheap GSO focal reducers will work fine. This one gives around 0.4x focal reduction https://astronz.nz/products/focal-reducer-0-5x-1-25

For SCTs a Meade 3.3x reducer is available, but long out of production.

## Mount Details
Computerised GOTO mounts are the most convenient and allow an easy workflow and fully automated observation using platesolving to find targets accurately.

A non-computerised GOTO mount can be used by manually entering coordinates, or using SharpCaps Push To assistant.

A tracking mount can use SharpCap Push To assistant.

A dobsonian or fixed mount can use the Sharpcap Push To assistant to prepoint the telescope, but it is more time consuming and difficult

Guiding or highly accurate tracking  is not necessary as long as you can keep the star in the image.

## Camera Details
Almost any astronomy camera can be used for occultations, so start with the camera you have, and if necessary upgrade later. The recommendation for beginners is to start using the cameras you have and just add the simple and cheap/free timing options.

The main requirements is being able to record at a fast enough frame rate without dropped frames or recording issues, up to ~25 fps/40 ms exposure. USB 3 cameras can usually do this. USB 2 cameras usually can't. Most modern astronomy cameras are USB 3, USB only used for some guide cameras and cheap colour cameras.

The best planetary cameras at the moment for occultations use the new Sony IMX662M sensor. Models include:
- ToupTek G3M662M (careful, they have another model with a USB2 interface which is not suitable)
- ZWO asi662m
- Models from Player One, QHY and others.

The Touptek G3M662M is currently the cheapest at about $US180.

Models using the older IMX462M sensor are nearly as good, slightly lower sensitive and slightly higher noise.

Older model CMOS mono cameras are fine, they will just not be quite as senstive.

For long focal length scopes (3,000+ mm) or if you can't use a focal reducer to get a short enough focal length, cameras with larger pixels are advisable. Cameras using the imx432M sensor have large 9 um pixels, and imx428/429 have 4.5 mm pixels, imx174 5.9 um pixels. These are more expensive and have larger sensors.

There are specialist GPS cameras with built in GPS timing available, but they are expensive (>$US 1,000). https://www.qhyccd.com/qhy174gps-imx174-scientific-cooled-camera/ QHY174GPS uses a sensor from 2014, so is not as senstive as newer cameras. https://dvticam.com/ DVTI+CAM has options for newer, more senstive sensors. ToupTek has a new model with built in GPS, available on special order. https://www.touptekastro.com/products/atr585m. This is the most sensitive and cheapest of the GPS cameras.

ASTRID is a dedicated GPS camera with built in computer that manages and records occultations. It is standalone and does not use a PC to record. https://occultations.org/astrid-details-and-ordering-page/

Colour cameras can be used, with less sensitivity again.

Older CCD cameras are not recommended as they usually have much lower sensitivey and much, much higher noise. Use it if that is all you have, but upgrade as soon as you can.

So start with the camera you have, and if necessary upgrade later.

## Windows PC
A windows PC running windows 10/11 is suitable. Old, very low spec machines should be avoided (may not have high speed USB ports, will be slow). Almost any modern laptop will be OK. Faster is better but don't need high performance.

Need a high speed USB port or USB C.

Do NOT need a graphics card.

Need enough storage for recordings (typically a few hundred MB each) so a few GB free space.

Need internet through WiFi or Ethernet

## Software
For recording and telescope control use **SharpCap Pro**. License is needed (~$20).  Version 4.1 or later. https://www.sharpcap.co.uk/ 

**Occulation Manager** is an add-in for SharpCap that manages and automates occultation recording, equipment setup and reporting. Highly recommended as otherwise you have to do a lot manually using many other software tools and systems, which is complicated and difficult to learn. https://github.com/labstercam/occultation-tools

**TANGRA3** is used for light curve reduction. http://www.hristopavlov.net/Tangra3/

**PyMovie/PyOTE** is another program for light curve reduction. https://github.com/bob-anderson-ok/py-ote  

Personally I prefer TANGRA, and it is better integrated with Occultation Manager at the moment so will be easier for beginners to get started

**Occult Watcher Cloud** account. Sign up here https://cloud.occultwatcher.net/login#

**Occult4**. Highly sophisticated software for occultation predictions, analysis, reporting etc. Full installation is recommended only once you have gotten established in occultation observations. See install instrucions below for the minimum installation required to get started in conjunction with Occultation Manager. Required if using TANGRA, optional if using PyMovie/PyOTER. http://www.lunar-occultations.com/iota/occult4.htm  

**Occult Watcher Desktop** (optional). Integrates with Occult Watcher Cloud and manages events with some reporting acability. Occultation Manager does many of the same things so you don't have to use Occult Watcher Desktop to get started. But Occult Watcher Desktop has better event searching and management, and can generate excellent star maps (using Occult4 software). You can manage without Occult Watcher Desktop when you are starting out, but recommend to use it.

**Xasteria** (optional). A handy phone app that aggregrates weather forecasts etc. ClearOutside and MeteoBlue give good forecasts for New Zealand. Sat24.com gives cloud satellite imagery.

## Timing
For occultations the recording frames must be timestamped with an accuracy of milli-seconds to UTC. Timing options include:
1. NTP (Network Time Protocol) on windows PC
2. GPS PPS timing on windows PC
3. GPS flash timing (external GPS flasher, DIY build or phone app)
4. Dedicated GPS camera

   

For beginners recommend using NTP timing on a windows PC as it is free and easy to set up and works with any camera. Use the **NTP Installer** https://github.com/labstercam/occultation-ntp-installer. This can give timing accuracy of ~5 ms which is good enough to get started. GPS PPS timing can be added later (cheap DIY build) or upgrade to a dedicated GPS camera.


# Getting Started - Step by Step

Basic setup to begin doing occultations. More complex software can be installed and learnt later

1. Sign up for an **Occult Watcher Cloud** account https://cloud.occultwatcher.net/login#
2. Install NTP timing **NTP Installer** using https://github.com/labstercam/occultation-ntp-installer . Installs Meinberg NTP, NTP Time Server Monitor, and the PC performance enhancements. Do not install the GPS options unless you have a GPS PPS or NMEA receiver.
3. Buy **SharpCap Pro** licence and install the software www.sharpcap.co.uk . Install drivers for your camera and equipment if necessary.
4. Download and install **Occultation Manager** add-in for SharpCap https://github.com/labstercam/occultation-tools
5. Download and install **TANGRA3** http://www.hristopavlov.net/Tangra3/
6. Download and install **Occult4**, minimal setup (see below)
7. Install the **AOTA addin** for TANGRA3. Open TANGRA3, go to Settings | Addins. Select "Occult Tools for Tangra", press 'Configure" then browse to the folder where Occult.exe is and select the folder.
8. Optionally install **Occult Watcher** if you want more sophisticated event management and/or customisable star charts. https://www.occultwatcher.net/ (see below)
9. If you want to use **PyMovie/PyOTE** instead of TANGRA download and install from https://github.com/bob-anderson-ok/py-ote 



## Occult4 Minimal Setup

Occult4 is a very sophisticated program with a lot of features that are not needed when you are starting out, so recommend either the following minimal installs to just keep it easy, or do the full install and take you time to learn how to use Occult4 as necessary.

As a beginner the only Occult4 functionality that is essential is the AOTA analysis. If you choose to use PyMovie/PyOTE you don't need AOTA.

### The minimal setup for Occult4 to use AOTA occultation analysis.
Download and minimal install may take 10-20 minutes. Full install takes much longer.

1. Go to http://www.lunar-occultations.com/iota/occult4.htm and follow instructions for download and install using OccultInstaller.zip
2. Unzip to the required location (see notes on page)
3. Create desktop shortcut to Occult.exe
4. Run Occult.exe (may need to approve)
5. Allow the .NET install if prompted (may already be on your system)
6. Allow download of InstallResources.zip if prompted.
7. Allow each downloads when prompted

At this point you will be taken to the Settings page where you can set up email and other users settings. These are not required to be able to use the AOTA analysis so are optional.

You will then be prompted to update a lot of data and resources. Again, these are not required to be able to use the AOTA analysis so are optional at this stage. 

### Minimal Occult4 download for Occult4 Star Charts
Occult4 generates really nice customisable star charts which are very helpful, but not essential as Occultation Manager can identify the target star and online catalog images are available. Occult4 star charts are better so recommded to install at some stage.

Minimum required are the GAIA catalog downloads (one of the items 40-43) for the magnitude limit you want (recommend mag 16 for 8"+ telescopes). This can be several GB download and if you have a PC with a small capacity drive (e.g. 64BG) this might be a problem.

### Full Occult4 setup
You will at some stage want the full Occult4 setup to be able to run predictions, examine asteroid and star information, do muuti-chord occultation analysis, double star analysis etc. So at some stage download all the Occult4 resources and complete the install, following the installation guidance on the webpage and the Occult4 help. You may need help or assitance from an experienced observer. 

## Occult Watcher Setup
Download and install from https://www.occultwatcher.net/

Open Occult Watcher. You may need to start it from an icon from the Windows start bar, found under the 'up' arrow. Right click to open. 

Follow the configruation instructions here to set up you location and enter your Occult Watcher Cloud credentials. https://www.occultwatcher.net/Configuration.html

Set up the Occult Tools addin to enable prediction details and star charts. Follow the instructions here https://www.occultwatcher.net/MoreAddins.html

Configure which feeds you want to use.


# Resources
Resources and further information. Note that this How To Guide focuses on how to use modern CMOS cameras and Sharpcap to do occultations. It does not cover other topics that have already been included in other resources, or are common astronomy practice, or outdated methods.

Note that many of these resources have not been updated for a long time and may refer to outdated information or obsolete equipment.

RASNZ Observing Occultations Using Video:  https://www.occultations.org.nz/videotime/manual.htm

IOTA Europe Resources Page: https://iota-es.de/guidelines.html

IOTA NA Observing Information: https://occultations.org/observing/



https://www.occultations.org.nz/videotime/manual.htm

