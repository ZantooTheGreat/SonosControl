# SonosControl
Taken from /r/sysadmin


After coming into the office and hearing ABBA blasting across the room for the 50th time, I'd had enough. Surely someone has written a script that can communicate with the SONOS across the network so I don't have to keep whipping my phone out to set volume levels to something acceptable??

Cue this gem - https://gallery.technet.microsoft.com/SONOS-PowerShell-500c9878

I used this script as a base, and edited it to support the 'GetVolume' command, as well as supporting multiple devices read from an external CSV file.

Each device has a Name, IP, and VolumeLimit. When you run the script with the -auto switch, it polls the devices on the network every 10 seconds, and checks if the device is above the volume level set in the CSV file. If the volume is above the specified maximum, it immediately hits the endpoint to set the volume back down to the limit. I've set a limit for the main office to "just above background noise", and for the break room the limit is zero.

The script is working perfectly and has already saved us from bleeding ears a few times this week. Whoever has been turning it up hasn't mentioned that the volume control doesn't seem to work anymore...
