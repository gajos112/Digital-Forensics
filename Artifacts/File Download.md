# Open/Save MRU (Most recently use)

**Description:**

In the simplest terms, this key tracks files that have been opened or saved within a Windows shell dialog box. This happens to be a big data set, not
only including web browsers like Internet Explorer and Firefox, but also a majority of commonly used applications.

**Location:**

Windows XP:
- NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSaveMRU

Win7/8/10:
- NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSavePIDlMRU

# E-mail Attachments

**Description:**
The e-mail industry estimates that 80% of e-mail data is stored via attachments. E-mail standards only allow text. Attachments must be  encoded with MIME/base64 format.

**Location:**

Outlook XP:
- %USERPROFILE%\Local Settings\ApplicationData\Microsoft\Outlook

Win7/8/10: 
- %USERPROFILE%\AppDat

**Interpretation:**
MS Outlook data files found in these locations include OST and PST files. One should also check the OLK and Content.Outlook folder, which might roam depending on the specific version of Outlook used. 

# Skype History

**Description:**

• Skype history keeps a log of chat nsessions and files transferred from one machine to another
• This is turned on by default in Skype installations 

**Location:**

XP:
- C:\Documents and Settings\<username>\Application\ Skype\<skype-name>

Win7/8/10:
- C:\%USERPROFILE%\AppData\Roaming\Skype\<skype-name>

Interpretation:
Each entry will have a date/time value and a Skype username associated with the action.

# Browser Artifacts

**Description:**

Not directly related to “File Download”. Details stored for each local user account. Records number of times visited (frequency).

**Location:**

Internet Explorer:
• IE8-9 %USERPROFILE%\AppData\Roaming\Microsoft\Windows\
IEDownloadHistory\index.dat
• IE10-11 %USERPROFILE%\AppData\Local\Microsoft\Windows\
WebCache\WebCacheV*.dat

Firefox:
• v3-25 %userprofile%\AppData\Roaming\Mozilla\ Firefox\
Profiles\<random text>.default\downloads.sqlite
• v26+ %userprofile%\AppData\Roaming\Mozilla\ Firefox\
Profiles\<random text>.default\places.sqlite
Table:moz_annos

Chrome:
• Win7/8/10 %USERPROFILE%\AppData\Local\Google\Chrome\User
Data\Default\History

**Interpretation:**
Many sites in history will list the files that were opened from remote sites and downloaded to the local system. History will record the
access to the file on the website that was accessed via a link.

# Downloads

**Description:**

Firefox and IE has a built-in download manager application which keeps a history of every file downloaded by the user. This browser artifact can provide excellent information about what sites a user has been visiting and what kinds of files they have been downloading from them.

**Location:**

Firefox:
• XP: %userprofile%\Application Data\Mozilla\ Firefox\Profiles\<random text>.default\downloads.sqlite
• Win7/8/10: %userprofile%\AppData\Roaming\Mozilla\ Firefox\Profiles\<random text>.default\downloads.sqlite

Internet Explorer:
• IE8-9 %USERPROFILE%\AppData\Roaming\Microsoft\Windows\
IEDownloadHistory\
• IE10-11 %USERPROFILE%\AppData\Local\Microsoft\Windows\
WebCache\ WebCacheV*.dat

**Interpretation:**

Downloads will include:
• Filename, Size, and Type • Download from and Referring Page
• File Save Location • Application Used to Open File
• Download Start and End Times

# ADS Zone.Identifer

**Description:**

Starting with XP SP2 when files are downloaded from the “Internet Zone” via a browser to a NTFS volume, an alternate data stream is added to the file. The alternate data stream is named “Zone.Identifier.”

**Interpretation:**

Files with an ADS Zone.Identifier and contains ZoneID=3 were downloaded from the Internet.
• URLZONE_TRUSTED = ZoneID = 2
• URLZONE_INTERNET = ZoneID = 3
• URLZONE_UNTRUSTED = ZoneID = 4
