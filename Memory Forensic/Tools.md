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
