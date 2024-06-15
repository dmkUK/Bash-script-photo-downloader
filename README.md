# Photo-downloader
## Why?
In an _attempt_ to learn a bit of bash and get to know some of the binaries available to an Ubuntu user, I've written my first script which solves a problem I had downloading photo's from my ancient Olympus DSLR camera. Over the years I created a slightly tortuous method using Oympus Viewer and Studio (via via virtualbox), Digikam, Darktable and Gimp to download, backup, keyword, develop, edit and archive my pictures. I download the RAW (.orf) or JPEG (.JPG) files into two locations with identical folder structures based on dates on separate hard drives, one to work on and one as a backup which remains untouched. Unfortunately the downloads were slow and latterly often corrupted over USB via virtualbox. I could do this with darktable or Digikam and rsync but I needed a little project, and so, a script....
## Contents
So far just two files, the script itself (which is heavily commented for my benefit) and the notes I kept whilst trying to figure this out.
