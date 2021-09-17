# Creating a File of a Specific Size in Linux

Creating a large file may be needed in various test scenarios. Here's how to do so in Linux.

`fallocate -L <bytes> <filename>`

Alternative:

`dd if=/dev/zero of=<filename> bs=4k iflag=fullblock,count_bytes count=<bytes>`
