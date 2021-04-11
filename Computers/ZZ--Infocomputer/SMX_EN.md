## MSX-X + smx improvements

#### Core by @NeuroRulez

---------------------------------


Using the ready image

Unzip the ./sdimg/SD_SM-X.ZIP file to get the SD_SM-X.img file.

Use Etcher or Win32DiskImager to save this image to an SD card (minimum 1Gb).

After recording, copy the file "SM-X.MCP" to the root of the card. Rename it to "core.np1" if you want automatic startup.

Generating from sdcreate

In the directory ./sdcreate there are 2 scripts, one for Windows and one for Linux, to
generate an SD card using its full capacity (up to the maximum size of
a FAT16 partition: 4GB)

More information in the README file inside the directory ./sdcreate