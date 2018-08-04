# img_stat

1. img_stat - Display details of an image file
root@kali:/tmp# img_stat /dev/sdb
IMAGE FILE INFORMATION
--------------------------------------------
Image Type: raw

Size in bytes: 15518924800

# mmls

2. mmls - Display the partition layout of a volume system  (partition tables)

root@kali:~# mmls -t list
Supported partition types:
	dos (DOS Partition Table)
	mac (MAC Partition Map)
	bsd (BSD Disk Label)
	sun (Sun Volume Table of Contents (Solaris))
	gpt (GUID Partition Table (EFI))

root@kali:~# mmls -t dos pendrive.dd
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000000061   0000000062   Unallocated
002:  000:000   0000000062   0015726591   0015726530   Linux (0x83)

# fdisk

3. fdisk - Manipulate disk partition table

-l, --list    List  the  partition  tables  for the specified devices and then
              exit.  If no devices are given, those mentioned in  /proc/parti‐
              tions (if that file exists) are used.

root@kali:~# fdisk -l /dev/sdb
Disk /dev/sdb: 14.5 GiB, 15518924800 bytes, 30310400 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0x245a2a06

# fsstat

4. fsstat - Display general details of a file system

root@kali:~# fsstat -o 63 /dev/sdb
FILE SYSTEM INFORMATION
--------------------------------------------
File System Type: NTFS
Volume Serial Number: F4B0A1E7B0A1B092
OEM Name: NTFS    
Volume Name: Dane
Version: Windows XP

METADATA INFORMATION
--------------------------------------------
First Cluster of MFT: 786432
First Cluster of MFT Mirror: 2
Size of MFT Entries: 1024 bytes
Size of Index Records: 4096 bytes
Range: 0 - 256
Root Directory: 5

CONTENT INFORMATION
--------------------------------------------
Sector Size: 512
Cluster Size: 4096
Total Cluster Range: 0 - 3788559
Total Sector Range: 0 - 30308479

$AttrDef Attribute Values:
$STANDARD_INFORMATION (16)   Size: 48-72   Flags: Resident
$ATTRIBUTE_LIST (32)   Size: No Limit   Flags: Non-resident
$FILE_NAME (48)   Size: 68-578   Flags: Resident,Index
$OBJECT_ID (64)   Size: 0-256   Flags: Resident
$SECURITY_DESCRIPTOR (80)   Size: No Limit   Flags: Non-resident
$VOLUME_NAME (96)   Size: 2-256   Flags: Resident
$VOLUME_INFORMATION (112)   Size: 12-12   Flags: Resident
$DATA (128)   Size: No Limit   Flags: 
$INDEX_ROOT (144)   Size: No Limit   Flags: Resident
$INDEX_ALLOCATION (160)   Size: No Limit   Flags: Non-resident
$BITMAP (176)   Size: No Limit   Flags: Non-resident
$REPARSE_POINT (192)   Size: 0-16384   Flags: Non-resident
$EA_INFORMATION (208)   Size: 8-8   Flags: Resident
$EA (224)   Size: 0-65536   Flags: 
$LOGGED_UTILITY_STREAM (256)   Size: 0-65536   Flags: Non-resident

# fls

5. fls - List file and directory names in a disk image

root@kali:~# fls -o 63 /dev/sdb
r/r 4-128-1:	$AttrDef
r/r 8-128-2:	$BadClus
r/r 8-128-1:	$BadClus:$Bad
r/r 6-128-4:	$Bitmap
r/r 7-128-1:	$Boot
d/d 11-144-4:	$Extend
r/r 2-128-1:	$LogFile
r/r 0-128-6:	$MFT
r/r 1-128-1:	$MFTMirr
r/r 9-128-8:	$Secure:$SDS
r/r 9-144-11:	$Secure:$SDH
r/r 9-144-14:	$Secure:$SII
r/r 10-128-1:	$UpCase
r/r 10-128-4:	$UpCase:$Info
r/r 3-128-3:	$Volume
d/d 37-144-1:	System Volume Information
-/r * 41-128-1:	asdasd.txt
d/d 256:	$OrphanFiles

-d - Display deleted entries only
-r - Recursively  display  directories.  This will not follow deleted directories, because it can't.

///////////////////////////////////////////////////////fls/////////////////////////////////////////////////////////////////

6. icat - Output the contents of a file based on its inode number.

root@kali:~# icat -o 63 /dev/sdb 41
asdasdasdasdsads

TEST TEST TEST

# ils

7. ils - List inode information

root@kali:/tmp# ils -o 63 /dev/sdb
class|host|device|start_time
ils|kali||1518033927
st_ino|st_alloc|st_uid|st_gid|st_mtime|st_atime|st_ctime|st_crtime|st_mode|st_nlink|st_size
41|f|0|0|1518006238|1518006224|1518006238|1518006224|777|1|34

-e - List every inode in the file system.
-m - Display the inode details in the format that the mactime program reads (replaces the ils2mac script from TCT)
-a - List only allocated inodes: these belong to files with at  least one  directory  entry  in  the file system, and to removed files
     that are still open or executing
     
root@kali:/tmp# ils -o 63 -m /dev/sdb > test.txt
md5|file|st_ino|st_ls|st_uid|st_gid|st_size|st_atime|st_mtime|st_ctime|st_crtime
0|<sdb-asdasd.txt-dead-41>|41|-/rrwxrwxrwx|0|0|34|1518006224|1518006238|1518006238|1518006224

root@kali:/tmp# mactime -b text.txt 
Wed Feb 07 2018 07:23:44       34 .a.b -/rrwxrwxrwx 0        0        41       <sdb-asdasd.txt-dead-41>
Wed Feb 07 2018 07:23:58       34 m.c. -/rrwxrwxrwx 0        0        41       <sdb-asdasd.txt-dead-41>

root@kali:/tmp# mactime -b text.txt -p /etc/passwd -g /etc/passwd
Wed Feb 07 2018 07:23:44       34 .a.b -/rrwxrwxrwx root     root     41       <sdb-asdasd.txt-dead-41>
Wed Feb 07 2018 07:23:58       34 m.c. -/rrwxrwxrwx root     root     41       <sdb-asdasd.txt-dead-41>

# MMLS ERROR
8. MMLS Error

Invalid sector address (dos_load_prim_table: Starting sector too large for image) 

You imaged the first partition (sdd1) of the physical disk (sdd).
That means your image does not contain the partition table that is in
the first sector of sdd.

However, since your image is a partition image, you can run fsstat to
read the superblock and tell you what the file system is (assuming
it's formatted.)

fsstat cruiser-1m.dd

mmls reads the first sector of whatever you hand it and tries to
interpret it as a partition table.  Since the first sector of your
partition image does NOT contain a valid partition table, you will get
nonsense results.

You need to image like this instead:

dd if=/dev/sdd of=cruiser-1m-phys.dd

That will give you a complete image of the physical disk and mmls will
give you a valid result.
