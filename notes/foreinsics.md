sudo fdisk -l -> display patitions exists/ see disk partition table
sudo dd if=[location of the USB drive] of=[the destination of outputfile with extension of .img]
ex- dd if=/dev/sdb of=/home/homer/Desktop/test.img