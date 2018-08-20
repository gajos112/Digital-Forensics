# Amcache

The Amcache.hve is a Windows Registry Hive that contains data about applications that have been run on a Windows system. 
The artifact also contains the file path for the executable, the date and time it was first run.

These executed applications include the execution path, first executed time, deleted time, and first installation.
On Windows 8, Amcache.hve replaces RecentFileCache.bcf and uses the Windows NT Registry File (REGF) format.

A **common location** for Amcache.hve is:

- \%SystemRoot%\AppCompat\Programs\Amcache.hve


Amcache.hve file is also an important artifact to record the traces of anti-forensic programs, portable programs, and external storage devices.

**Tools:**

- Amcacheparser: Windows command line tool (free), https://ericzimmerman.github.io

- RegRipper: Amcache plugin (free), https://github.com/keydet89

- Amcache.py: Python tool (free), https://github.com/williballenthin/python-registry/tree/master/samples

- EnCase: Enscript, links for v6 and v7 enscripts 

**How can be leveraged?**

Amcache.hve records the recent processes that were run and lists the path of the files that’s executed which can then be used to find the executed program.
It also records the programs SHA1 so it can be researched with databases like VirusTotal for easy identification.
