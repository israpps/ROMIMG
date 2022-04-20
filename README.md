ROM Image Generator by SP193


## Introduction
> ROMIMG is a tool that handles IOP image files (e.g. those IOPRP images and the boot ROM image itself) that are used for IOP resets or for just storing files.

### It has the following features: 

- Supports IOPRP image files.
- Supports extracting files from boot/DVD ROM (aka the "BIOS") image files
- Allows files to be added, removed and extracted from images.
- Supports the adding and removing of the Bootstrap program (The RESET file).

Syntax
```
ROMIMG -c <ROM image> <files>
        Create ROM image
ROMIMG -l <ROM image>
        List files in ROM image
ROMIMG -a <ROM image> <file(s)>
        Add file(s) to ROM image
ROMIMG -d <ROM image> <file(s)>
        Delete file(s) from ROM image
ROMIMG -x <ROM image>
        Extract all files from ROM image
ROMIMG -x <ROM image> <file>
        Extract file from ROM image
```
#### Note: 
> The RESET file entry cannot be detected because it must be there for the image to be considered valid. However, deleting it with the delete command will just clear off the bootstrap program. A bootstrap program can be added to an image that does not have one (RESET is 0 bytes in size).

The bootstrap program is a binary file with the entry point at the start at the file. It is used during the startup sequences by both the IOP and EE during cold boots. Usually, this feature will not be used except for when building a boot ROM image (e.g. for PCSX2).

## Known limitations/bugs
```
Note 2013/08/27: I don't think that it's possible to rebuild the Sony PS2 boot ROM with this tool at this moment, as some files (e.g. RDRAM) must be stored at specific locations within the ROM image. The entries named "-" appear to be fillers, and exist before the files that need to exist at specific regions.
```

Original Download Links
ROMIMG v1.12: http://www.mediafire.com/download/7agibndqshasrbx/%5B130629%5DROMIMG_bin.7z 

ROMIMG v1.12 (Source code): http://www.mediafire.com/download/rx7onlcgvu7yak3/%5B130629%5DROMIMG.7z 
