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

