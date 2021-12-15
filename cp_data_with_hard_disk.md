# copy data from/to server with your mobile harddidk
If you find errors or better ways, I would appreciate your feedback.

## check information about server
You can find the documents in our Wechat group. 
Look for where the server is, and the sticker on each server shall help you recognize your server.

## connect your harddisk
I think you have a wire for USB

## login the server
+ login with the human interface devices in the machine room 
+ login with ssh (recommended)
```
sudo -s # if you have admin's right
```

## check the harddisks connected to the server
+ fsidk -l (-u)
+ lsblk

notes:
+ both commands can works
+ you may recognize your harddisk with its capability or compare the output with mounted disks(df -h)

## make a new directory and mount your harddisk
```
mkdir new_dir
mount /dev/sdb1 new_dir # your harddisk might be /dev/sdb1 
```

note:
If the file system of harddisk wasn't safely closed on Windows, mount could fail.
In this situation, use lsblk to find the block of your harddisk, and mount the block.

## you can visit your harddisk the the directory new_dir
Play around as you like