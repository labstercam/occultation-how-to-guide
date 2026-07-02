# Using SharpCap for Occultations

SharpCap is recommended for occultations as it supports specialist GPS cameras for occultations, uses the ADV occulation video format, and has the Occultation Manager add in available. Robin Glover (developer/owner) has always supported the occultation community and added many feastures specifically for occultations.

SharpCap is the ONLY consumer level software that has known timestamp performance which is essential for accurate timing.

## General Setup

Some general setup tips.
1. Set your location coordinates
2. Set up for Plate Solving. Use the built in Sharp Solve. Download the SharpSolve databases that suit your field of view. Can work down to ~0.1 degrees FOV
3. Install Occultation Manager addin
4. Install the manufacturer's drivers for your camera. Generic ASCOM or DirectShow drivers perform poorly and have limited camera functionality

   

# *** IMPORTANT ***
For accurate timing using CMOS astronomy cameras the camera acquisition delay must be measured. The delays only apply the SPECIFIC camera settings used. So don't keep chopping and changing camera settings. Find a setting or a few settings that work for your setup and stick with them

Gain and Exposure do NOT affect timing. Almost everything else does.


## Camera Setup for Occultations

SharpCap has Camera Profiles available so you can save and load the settings. Make use of them so you can keep your settings under control.

To get accurate timing using SharpCap you MUST NOT run the camera at too high a rate as it will have dropped frames. Recommendation is no more than 1/3 the max frame rate for the specific camera settings.

Tips to increase the max rate:
1. Reduce the region of interest to a roughly square FOV that is roughly 0.2 deg or so wide. This is usually sufficient to keep the star in the FOV and to have enough other stars for trackking and comparison
2. Use binning 2x2 or higher. Image scale up to 3-4" per pixel is fine for occultation recording
3. Use Hardware Binning if your camera supports it
4. Experiment with USB settings to find the best frame rates


### Recording Format

Recommend using a video format, in this priority:
1. ADV (Astro Digital Video). A specific format  for occultations that has rich meta-data including timestamps, supports GPS cameras, and has lossless compression. Smallest file sizes possible
2. SER. A general video format. Has frame timestamps but not much else. Some PCs may have trouble with ADV format, so use SER instead

Do not use AVI. This does not have frame timestamps, only onscreen timestamps if enable, and make processing much more difficult

If you can't use video formats or don't want to then use FITS format. This will be much larger file sizes, and timing performance is not as good

### Color Space
Use MONO8 or MONO16. Most colour cameras have the option to record in MONO.

MONO16 has a much larger dynamic range so does not saturate as easily as MONO8. This makes it much easier to set the gain as you can usually just use a fixed gain.

MONO8 is 1/4 the file size and may have higher frame rates, so you might have to use it. It will saturate more easily so you have to be more careful with the gain

### Gain

Use medium to high gain, roughly 2/3 of maximum. CMOS cameras have lower read noise at higher gain and will perform better. Check your camera for the gain setting where it switches from Low Gain Conversion (LGC) to High Gain Conversion (HGC). Only use it in the HGC range unless you have major saturation problems with bright stars.

Do not use unity gain or low gain. It will be noisy, and the low signal level with MONO16 will confuse TANGRA.

### ROI - Region of Interest, tilt and pan
Reduce the ROI to around 0.2 deg. This is a good FOV for most occultation work.

If you don't have tracking and are doing prepoint or drift through you may need to use thr full sensor size. But it will greatly increase the file size and reduce the max frame rate.

Tilt and pan usually don't matter, but you MUST use the same tilt and pan settings as you have calibrated the camera acqusition delays.

Sometimes when doing Lunar occultations adjusting tilt and pan can help avoid glare.

### USB Settings
Different cameras will have different USB settings available. In general, avoid using the max speed as this leaves little room in the buffer for problems

If there is a TUrbo or High Speed mode than use it.

Set the frame rate limit to maximum

Test the USB settings with 1 ms exposures and check the frame rate in the status bar. Find out which settings are higher speed so you know how they work.

Once you have decided on the USB settings don't change them, as it can affect the timing.

### Pre-Processing - Turn it all off!
Turn off ALL preprocessing as it will slow your recording and could affect timing, and will also mess with the recorded data. No darks, flats, gradient rmoval etc.

You can apply darks and flats in post processing in TANGRA or PyMovie if necessary. It is not usually necessary for occultations

### Graphics Card
SharpCap has an option to use the Graphics card for screen display (not video processing). Not usually necessary but you can turn it on if your display is not keeping up or if you having processing load issues.




