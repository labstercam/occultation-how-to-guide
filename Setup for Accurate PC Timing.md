# Setup for Accurate PC Timing

Windows PCs require setup for hardware, software and user operation so that the timestamps of recording have the best possible accuracy.

The Windows (TM) operating systems is not a real-time operating system, so all processes are run via a scheduler which manages competing processes and tasks and allocates resources such as RAM, CPU and USB traffic when they are available. For example, when a USB frame is sent from the camera the USB hub has to manage all competing traffic or processes before it can receive the frame. It is only made available to the recording software (e.g. SharpCap) once it has started processing the frame. These will cause delays in processing, and if the system has too many competing processes these delays can become large and unpredictable.
   ### If NOT set up properly there could be MAJOR problems with the recordings, with a lot of dropped frames, late frames, and inaccurate timestamps. This could give unusable recordings or incorrect event times.

## Tools for Analysing PC Performance and Timestamp Delays
**Occultation Manager** has a built in tool to check timestamp performance under load. Open from the **Tools | Open PC Performance Testing** menu. It gives a live display of the time between frames and shows the PC load so that you can test to see what happens when you have other programs running, or competing hardware, or operating the PC. Experiment with the camera settings and with the competing processes to determine what settings give you good timestamp performance, and which cause problems.

Here is an example of excellent timestamp performance. There is timestamp jitter of +/- 1 ms which is mainly just rounding to 1 millisecond by SharpCap.

<img width="1055" height="375" alt="image" src="https://github.com/user-attachments/assets/35fef485-07e3-45de-b11b-b6fd39395584" />

Here is an example of poor timestamp performance, with Stellarium running, and playing a video in Tangra. There is no evidence of dropped frames here (would need to be 50 ms gap) but it can get much worse than this

<img width="1065" height="382" alt="image" src="https://github.com/user-attachments/assets/1831b321-98c9-4f29-af9f-4f48f0d8802f" />

[LatencyMon](https://www.resplendence.com/latencymon) is a program that analyses latencies in Windows processes and can help to identify processes or devices causing excessive latency.

## Main causes of Windows PC timing performance issues

The main causes of problems with timestamping are:
1. Running the camera at too high a frame rate for the camera settings
2. Other programs with heavy CPU or memory demands (e.g. Chrome/Edge/Firefox browsers, Stellarium etc)
3. Devices competing with the USB host controller - other USB devices, WiFi adapters and other devices
4. The observer messing around with the keyboard, mouse, swapping windows etc whilst recording.
5. High internet traffic (e.g. videos, video calls, screen sharing or remote access)
6. Windows power saving, performance and sleep settings
7. SharpCap priority
   
Don't be alarmed by this list - when setup and operated properly these issues can be minimised or eliminated to ensure reliable timestamping. Specific guidance is provided below

**The general principle is to minimise load on the PC and only operate hardware and programs that are necessary for the actual recording**

## 1. Choose Conservative Camera Settings and Frame Rate
If the camera is run at too high a frame rate for the camera settings the USB interface may be unable to keep up and you may get dropped or late frames or delayed timestamps.

See [Camera Settings for Occultations](https://github.com/labstercam/occultation-how-to-guide/blob/main/SharpCap.md#camera-setup-for-occultations) for recommendations on camera settings and max frame rate

The recommended maximum frame rate is 1/3 the maximum frame rate for you camera settings.

Use USB 3 ports to connect cameras. Most modern laptops and PCs only have USB3.0 ports, but low spec or older PCs may have some USB 2 ports. USB 3 ports have the trident symbol + SS (SuperSpeed) mark. USB 2 ports only have the trident symbol. When connected in SharpCap the top Windows bar will display USB2 or USB3, as seen below.

<img width="473" height="42" alt="image" src="https://github.com/user-attachments/assets/d49aa5c4-ead1-4c65-9e91-3dcd05b477ca" />

If you use a low quality or damaged cable with a USB3 port it may revert to a USB2 connection

## 2. Close Programs with heavy CPU or Memory load
Programs that make heavy use of CPU or Memory compete with SharpCap and USB and will cause unstable timestamps and dropped frames. 

The **WORST** programs for high load are:
1. Browsers (Chrome, Edge etc). Even a single browser tab can consume 1 GB of RAM
2. Stellarium and other planetarium software
3. Microsoft Office applications - Word, Outlook etc
4. Video playback, Video calls or screen sharing and Remote PC access
7. Anti-virus scans

Only run your recording software (SharpCap) and programs that are actually required during the recording. If you are using remote PC access then adjust settings to minimise the load.

You can see how much CPU and RAM programs are using using the Task Manager and the total load. Right click on the Start Menu icon or bar and select 'Task Manager'. The Processes tab lists all programs running. Click on CPU or Memory column to see the top consumers, and prioritise closing the top consumers.

If the total CPU or RAM load is approaching or hitting 100% then bad things will happen, with potentially long delays waiting for the CPU, or programs paging to the SSD/Hard drive rather than RAM memory. This is **CATASTROPHIC** for the recording timestamps. It is easily avoided by closing programs you don't need.

## 3. Reduce impact of competing hardware
Disconnect or disable other USB devices that are not needed, especially cameras.

WiFi, Bluetooth and external Ethernet adapaters may share the USB contoller. If you do not need them then turn them off or disconnect, or configure them to reduce the impact.

### WiFi

If you don't need WiFi then turn it off. Use Ethernet instead if you can.

**WiFi adapter power saving is one of the main causes of hardware interupts which can affect timing**. When power saving is on the WiFi it constantly switching on and off, causing hardware interrupts and latency.

To turn off WiFi power saving:
1. Right-click the Windows Start button and select Device Manager.
2. Expand the Network adapters section.
3. Right-click your wireless adapter (for example, Intel Wi-Fi 6 AX200 or MediaTek Wi-Fi 6) and select Properties.
4. Click the Power Management tab at the top and uncheck Allow the computer to turn off this device to save power.
5. Click OK to save.

If these settings are not available you may have a more modern WiFi hardware. Do an AI search for how to turn off WiFi power management.

There are various other WiFi settings that could affect performance, but they may differ between devices. If you still have problems then do you own research.

### Bluetooth
Turn it off if you don't need it

## 4. Don't mess around with the PC whilst recording
User interaction such as moving the mouse, typing, swapping windows or tabs, or clicking the Windows Start button create bursts of activity and bursts of USB traffic. These can cause temporary small delays to frame timestamps, usually only a few milliseconds but can be much larger.

So don't mess with the PC whilst record - just leave it alone.

## 5. High Internet Traffic
High internet traffic through WiFi may compete with the USB interface, causing competition for the camera. Ethernet should not compete with USB, but will add processing load. 

Internet Video, Video Calls and remote PC access will increase WiFi traffic and processing load. If you have to use them, adjust the settings to reduce video resolution and data traffic

Minimise internet traffic during recordings.

## 6. Windows power saving, performance and sleep settings
Set your PC up to use maximum performance, disable power saving and sleep settings. Always use a laptop plugged in if you can.

Any time the PC changes a power or sleep setting mode (e.g. turning the screen on or off) it triggers a state change and a burst of activity that can affect timestamps.


## 7. SharpCap Priority
SharpCap by default is run with normal priority. Yuu can check the priority in the Windows Task Manager, Details tab.

Setting SharpCap to High priority makes Windows prioritise SharpCap and will reduce delays caused by competing processes. You can set this for SharpCap using Task Manager. Go to the Details tab, search for SharpCap, Right Click and click 'Set Priority' and choose 'High'. Do NOT choose 'Real Time' as this can cause problems. Do NOT Set Affinity for SharpCap as this will hurt performance.

SharpCap can be permanently set to use High priority by making changes to the Windows Registry. This can be done using the following Windows PowerShell commands

```
# Run this in an ELEVATED PowerShell (Administrator) - it writes to HKLM.
$exe  = 'SharpCap.exe'
$ifeo = "HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\$exe"

New-Item -Path "$ifeo\PerfOptions" -Force | Out-Null

# CpuPriorityClass: 1=Idle 2=Normal 3=High 4=RealTime 5=BelowNormal 6=AboveNormal
New-ItemProperty -Path "$ifeo\PerfOptions" -Name CpuPriorityClass -Value 3 -PropertyType DWord -Force | Out-Null
# (also set directly on the key, for Windows builds that read it there)
New-ItemProperty -Path  $ifeo            -Name CpuPriorityClass -Value 3 -PropertyType DWord -Force | Out-Null

Write-Host "SharpCap.exe set to High priority. Restart SharpCap to apply."
```
To run this code:
1. Copy the code snippet above
2. Click the Windows Start Button and start typing Powershell. Windows Powershell should appear in the menu
3. Select 'Run as Administrator'. If you don't have administrator access you will need an admin to do if for you
4. Right Click anywhere in the Windows Powershell window to paste the code
5. Press enter
6. Restart SharpCap

