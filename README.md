# Linux-jp2a
I made this cool .jpg with Linux command line app "jp2a".
Learn more about it here: https://csl.name/jp2a/
Download it here: https://sourceforge.net/projects/jp2a/

![alt text](https://raw.githubusercontent.com/JasonMayberry/Linux/master/images/LinuxScreenShot.jpg)

![alt text](https://raw.githubusercontent.com/JasonMayberry/Linux-jp2a/master/images/jp2a-top.png)
# About
jp2a is a small utility that converts JPG images to ASCII. It's written in C and released under the GPL.
# Download and source
You can install jp2a from your favourite package manager. If jp2a is not there, you can download and build the source from https://github.com/cslarsen/jp2a.
# Screenshots
You can view an online jp2a gallery and try for yourself over at asciiconvert.com. Check out the JPEG screenshots of jp2a. Thumbnails Here are some other images in plain text:
Oswald, the lucky rabbit (side view)
Oswald, the lucky rabbit (front view)
Google-logo
![alt text](https://raw.githubusercontent.com/JasonMayberry/Linux-jp2a/master/images/thumbs.png)
Bender
Here are some color HTML-images:
Bender (ASCII, HTML color)
A dog, fence and mountains (ASCII, HTML color)
# Building and installing
## General
Compilation of jp2a requires jpeglib with libcurl as a recommended option. On many systems you can just do the following to compile jp2a:
./configure
make
make test    # optional
make install
If you have jpeglib installed in non-standard directory, say in /opt/local/include/jpeglib.h and /opt/local/lib/libjpeg.a then you can do
./configure --with-jpeg-prefix=/opt/local
## If you need to build jpeglib yourself
Download the sources from IJG.org and build them like for instance this:
./configure --prefix=/usr
make
make install-lib   # simply make install is not good enough for jp2a
## Mac OS X
jp2a is now part of DarwinPorts, so if you do a
sudo port install jp2a
then everything should be installed.
## FreeBSD
You can use the Freshports:
pkg_add -r jp2a
## Debian
You can use the Debian package:
apt-get install jp2a
## Gentoo
You can use the Gentoo package:
emerge jp2a
# Reading other graphics formats
In normal operation, you'd use jp2a with something like
jp2a --width=76 file.jpg
However, if you want to be able to read other graphics-formats, you can use ImageMagick's convert program with pipes, like
convert somefile.png jpg:- | jp2a --width=76 -
Convert is a very nice utility, letting you set a lot of options that might enhance the ASCII output (e.g. by setting contrast and brightness). Another example, increase brightness by 170% and then rotate 45 degress clockwise:
convert bender.bmp -modulate 170 -rotate 45 jpg:- | jp2a -
Convert handles just about any graphics-format you can think of, including video formats and vector formats like PDF and Postscript (handled by convert using Ghostscript).
# Reading images off the net
jp2a now handles downloading by using libcurl. Just do this:
jp2a http://foo.bar/image.jpg
If you didn't compile jp2a with curl, you can use another HTTP reader and pipe the result to jp2a: For instance, to download and convert the Google logo all on the fly, you can do this:
convert http://www.google.com/intl/en/images/logo.gif jpg:- | jp2a -           
                                                                      
       .......                                       .':.             
    .::'....':xd.                                     dX'             
  .ld.        ..       .                              oX.          ...
  ;O'              .c;..'cxc    ;,...,c;.  .:'.,lxc.  dX.  ,:'.,dx.. .
  oO.             .ox.    ,x0 .cd.    .cd..ll    l0.  xX. :K,..,::.   
  cxx.      .',cl 'x0      lK'.cx      ;k, lO;  .ll.  dX. o0:         
   ,dkc.      :kd  :kx.   :d;  ,ol.   .lc.  .''lk'    kX'  oOo'...    
     .;:cc;,,',,.    .;;,'..     .,,'...   ''',:lxo. .','.  .,::;.    
                                         .oc.     dO                  
                                          lk;....'c'                  
                                            .'....                    
                                                                      
# Why I made jp2a
I wanted a small project to teach myself how to use various libraries and autotools.
Suggestions
If you have any suggestions or code patches, I will be very glad to hear from you. You can email me to csl@csl.name.
I was asked if there are any bindings for Python. Unfortunately, no, but if anyone wants to make that, let me know.

# Links
## jp2a pages
jp2a on Freshmeat
jp2a on Advogato
jp2a on Linuxlinks
jp2a in the Free Software Foundation directory
jp2a on DarwinPorts
jp2a on Softpedia
jp2a on AUR ArchLinux
jp2a on OpenSoftware (in Polish)
jp2a on del.icio.us
jp2a on crux.nu
jp2a on os4depot.net — jp2a on Amiga!!
jp2a on freshports.org (freebsd ports)
jp2a on ALT Linux Sisyphus repository (in Russian)
jp2a on Moongift (in Japanese)
jp2a Debian package
How to ensure Set-Top-Box (STB) is Powered On? — a very original use for jp2a
## Other pages
The Independent JPEG Group, contains the JPEG library
CURL
asciiconvert.com converts images to ASCII online using jp2a
Someone used jp2a to convert a movie to ASCII
Decrypt.py, a cool, animated ASCII garbler, uses jp2a as an example
Instascii is an instagram client for the console
movie2ascii converts movies using jp2a to a JavaScript player in HTML!
# Author
jp2a is written by Christian Stigen Larsen
