# occultation-how-to-guide
How to do Occultation observations using modern equipment. A practical step-by-step guide for setting up software and equipment to perform occultations observations

# What are Occultations?
An occultation occurs when one celestial body moves in front of another, blocking (occulting) its light. In a lunar eclipse the moon occults the sun.

When an asteroid occults a star it breifly blocks the light. By accurately measuring the time of the disappearance and reappearance the position and size of the asteroid can be deteremined, and sometimes much more.

Asteroid occultations provide the most acurate measurements of asteroid position and size of any method, and can discover rings, moons around asteroid and atmospheres.

# What Equipment is Needed?
If you do astrophotography or planetary imaging you likely already have all the gear needed, just need to add timing.

Just start with what you have and upgrade later if you want.

- Telescope of any type. Sweet spot is 8-12", but smaller scopes are useful for mobile observations, and larger scopes can go deeper
- Astronomy camera. MONO planetary cameras are ideal (very senstive and cheap). Almost any astronomy camera can be used
- Mount. GOTO tracking mount with PC control is ideal, but a simple motorised tracking mount, non-tracking mount of dobsonian can be used
- Astronomy camera. MONO planetary cameras are ideal (very senstive and cheap). Almost any astronomy camera can be used
- Windows PC with Windows 10/11. Low sped is OK, a few GB of free disk space
- Accurate timing - see below

  
## Telescope Details
Ideal focal length range is 400-1,000 mm for good image scale and a FOV that makes it easy to plate solve and find targets. 

Longer focal lengths will work but at some point computer control and platesolving will be essential. Very long focal lengths (2,000+ mm) will start to cause problems with large star sizes.

A focal reducer can be used to get a more favourable focal length. Image quality is not important. Even the cheap GSO focal reducers will work fine. This one gives around 0.4x focal reduction https://astronz.nz/products/focal-reducer-0-5x-1-25

For SCTs a Meade 3.3x reducer is available, but long out of production.

## Mount Details
Computerised GOTO mounts are the most convenient and allow an easy workflow and fully automated observation using platesolving to find targets accurately.

A non-computerised GOTO mount can be used by manually entering coordinates, or using SharpCaps Push To assistant.

A tracking mount can use SharpCap Push To assistant.

A dobsonian or fixed mount can use the Sharpcap Push To assistant to prepoint the telescope, but it is more time consuming and difficult

Guiding or highly accurate tracking as long as you can keep the star in the image.

## Camera Details
Almost any astronomy camera can be used for occultations, so start with the camera you have, and if necessary upgrade later. 

The main requirements is being able to record at a fast enough frame rate without dropped frames or recording issues, up to ~25 fps/40 ms exposure. USB 3 cameras can usually do this. USB 2 cameras usually can't. Most modern astronomy cameras are USB 3, USB only used for some guide cameras and cheap colour cameras.

The best planetary cameras at the moment for occultations use the new Sony IMX662M sensor. Models include:
- ToupTek G3M662M (careful, they have another model with a USB2 interface which is not suitable)
- ZWO asi662m
- Models from Player One, QHY and others.

The Touptek G3M662M is currently the cheapest at about $US180.

Models using the older IMX462M sensor are nearly as good, slightly lower sensitive and slightly higher noise.

Older model CMOS mono cameras are fine, they will just not be quite as senstive.

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
https://www.sharpcap.co.uk/ For recording and telescope control use SharpCap Pro. License is needed (~$20).  Version 4.1 or later

https://github.com/labstercam/occultation-tools Occulation Manager is an add-in for SharpCap that manages and automates occultaiton recording, equipment setup and reporting. Highly recommended as otherwise you have to do a lot manually using many other software tools and systems.

TANGRA3 is used for light curve reduction. http://www.hristopavlov.net/Tangra3/

PyMovie/PyOTE is another program for light curver reduction. https://github.com/bob-anderson-ok/py-ote  

Personally I prefer TAGNRA3, and it is better integrated with Occultation Manager so will be easier for beginners to get started

Occult Watcher Cloud account. Sign up here https://cloud.occultwatcher.net/login#

Occult4. http://www.lunar-occultations.com/iota/occult4.htm  Highly sophisticated software for occultation predictions, analysis, reporting etc. Full installateion is recommended once you have gotten established in occultation observations. See install instrucions for the minimum installation required to get started in conjumction with Occultation Manager.

Occult Watcher Desktop (optional). Integrates with Occult Watcher Cloud and manages events with some reporting acability. Occultation Manager does many of the same things so you don't have to use Occult Watcher Desktop to get started. Desktop has better event searching and management, and the main feature is generating star maps (using Occult4 software). You can manage without Occult Watcher Desktop when you are starting out, but recommend to use it.

Occult Watcher Mobile (optional). A handy Phone app for listing your events from Occult Watcher Cloud. Currently requires manual side load

Xasteria (optional). A handy phone app that aggregrates weather forecasts etc. ClearOutside and MeteoBlue give good forecasts for New Zealand. Sat24.com gives cloud satellite imagery.








# Resources
https://www.occultations.org.nz/videotime/manual.htm

