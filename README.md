# (This location could not be displayed error) linux-filesystem-recovery
This project documents a real-world incident where a 600GB directory became inaccessible after mounting another filesystem over it, followed by accidental writes, resulting in major data loss. This repo presents my experience, recovery techniques and lessons learned.

![Mount Error](images/mount_error.png)

----------------------------------------------------------------------------------------------------------------------------------------
Each branch and Directory represents a different phase of the learning and recovery process:

├──**v1.0-Incident-receation**: Steps and screenshots recreating the incident for safe learning purposes. as I started this repo after

│                               recovering the incident, I needed to simulate it.

│   ├── *README.md*: presents the steps taken, screenshots from the terminal.

│

│   ├──*commands.txt*: commands used.

│   └── *screenshots*: collection of clear screenshots taken from the terminal for the inputs and outputs.

├──**v1.1-Incident-recovery**: Recovery process of the hidden directory from the backup disk image, including commands, logs, and 

│                               screenshots. -the same where taken for the real incident-

│   ├──*README.md*: presents the steps taken for recovery, screenshots from the terminal.

│   ├──*logs*: Optional raw text logs from the recovery process, Screenshots in the README document the main steps, so these logs  

│             are provided for completeness and later review if needed.

│   └──*screenshots*: Contains images captured during each step of the recovery or incident recreation.

│

└──**v1.2-testdisk**: testdisk is a free open source recovery tool was super useful and supportive through the incident.

   └──*README.md*: this documents beneficial infomation about the tool and how it was used in the incident.
