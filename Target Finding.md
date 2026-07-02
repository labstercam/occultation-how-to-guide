# Target Finding
## Or how not to be Lost In Space!!

One of the most challenging tasks for new observers is finding the target star. These are often faint, in the mag 13-16 range, and if in the Milky Way may be in a very crowded field.

Plate Solving is the best way to find target stars. This uses software built into SharpCap (recommended) or other tools to analyse a frame and determine its exact RA/DEC coordinates, orientation (rotation) and field of view.

You can use Plate Solving even if you do not have a computerised or GOTO mount.

## Plate Solving with a Computerised GOTO Mount

A computerised GOTO mount is connected to you PC and is controlled by SharpCap. It will point wherever you want it to go and will plate-solve and if necessary resync to get exactly on target, even if you mount is not accurately aligned. This is the most convenient way to find targets.

Using Occulation Manager, the Observation Preparation panel allows you to load the event details, execute a GOTO, then plate solve to label the target star. Once complete the star is marked on screen and you know you are on target.

Using Occultation Manager automated sequences, you can set up the GOTO and platesolve to automatically centre the target star, and there are sequence code examples to also label the star.


## Finding targets with a well aligned non-computerised mount
If you have a permanent mount or a very well aligned mount that points to better than 0.1 deg anywhere in the sky then you can just go to the target coordinates and do a minor adjustment without plate solving

## Plate Solving with non-computerised tracking mounts
For non-computerised mounts that track you can use SharpCap Push-To assistant to find the target using plate solving.

First, in Occulation Manager select and event and press 'Load Event'. This will copy the coordinates to the clipboard. Now open Tools | Push To Assistant, and paste the coordinates there. It will tell you the ALT-AZ position.

Move the telescope to that ALT-AZ region of the sky so you are not a long way away, or you could manually enter the coords into the hand controller to get you close.

Then press 'Start' in Sharpcap and it will plate solve and tell you which direction to move the mount, in EQ or ALT-AZ directions. Move the mount and it will keep plate solving automatically.

If it loses the plate solve and doesn't find it again quickly, press 'Stop' and then 'Start' again. This can happen with smaller FOV.

If you have a guidescope with camera you can use it for the Push To Assistnat to get close to target, then do a final plate solver using your main scope.But make sure you change the focal length between them!

Once you are very close to target (< 0.1 deg away) you should be able to see the target star. Press 'Plate Solve' in Occultation Manager to label it.

## Plate Solving with non-tracking or fixed mouonts
If using a non-tracking mount or dobsonian then the mount needs to be pre-pointed so the target star will move into the center of the FOV at the event time.

Pre-pointing will be added to Occultation Manager soon.

Currently you can use Occult4 to calculate bright target stars to pre-point to, and use the plate solving to find them.

## Finding the Star Later On for Analysis

Once you have done the observation and come to analyse the recording you have to identify the target star. If you have saved an image before recording with the target star annotation then great, otherwise you will have to find it again.

If you have used GOTO/Plate solve and have a computerised mount it should be near the center and may be obvious if it is a bright star.

Otherwise you will need to check against the star field online image or Occult 4 star chart. To see the star field from Occultation Manager, click on the event name and it will open Occult Cloud pages including the 0.5 deg FOV image with the star marked. If you can match the star, then great. If your FOV is different you can manually edit the URL address to change the FOV. If the rotation is not the same (North is up) it can be challenging to visualise the stars.

Occult 4 has excellent star charts available. You can access these through Occult Watcher Desktop, right click on the event and select 'Open Event in Occult'. This opens a world map and information panel. Click on the icon that looks like a small star image and a star chart iwll pop up. This can have the size and rotation adjusted, and be made transparent to overlap your image.

## Tip for Easier star finding
If you have an EQ mount then adjust your camera rotation so that North is Up. When you plate solve in SharpCap it will tell you the orientation. Make it close to 0, say 358 through 2 degrees. Once you know the orientation remember it so you can set it again later. On an SCT it is usually lined up with the focus knob.

## Tips for Mount setup and plate solving
You do not need an accurately aligned mount to plate solve and find targets. Accurate alignment mainly affects your tracking and means the target star will drift out of field eventually.

For an EQ mount if you set it up in the same position each night, for example on a concrete driveway with tape marks for the legs, it should be aligned well enough to find and track stars without doing an accurate polar alignment each time. 

For an ALT-AZ mount it should be sufficently accurate to have the mount base level and then start the mount/scope with the telescope in the HOME (pointed N and level) or previously parked position. Tape marks on the ground for legs can help you set up in the same position each time.

These simple setup steps can save you a lot of time in setting up.

SharpCap can be used to align and sync a PC connected mount. It is usually as easy as point to a patch of sky well away from the N or S pole and press the Plate Solve and Sync button (next to the arrows on the mount direction arrows). One solve and sync is enough to plate solve and goto. Solving in more places around the sky will give more accurate alignment.






