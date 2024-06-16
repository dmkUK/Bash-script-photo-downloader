# Photo-downloader
## Why?
In an _attempt_ to learn a bit of bash and get to know some of the binaries available to an Ubuntu user, I've written my first script which solves a problem I had downloading photo's from my ancient Olympus DSLR camera. Over the years I created a slightly tortuous method using Oympus Viewer and Studio (via virtualbox), Digikam, Darktable and Gimp to download, backup, keyword, develop, edit and archive my pictures. I download the RAW (.orf) or JPEG (.JPG) files into two locations with identical folder structures based on dates on separate hard drives, one to work on and one as a backup which remains untouched. Unfortunately the downloads were slow and latterly often corrupted over USB via virtualbox. I could do this with darktable or Digikam and rsync, but I wanted a little project, and so, a script....
## Contents
So far just two files, the script itself (which is heavily commented for my benefit) and the notes I kept whilst trying to figure this out.
## Reqiurements
This was written on Ubuntu 22.04.4 LTS and the only additional requirement is [ExifTool by Phil Harvey](https://exiftool.org/) currently __Download Version 12.87 (7.1 MB) - June 13, 2024__

On Ubuntu 22.04.4 LTS:
```
$ apt show *exiftool*
```
>Package: libimage-exiftool-perl  
Version: 12.40+dfsg-1  
Priority: optional  
Section: universe/perl  
Origin: Ubuntu  
Maintainer: Ubuntu Developers <ubuntu-devel-discuss@lists.ubuntu.com>  
Original-Maintainer: Debian Perl Group <pkg-perl-maintainers@lists.alioth.debian.org>
Bugs: https://bugs.launchpad.net/ubuntu/+filebug  
Installed-Size: 22.7 MB  
Provides: exiftool  
Depends: perl:any  
Recommends: libarchive-zip-perl, libunicode-linebreak-perl  
Suggests: libposix-strptime-perl  
Homepage: https://exiftool.org/  
Task: ubuntustudio-photography  
Download-Size: 3,717 kB  
APT-Sources: http://gb.archive.ubuntu.com/ubuntu jammy/universe amd64 Packages  
Description: library and program to read and write meta information in multimedia files  
 Image::ExifTool is a customizable set of Perl modules plus a full-featured
 command-line application called exiftool for reading and writing meta
 information in a wide variety of files, including the maker note information
 of many digital cameras by various manufacturers such as Canon, Casio, DJI,
 FLIR, FujiFilm, GE, GoPro, HP, JVC/Victor, Kodak, Leaf, Minolta/Konica-Minolta,
 Nikon, Nintendo, Olympus/Epson, Panasonic/Leica, Pentax/Asahi, Phase One,
 Reconyx, Ricoh, Samsung, Sanyo, Sigma/Foveon and Sony.  
 The following modules/packages are recommended for specific features, e.g.
 decoding compressed and/or encrypted information from the indicated file
 types, calculating digest values for some information types, etc.:  
>  * Archive::Zip / libarchive-zip-perl: ZIP, DOCX, PPTX, XLSX, ODP, ODS, ODT,
    EIP, iWork
>  * Unicode::LineBreak / libunicode-linebreak-perl: for column-alignment of
    alternate language output
>  * POSIX::strptime / libposix-strptime-perl: for inverse date/time conversion
>  * Time::Piece (in perl core): alternative to POSIX::strptime
>  * IO::Compress::RawDeflate + IO::Uncompress::RawInflate (in perl core): for
    reading FLIF images
>
>Package: exiftool  
State: not a real package (virtual)

```
sudo apt-get install exiftool
```
or  
```
sudo apt-get install libimage-exiftool-perl
```
acheive the same end as exiftool is a dummy package which gives the message:  
> Note, selecting 'libimage-exiftool-perl' instead of 'exiftool'
