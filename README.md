# forensics-cheatsheet

exif : show and edit metadata of images mainly jpeg
**Note** : [exif tags](https://exiftool.org/TagNames/EXIF.html)
for example:
`exif --tag=0x010F bild.jpg`
show Make metadata (Camera manufacturer)

`exif --tag=0x9003 bild.jpg`
show DateTimeOrignal Metadata

`exif --tag=0x9003 --set-value="2012:12:12 12:12:12" ifd=EXIF bild.jpg`
edit DateTimeOrignal metadata to a specific value

`stat file.txt`
show detailed info and metadata of a file

`touch -a -m -t 201212121212.12 test.txt`
changing access and modify time stamp to a specific value

Or for **Powershell**:
`(Get-Item test.txt).lastwritetime=$(Get-Date "12/12/2012 12:12 am")`
`(Get-Item test.txt).creationtime=$(Get-Date "12/12/2012 12:12 am")
`(Get-Item test.txt).lastaccesstime=$(Get-Date "12/12/2012 12:12 am")

Edit timestamp with Metasploit timestomp :
meterpreter > timestomp -h
print the help for timestomp

meterpreter > timestomp C:\\ -r
blank the timestamp recursively of a folder (here the C: drive)

##### Securing Hard-drive 
###### Data about connected devices
`dmesg | grep sda`
print the kernel messages (kernel ring buffer) with the word sda (meaning the drive number "a")

`modprobe usbmon`
Loads the usbmon kernel module to enable USB traffic monitoring.

`lsmod | grep usbmon` 
check the modules loaded and grap the info about usbmon module

`lsusb`
list usb devices

`lshw -businfo -class disk`
list hardware with the options -class disk; list all disks


`lshw -businfo -class storage`
list hardware with the options -businfo;print bus info. and the option -class storage print storage devices

`hdparm -I /dev/sda`
get/set SATA/IDE device parameters with the option -I; get identification info directly from the drive which is displayed in an expanded format.


