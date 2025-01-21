#### 3 USB Info
```bash
> sudo blkid

/dev/sdb1: LABEL_FATBOOT="DISK_IMG" LABEL="Lexar" UUID="005E-E323" BLOCK_SIZE="512" TYPE="vfat" PARTUUID="005ee323-01"

/dev/sdc1: LABEL_FATBOOT="DISK_IMG" LABEL="Lexar" UUID="054D-0333" BLOCK_SIZE="512" TYPE="vfat" PARTUUID="054d0333-01"

/dev/sdd1: LABEL_FATBOOT="DISK_IMG" LABEL="Lexar" UUID="0092-046E" BLOCK_SIZE="512" TYPE="vfat" PARTUUID="0092046e-01"


> lsblk

sda           8:0    1     0B  0 disk 
sdb           8:16   1 116.1G  0 disk 
└─sdb1        8:17   1 116.1G  0 part /media/goyeir/Lexar
sdc           8:32   1 116.1G  0 disk 
└─sdc1        8:33   1 116.1G  0 part /media/goyeir/Lexar1
sdd           8:48   1 116.1G  0 disk 
└─sdd1        8:49   1 116.1G  0 part /media/goyeir/Lexar2


> sudo fdisk -l

Disk /dev/sdb: 116.11 GiB, 124675686400 bytes, 243507200 sectors
Disk model: USB Flash Drive 
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x005ee323

Device     Boot Start       End   Sectors   Size Id Type
/dev/sdb1  *       64 243507199 243507136 116.1G  b W95 FAT32


Disk /dev/sdc: 116.11 GiB, 124675686400 bytes, 243507200 sectors
Disk model: USB Flash Drive 
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x054d0333

Device     Boot Start       End   Sectors   Size Id Type
/dev/sdc1  *       64 243507199 243507136 116.1G  b W95 FAT32


Disk /dev/sdd: 116.11 GiB, 124675686400 bytes, 243507200 sectors
Disk model: USB Flash Drive 
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x0092046e

Device     Boot Start       End   Sectors   Size Id Type
/dev/sdd1  *       64 243507199 243507136 116.1G  b W95 FAT32

> df -l

/dev/sdb1      121720768       32 121720736   1% /media/goyeir/Lexar
/dev/sdc1      121720768       32 121720736   1% /media/goyeir/Lexar1
/dev/sdd1      121720768       32 121720736   1% /media/goyeir/Lexar2


```

// FORMATTED 3 USB's

#### VG LV
```bash
$ sudo apt install -y lvm2

$ lsblk

sdb           8:16   1 116.1G  0 disk 
sdc           8:32   1 116.1G  0 disk 
sdd           8:48   1 116.1G  0 disk 

$ sudo pvcreate /dev/sdb

$ sudo pvdisplay
  "/dev/sdb" is a new physical volume of "116.11 GiB"
  --- NEW Physical volume ---
  PV Name               /dev/sdb
  VG Name               
  PV Size               116.11 GiB
  Allocatable           NO
  PE Size               0   
  Total PE              0
  Free PE               0
  Allocated PE          0
  PV UUID               YBo26p-GwRD-fS60-EcEF-0CyP-AMiS-464DE7

$ sudo vgcreate vg-Lexi /dev/sdb
  Volume group "vg-Lexi" successfully created

$ sudo pvs
  PV         VG      Fmt  Attr PSize    PFree   
  /dev/sdb   vg-Lexi lvm2 a--  <116.11g <116.11g

$ sudo vgdisplay
  --- Volume group ---
  VG Name               vg-Lexi
  System ID             
  Format                lvm2
  Metadata Areas        1
  Metadata Sequence No  1
  VG Access             read/write
  VG Status             resizable
  MAX LV                0
  Cur LV                0
  Open LV               0
  Max PV                0
  Cur PV                1
  Act PV                1
  VG Size               <116.11 GiB
  PE Size               4.00 MiB
  Total PE              29724
  Alloc PE / Size       0 / 0   
  Free  PE / Size       29724 / <116.11 GiB
  VG UUID               MhEIEp-R5lg-0NJk-NsrW-LFdZ-D2py-GbXVfd

$ sudo lvmdiskscan
  /dev/nvme0n1p1 [     260.00 MiB] 
  /dev/loop1     [      74.21 MiB] 
  /dev/nvme0n1p2 [      16.00 MiB] 
  /dev/loop2     [     <74.24 MiB] 
  /dev/nvme0n1p3 [     330.02 GiB] 
  /dev/loop3     [    <240.51 MiB] 
  /dev/nvme0n1p4 [    <146.65 GiB] 
  /dev/loop4     [     270.74 MiB] 
  /dev/loop5     [     <10.69 MiB] 
  /dev/loop6     [     <10.72 MiB] 
  /dev/loop7     [     496.98 MiB] 
  /dev/loop8     [    <505.09 MiB] 
  /dev/loop9     [     <91.69 MiB] 
  /dev/loop10    [     <10.25 MiB] 
  /dev/loop11    [     <10.36 MiB] 
  /dev/loop12    [      38.73 MiB] 
  /dev/loop13    [     <39.10 MiB] 
  /dev/sdb       [     116.11 GiB] LVM physical volume
  /dev/sdc       [     116.11 GiB] 
  /dev/sdd       [     116.11 GiB] 
  2 disks
  17 partitions
  1 LVM physical volume whole disk
  0 LVM physical volumes

$ sudo vgextend vg-Lexi /dev/sdc
  Volume group "vg-Lexi" successfully extended

$ sudo vgextend vg-Lexi /dev/sdd
  Volume group "vg-Lexi" successfully extended

$ sudo vgdisplay
  --- Volume group ---
  VG Name               vg-Lexi
  System ID             
  Format                lvm2
  Metadata Areas        3
  Metadata Sequence No  3
  VG Access             read/write
  VG Status             resizable
  MAX LV                0
  Cur LV                0
  Open LV               0
  Max PV                0
  Cur PV                3
  Act PV                3
  VG Size               <348.33 GiB
  PE Size               4.00 MiB
  Total PE              89172
  Alloc PE / Size       0 / 0   
  Free  PE / Size       89172 / <348.33 GiB
  VG UUID               MhEIEp-R5lg-0NJk-NsrW-LFdZ-D2py-GbXVfd

$ sudo lvcreate -n Volume -L 1g vg-Lexi
  Logical volume "Volume" created.

$ sudo lvdisplay
  --- Logical volume ---
  LV Path                /dev/vg-Lexi/Volume
  LV Name                Volume
  VG Name                vg-Lexi
  LV UUID                zKzi03-pGpZ-pT9W-Ektq-WLmB-DKbK-PvZg1s
  LV Write Access        read/write
  LV Creation host, time codevif, 2024-05-22 12:15:43 +0200
  LV Status              available
  # open                 0
  LV Size                1.00 GiB
  Current LE             256
  Segments               1
  Allocation             inherit
  Read ahead sectors     auto
  - currently set to     256
  Block device           252:0

$ sudo mkfs.ext4 /dev/vg-Lexi/Volume
mke2fs 1.47.0 (5-Feb-2023)
Creating filesystem with 262144 4k blocks and 65536 inodes
Filesystem UUID: 38dfa747-d599-4b5d-8dc3-6113bb4806e3
Superblock backups stored on blocks: 
	32768, 98304, 163840, 229376

Allocating group tables: done                            
Writing inode tables: done                            
Creating journal (8192 blocks): done
Writing superblocks and filesystem accounting information: done

$ sudo mkdir -p /mnt/lvm/lv-Volume001
$ sudo mount /dev/vg-Lexi/Volume /mnt/lvm/lv-Volume001

$ df -hl
Filesystem                   Size  Used Avail Use% Mounted on
tmpfs                        1.6G  2.6M  1.6G   1% /run
/dev/nvme0n1p4               144G   46G   91G  34% /
tmpfs                        7.7G  2.2M  7.7G   1% /dev/shm
tmpfs                        5.0M   12K  5.0M   1% /run/lock
efivarfs                     192K  124K   64K  66% /sys/firmware/efi/efivars
/dev/nvme0n1p1               256M   71M  186M  28% /boot/efi
tmpfs                        1.6G  5.6M  1.6G   1% /run/user/1000
/dev/mapper/vg--Lexi-Volume  974M   24K  907M   1% /mnt/lvm/lv-Volume001

$ sudo lvdisplay
  --- Logical volume ---
  LV Path                /dev/vg-Lexi/Volume
  LV Name                Volume
  VG Name                vg-Lexi
  LV UUID                zKzi03-pGpZ-pT9W-Ektq-WLmB-DKbK-PvZg1s
  LV Write Access        read/write
  LV Creation host, time codevif, 2024-05-22 12:15:43 +0200
  LV Status              available
  # open                 1
  LV Size                1.00 GiB
  Current LE             256
  Segments               1
  Allocation             inherit
  Read ahead sectors     auto
  - currently set to     256
  Block device           252:0

$ sudo lvextend -n /dev/vg-Lexi/Volume -L +9g
  Size of logical volume vg-Lexi/Volume changed from 1.00 GiB (256 extents) to 10.00 GiB (2560 extents).
  Logical volume vg-Lexi/Volume successfully resized.

$ sudo resize2fs /dev/mapper/vg--Lexi-Volume
resize2fs 1.47.0 (5-Feb-2023)
Filesystem at /dev/mapper/vg--Lexi-Volume is mounted on /mnt/lvm/lv-Volume001; on-line resizing required
old_desc_blocks = 1, new_desc_blocks = 2
The filesystem on /dev/mapper/vg--Lexi-Volume is now 2621440 (4k) blocks long.

$ df -hl
Filesystem                   Size  Used Avail Use% Mounted on
tmpfs                        1.6G  2.6M  1.6G   1% /run
/dev/nvme0n1p4               144G   46G   91G  34% /
tmpfs                        7.7G  2.7M  7.7G   1% /dev/shm
tmpfs                        5.0M   12K  5.0M   1% /run/lock
efivarfs                     192K  124K   64K  66% /sys/firmware/efi/efivars
/dev/nvme0n1p1               256M   71M  186M  28% /boot/efi
tmpfs                        1.6G  5.7M  1.6G   1% /run/user/1000
/dev/mapper/vg--Lexi-Volume  9.9G   24K  9.4G   1% /mnt/lvm/lv-Volume001

```

#### Gestion des volumes de stockage
###### Ajouter d’autres pv à un vg

• sudo vgextend vg-test /dev/sdc
• sudo vgextend vg-test /dev/sdd
• sudo vgextend vg-test /dev/sde

###### Ajouter un espace supplémentaire à un volume logique

• sudo lvextend -L+10g /dev/vg-test/myvol
// ajout de 10go supplémentaire à myvol1. on peut aussi écrire 10GB
• sudo resize2fs /dev/vg-test/myvol1

###### Suppression des volumes avec LMV

• sudo lvremove vg-test/myvol
• sudo vgremove vg-test