# LINUX
- **FMEM** - kernel module that creates device /dev/fmem, similar to /dev/mem but without limitations. This device (physical RAM) 
can be copied using dd or other tool. Works on 2.6 Linux kernels. Under GNU GPL.

- **LiME** - Linux Memory Extractor (LiME) is a Loadable Kernel Module (LKM), which allows the acquisition of volatile memory from 
Linux and Linux-based devices, such as those powered by Android. The tool supports dumping memory either to the file 
system of the device or over the network.

**/dev/mem** - On older Linux systems, the program dd can be used to read the contents of physical memory from the device file /dev/mem. 
On recent Linux systems, however, /dev/mem provides access only to a restricted range of addresses, rather than the full physical 
memory of a system. On other systems it may not be available at all.

**/dev/crash** - On Red Hat systems (and those running related distros such as Fedora or CentOS), the crash driver can be loaded to create 
pseudo-device /dev/crash for raw physical memory access (via command "modprobe crash").


# WINDOWS

- **dumpit.exe**

- **winpmem.exe**

- **FTK Imager**

- **Redline - FireEye**

# MEMORY ANALYSIS USING VOLATILITY

**1.** volatility –f <file> imageinfo - Figure out what operating system it belongs to.
  
**2.** volatility -f <file> --profile=Win10x64_14393 -h - Display plugins.

**3.** volatility -f <file> --profile=Win10x64_14393 pslist - List processes from memory image.

**4.** volatility -f <file> --profile=Win10x64_14393 psscan - More indeep view of prcocesses can display more proccesses.

**5.** volatility -f <file> --profile=Win10x64_14393 procdump -p PROCCESS_ID --dump-dir=./ - Dump a process to an executable file sample

**6.** volatility -f <file> --profile=Win10x64_14393 memdump -p PROCCESS_ID --dump-dir=./ - To extract all memory resident pages in a process into an individual file, use the memdump command.
  
**7** volatility -f Desktop/memory-images/xp-laptop-2005-06-25.img --profile=WinXPSP2x86 dumpfiles --dump-dir=./ - Extract memory mapped and cached files

**8**  volatility -f Desktop/memory-images/xp-laptop-2005-06-25.img --profile=WinXPSP2x86 modscan - Pool scanner for kernel modules


# CONVERTING HIBERNATION FILES AND CRASH DDUMPS #

**IMAGECOPY** - Convert alternate memory sources to raw.

*-f* - Name of source file

*-O* - Output file name
    
*--profile* - Source OS from imageinfo

vol.py imagecopy -f hiberfil.sys -O hiber.raw --profile=Win7SP1x64
vol.py imagecopy -f MEMORY.DMP -O crashdump.raw –-profile=Win2016x64_14393
