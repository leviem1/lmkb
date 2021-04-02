# Creating a File of a Specific Size in Linux

Creating a large file may be needed in various test scenarios. Here's how to do so in Linux.

`fallocate -L <size> <filename>`

Alternative:

`dd if=/dev/zero of=<filename> bs=4k iflag=fullblock,countbytes count <size>`