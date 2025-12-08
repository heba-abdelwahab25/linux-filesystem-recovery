## Incident Recovery: Directory Hidden my Mounted Filesystem
This phase demonstrates the recovery of the directory ('d_harddrive') that was hidden due to an accidental overlay of a new filesystem on top of the original directory. The goal is to practice safe recovery techniques for the incident we've recreated in the v1.0-incident-recreation section without harming the original data on my/your system.
**Note:** The original directory is **not deleted**, only hidden when the overlaying filesystem is mounted. Recovery is performed from a **backup disk image** to ensure safety.


**0. Backup Preparation**
Before starting the recovery process, we create a backup of the original disk image ('sdaX.img') to ensure data integrity.
![backup-image.img](screenshots/00-backup-image.jpeg)


**1. Attach the Disk Image as a loop Device**
We attach the backup disk image to a loop device using *losetup*. This allows us to interact with it as if it were a real block device.
```losetup -fP sdaX_backup.img```
![loop-setup.img](screenshots/01_Loop_setup.jpeg)

**2. Map the Partition**
We use ```kpartx``` to create device mappings for the partitions inside the disk image. This maps each partition to */dev/mapper/*.
![kpartx-mapping.img](screenshots/02_kpartx_mapping.png)

**3. Check Filesystem Consistency**
Before mounting, we perform a read-only filesystem check using ```fsck.ext4``` to verify that the partition is clean.
![fsck-readonly.img](screenshots/03-fsck-readonly-check.png)

**4. Mount the Partition in Read-Only Mode**
To safely access the hidden directory without risk of modifying it, we mount the mapped partition read-only.
![read-only.img](screenshots/04_readonly_mount.png)
![MP.img](screenshots/MP.png)

**5. Explore the Hidden Directory**
We recursively list the hidden directory to verify the contents.
![data-visibility.img](screenshots/05data_visibl.png)


**6. Copy Recovered Data**
We safely copy the hidden directory to a local recovery folder to work with it without modifying the original image.
![copy-recovered.img](screenshots/06-copy_recovered_files.png)
![verify-recovery.img](screenshots/07-verify_recovery.png)

**7. Clean Up Mounts and Mappings**
After recovery, we unmount the partition and remove the loop device mappings to avoid accidental modifications.
![cleanUp.img](screenshots/08-cleanUp.png)

##⚠️ Things I have avoided while recoverying and recreation for the incident ⚠️##
These steps were only for learning purposes and to avoid having a tragic learning practice XD. I**Never** apply these steps to real disks.
- Always work on a disk image or backup.
- Use read-only mounts for verification whenever possible.
- Keep clear backups before performing destructive commands like 'mkfs' or 'mount --bind'.
- Follow the steps in the v1.0-incident-recreation branch for exact commands and screenshots.

