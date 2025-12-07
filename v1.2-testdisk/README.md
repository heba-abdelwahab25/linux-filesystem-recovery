In this branch, I document my experience using the amazing free recovery tool *TestDisk* to analyze and recover hidden or lost data, including lost partitions and file system structures.
Steps Taked:
1. install testdisk, I use linux so I intalled it using the terminal *sudo apt upadate* --> *sudo apt install testdisk*
2. I ran testdisk using: *sudo testdisk*, sometimes I recieve a warning that tells something like *testdisk requires a terminal with at least 24 lines*, this was solved by resizing the terminal window to make it taller.
3. I selected  *Create* to start a new log file.
4. select one of the listed disk, in my case I chose sda as I know that the lost data where mounted from sda, then pressed enter to proceed.
5. select the partition table type, in my case I selected *intel*, checking the disk's partition table can be done by running: *sudo parted /dev/"DISKNAME" print*, then pressed enter to proceed.
6. in this step I started to analysis the partition structure, the testdisk offered a *Quick search* feature to scan the disk for existing and deleted partitions for sda.
7. I identified the partition that probably included the hidden data I stopped the search to avoid unnecessary scanning.
8. I started to explore the partition, navigated into that partition and pressed p to list the files and make sure they are the ones I am looking for.
9. testdisk displayed all recoverable files and provided options to recover either specific files or the entire list.
10. I was able to view and verify the hidden files before deciding whether to copy them.
**⚠️ Important Safety Note**
I learned a very important safety note in the recoverying step:
*NEVER* recover files to their old or original path, always recovery them to a separate directory, as copying to the original location could overwrite hidden or partially recovered files, this causes permanent data loss. working on a separate path ensures the original disk or backup image remains intact for further analysis.
