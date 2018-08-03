# Portable Executable 
(PE) format is a file format for executables, object code, DLLs, Font files, and others used in 32-bit and 64-bit versions of Windows operating systems. For example, PE formatted files include:
**- .exe**

**- .dll**

**- .sys (driver files)**
     
     +-------------------+  file offset 0
      | DOS-header        |
      +-------------------+
      | PE/COFF-header    |
      +-------------------+
      | optional header   |
      |- - - - - - - - - -|
      |                   |
      | data directories  |
      | array             |
      |                   |
      +-------------------+
      |                   |
      | section headers   |
      | array             |
      |                   |
      +-------------------+
      |                   |
      | section 1         |
      |                   |
      +-------------------+
      |                   |
      | section 2         |
      |                   |
      +-------------------+
      |                   |
      | ...               |
      |                   |
      +-------------------+
      |                   |
      | section n         |
      |                   |
      +-------------------+  end of file

# DOS MZ header
The DOS MZ executable format is the executable file format used for .EXE files in DOS.

The file can be identified by the ASCII string "MZ" (hexadecimal: 4D 5A) at the beginning of the file (the "magic number"). 
"MZ" are the initials of Mark Zbikowski, one of leading developers of MS-DOS.

# DOS STUB
MS-DOS stub is to print message to the user and then exit if the .exe file is run from under MS-DOS.

“This program cannot be run in DOS mode”

# PE HEADER
The PE file header is located by indexing the e_lfanew field of the DOS header. The e_lfanew field simply gives the offset in the file to the begining of the PE header. This header begins with a 4 byte signature thats reads 'PE' in ASCII. The PE header is called IMAGE_FILE_HEADER (WINNT.H) and its field are described below:

**1. Signature** The PE signature.

**2. Machine** The architecture type of the computer.This member can be one of the following values:
- IMAGE_FILE_MACHINE_I386: 0x014c (x86)
- IMAGE_FILE_MACHINE_IA64: 0x0200 (Intel Itanium)
- IMAGE_FILE_MACHINE_AMD64: 0x8664 (x64)

**3. NumberOfSections** The number of sections. This indicates the size of the section table, which immediately follows the headers. Note that the Windows loader limits the number of sections to 96.

**4. TimeDateStamp** The low 32 bits of the time stamp of the image. This represents the date and time the image was created by the linker. The value is represented in the number of seconds elapsed since midnight (00:00:00), January 1, 1970, Universal Coordinated Time, according to the system clock.

**5. PointerToSymbolTable** The offset of the symbol table, in bytes, or zero if no PE symbol table exists.

**6. NumberOfSymbols** The number of symbols in the symbol table.

**7. SizeOfOptionalHeader** The size of the optional header, in bytes. This value should be 0 for object files.

**8. Characteristics** The characteristics of the image. Several values.

# COFF Header

# OPTIONAL HEADER

# SECTION TABLE

# SECTIONS

**Executable Code Section** named .text (Microsoft) od CODE (Borland)

**Data Sections** named .data, .rdata or .bss (Microsoft) or DATA (Borland)

**Resources Sections** named .rsrc

**Export Data Section** named .edata

**Import Data Sections** named .idata

**Debug Information Section** named .debug
