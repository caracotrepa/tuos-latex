# tuos-fonts

Trivial LaTeX style for using the cooperate fonts used by The
University Sheffield. The actual magic is done by two style files that
are auto-generated by `autoinst`, which is part of
[Fontool](https://www.ctan.org/tex-archive/fonts/utilities/fontools/).

## Disclaimer

Please not that this LaTeX setup is neither endorsed nor officially
supported by the University of Sheffield.

## Prerequisites 

* The
  [Stephenson and Blake fonts](https://www.sheffield.ac.uk/marketing/visual-identity/downloads/fonts)
  used by The University for Sheffield. Note that you need to be a
  member of the University do
  [download](https://www.sheffield.ac.uk/polopoly_fs/1.15319!/file/Fonts.zip)
  them.

* The `autoinst' too from the
  [Fontool](https://www.ctan.org/tex-archive/fonts/utilities/fontools/)
  package. If you have a modern LaTeX distribution, it is most likely
  already installed on your machine. 


## Installation 

* First, we use `autoinst` to generate LaTeX styles
  for both fonts.
* Unzip the archive with the fonts:
```
mkdir fonts
cd fonts 
unzip ../Fonts.zip 
```
  * Now use `autoinst` for generating the font-specific LaTeX
    styles (using the default, autoinst will install the styles
    in your home directory):
   * Stephenson (the serif font) 
```
autoinst Steph.ttf StephBd.ttf StephIt.ttf
```
   * Blake (the sans serif font) 
```
autoinst -sanserif Blake.ttf BlakeBd.ttf BlakeIt.ttf 
```
* Most likely, you need to update the font maps. Please consult
  your LaTeX distribution and operating system help for detailed
  instructions. For example, in case Debian, you might (for a
  system wide-installation) to edit
  `/etc/texmf/web2c/updmap.cfg` and add the two lines (adapt the
  path information):
  
```
MixedMap TUOSBlake/TUOSBlake.map
MixedMap TUOSStephenson/TUOSStephenson.map
```
  and call `update-updmap`.

* For your convince, you might want to install `tuos-fonts.sty`, which
  just includes the generated styles for Stephenson and Blake and
  configures them using lining figures (as this is the default used by
  The University of Sheffield.

Please not that the fonts provided by The University of Sheffield do
not provide all the symbols requires for type-setting mathematical
content.

## License

This project is dual-licensed under a 2-clause BSD-style license and/or 
the LPPL version 1.3c or (at your opinion) any later version. 

SPDX-License-Identifier: LPPL-1.3c+ OR BSD-2-Clause

## Master Repository

The master git repository for this project is hosted by the [Software
Assurance & Security Research Team](https://logicalhacking.com):
<https://git.logicalhacking.com/adbrucker/tuos-latex>.
