# Shimcache

Shimcache, also known as AppCompatCache, is a component of the Application Compatibility Database, which was created by Microsoft (beginning in Windows XP) and used by the operating system to identify application compatibility issues.
The cache stores various file metadata depending on the operating system, such as:

•	File Full Path

•	File Size

•	$Standard_Information (SI) Last Modified time

•	Shimcache Last Updated time

•	Process Execution Flag

Similar to a log file, the Shimcache also “rolls” data, meaning that the oldest data is replaced by new entries.
The amount of data retained varies by operating system.
This helps developers troubleshoot legacy functions and contains data related to Windows features: it is used for quick search to decide whether modules need shimming for compatibility or not.
A Shim is a small library that transparently handles the applications interworking’s to provide support for older APIs in a newer environment or vice-versa.

The **Registry Key** related to this cache is located at:

- HKLM\SYSTEM\CurrentControlSet\Control\SessionManager\AppCompatCache\AppCompatCache

**Tools:**

- ShimCacheParser - https://github.com/mandiant/ShimCacheParser
- AppCompatCacheParser  - https://github.com/EricZimmerman/AppCompatCacheParser

**How can be leveraged?**

The Shimcache tracks metadata such as the full file path, last modified date, and file size but only contains the information prior to the system’s last startup, as current entries are stored only in memory
The events in Shimcache.hve are listed in chronological order with the most
recent event first and can be used in timelines to recreate and determine malicious activities.
