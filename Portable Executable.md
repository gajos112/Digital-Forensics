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
PE header starts with magic string "PE" which we are able in ASCII while opening file with HEX Editor.

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
