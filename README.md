# ncatool

![License](https://img.shields.io/badge/license-ISC-blue.svg)

ncatool is a tool to view information about, decrypt, and extract Nintendo Content Archives.

It is heavily inspired by [ctrtool](https://github.com/profi200/Project_CTR/tree/master/ctrtool).

## Usage

```
Usage: ncatool [options...] <file>
Options:
-i, --info        Show file info.
                      This is the default action.
-x, --extract     Extract data from file.
                      This is also the default action.
  -r, --raw          Keep raw data, don't unpack.
  -y, --verify       Verify hashes and signatures.
  -d, --dev          Decrypt with development keys instead of retail.
  --titlekey=key     Set title key for Rights ID crypto titles.
  --contentkey=key   Set raw key for NCA body decryption.
NCA options:
  --section0=file    Specify Section 0 file path.
  --section1=file    Specify Section 1 file path.
  --section2=file    Specify Section 2 file path.
  --section3=file    Specify Section 3 file path.
  --section0dir=dir  Specify Section 0 directory path.
  --section1dir=dir  Specify Section 1 directory path.
  --section2dir=dir  Specify Section 2 directory path.
  --section3dir=dir  Specify Section 3 directory path.
  --exefs=file       Specify ExeFS file path. Overrides appropriate section file path.
  --exefsdir=dir     Specify ExeFS directory path. Overrides appropriate section directory path.
  --romfs=file       Specify RomFS file path. Overrides appropriate section file path.
  --romfsdir=dir     Specify RomFS directory path. Overrides appropriate section directory path.
  --listromfs        List files in RomFS.
```

## Building

Copy `config.mk.template` to `config.mk`, make changes as required, and then run `make`.
If your `make` is not GNU make (e.g. on BSD variants), you need to call `gmake` instead.

To build under windows, you will need to build [libgpgerror](https://www.gnupg.org/(fr)/related_software/libgpg-error/index.html), and [libgcrypt](https://www.gnu.org/software/libgcrypt/).
You may need [libiconv](https://www.gnu.org/software/libiconv/) when not building on Linux.
Fairly recent versions (~1.8.0) are required of the libraries in order to support AES-XTS operations. I recommend using MinGW.

## Licensing

This software is licensed under the terms of the ISC License.  
You can find a copy of the license in the LICENSE file.
