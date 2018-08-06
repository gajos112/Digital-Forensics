# How to copy on Linux

**1. Disk do Disk**
dd if=/dev/sda2 of=/dev/sdb2 bs=512 noerror

**2. DCFLDD (developed by defense computer forensics lab)**
dcfldd if=/dev/sda hash=md5 of=/media/diskimage.dd bs=512 noerror
   
- if=/dev/sda is the input device, in this case /dev/sda.
- hash=md5 tells the command to calculate an MD5 hash of the image that we can use to assure the image integrity.
- of=/media/diskimage.dd is the file that the disk image with go, in this case on an external device mounted at /media.
- bs=512 tells the command we want to transfer the image 512 bytes at a time.
- noerror tells the command that in the case of error continue to do the data transfer, but write zeros where the error occur.

**3. Dc3DD (developed by defense cymber crime center)**
- use dd and adds other capabilities
- faster than dd

**4. GUYMAGER (GUI tools for Linux, free)**

**5. ddrescure -r1 -v /dev/sdb1 /dev/sdc1 ddrescue1.log (usfeull when you got bad cluster)**
Coppise DATA and attempts to rescure data in the event of read erros.

**6. DD across a network with Netcat**
- Source: dd if=/dev/had bs=16065b | netcat targethost_IP target_port
- Target: Netcat -l -p target_port | dd of=/dev/hdc bs=16065b

**7. FTK Imager**
https://accessdata.com/product-download/ftk-imager-version-3.4.3

# How to copy on Windows

**-EnCase Forensic**

**-dd.exe**

**-FTK Imager**

**-dc3dd**

# How to copy mobile devices

**MOBILedit (tool designted for mobile devices)**
- http://www.mobiledit.com/http://www.mobiledit.com/

**Android SDK (tool designted for mobile devices)**

# Power ON and OFF

**Power is ON**

- Collectn the RAM information
- Encrypted data could be unencrypted in RAM
- Identify running processes

**Power is OFF**
- Leave off
- Make two Bit Copies
