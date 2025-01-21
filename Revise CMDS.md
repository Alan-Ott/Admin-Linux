


kill -s 15 process Id
kill all

systemctl nginx

systemctl status nginx.service
 -can find file location

crontab 

vi script.sh

crontab -e 
	-run a script every x(minutes hours days months)


```bash
goyeir@codevif:~$ cd /dev
goyeir@codevif:/dev$ df -hl
Filesystem      Size  Used Avail Use% Mounted on
tmpfs           1.6G  2.5M  1.6G   1% /run
/dev/nvme0n1p4  144G   34G  103G  25% /
tmpfs           7.7G  2.3M  7.7G   1% /dev/shm
tmpfs           5.0M   12K  5.0M   1% /run/lock
efivarfs        192K  124K   64K  66% /sys/firmware/efi/efivars
/dev/nvme0n1p1  256M   71M  186M  28% /boot/efi
tmpfs           1.6G   10M  1.6G   1% /run/user/1000
goyeir@codevif:/dev$ du -hl
0	./dri/by-path
0	./dri
0	./v4l/by-path
0	./v4l/by-id
0	./v4l
du: cannot read directory './vboxusb': Permission denied
0	./vboxusb
0	./snd/by-path
0	./snd
0	./vfio
0	./cpu/15
0	./cpu/14
0	./cpu/13
0	./cpu/12
0	./cpu/11
0	./cpu/10
0	./cpu/9
0	./cpu/8
0	./cpu/7
0	./cpu/6
0	./cpu/5
0	./cpu/4
0	./cpu/3
0	./cpu/2
0	./cpu/1
0	./cpu/0
0	./cpu
0	./mqueue
0	./hugepages
0	./shm
0	./usb
0	./bsg
0	./block
0	./disk/by-label
0	./disk/by-uuid
0	./disk/by-partlabel
0	./disk/by-partuuid
0	./disk/by-path
0	./disk/by-id
0	./disk/by-diskseq
0	./disk
0	./bus/usb/004
0	./bus/usb/003
0	./bus/usb/002
0	./bus/usb/001
0	./bus/usb
0	./bus
0	./char
0	./pts
0	./mapper
0	./input/by-id
0	./input/by-path
0	./input
0	./net
0	./dma_heap
0	.

```

/dev/nvme0n1p4

/dev/vda1
	-disk 1 partition 1
/dev/vda2
	-disk 1 partition 2
/dev/vdb1
	-disk 2 partition 1
/dev/vdb2
	-disk 2 partition 2

```bash
sudo lsblk
NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
loop0         7:0    0     4K  1 loop /snap/bare/5
loop1         7:1    0  74.2M  1 loop /snap/core22/1122
loop2         7:2    0  74.2M  1 loop /snap/core22/1380
loop3         7:3    0 240.5M  1 loop /snap/firefox/3216
loop4         7:4    0 270.7M  1 loop /snap/firefox/4259
loop5         7:5    0  10.7M  1 loop /snap/firmware-updater/121
loop6         7:6    0  10.7M  1 loop /snap/firmware-updater/127
loop7         7:7    0   497M  1 loop /snap/gnome-42-2204/141
loop8         7:8    0 505.1M  1 loop /snap/gnome-42-2204/176
loop9         7:9    0  91.7M  1 loop /snap/gtk-common-themes/1535
loop10        7:10   0  10.2M  1 loop /snap/snap-store/1110
loop11        7:11   0  10.4M  1 loop /snap/snap-store/1134
loop12        7:12   0  39.1M  1 loop /snap/snapd/21184
loop13        7:13   0  38.7M  1 loop /snap/snapd/21465
loop14        7:14   0   476K  1 loop /snap/snapd-desktop-integration/157
loop15        7:15   0   452K  1 loop /snap/snapd-desktop-integration/83
sda           8:0    1     0B  0 disk 
nvme0n1     259:0    0 476.9G  0 disk 
├─nvme0n1p1 259:1    0   260M  0 part /boot/efi
├─nvme0n1p2 259:2    0    16M  0 part 
├─nvme0n1p3 259:3    0   330G  0 part 
└─nvme0n1p4 259:4    0 146.6G  0 part /var/snap/firefox/common/host-hunspell
```




### partition disks

```bash
su root



```