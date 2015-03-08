
PDF Image to text converter
===========================

This program written in Bash Shell converts any PDF (either Image-based PDF or text-based PDF) to plaintext.

It's using the following free software to run:

- Pdftk (to extract pages of the PDF, one by one)
- ImageMagick (to convert each page to a PNG file)
- Scantailor (to adjust the PNG files and convert them to TIFF, enhancing the contrast)
- Tesseract OCR (to convert the TIFF to text)

On debian:

apt-get install tesseract-ocr tesseract-ocr-deu tesseract-ocr-eng tesseract-ocr-fra tesseract-ocr-equ imagemagick scantailor pdftk

Note: it may be necessary to enable BACKPORTS in wheezy to have the latest scantailor

Requirements:
-------------

- a Linux or *NIX machine with the software above
- some space in /tmp/ (could be up to ~10 times the biggest PDF you'll convert)
- a *lot* of CPU power. This shell knows how to use multi-core CPUs \o/
- some disk I/O during conversions

Usage:
------

    pdfimagetotext <pdf file> [text file]

Convert the <pdf file> to the same file replacing .pdf by .txt 
unless a text file name has been passed as second parameter, the text version is saved there instead
If text file is "-", the text version will be sent to STDOUT instead.

if the first argument is -v verbose instructions will be echoed to STDERR


Configuration:
--------------


License:
--------

GPLv3+ 

(C) Benjamin Sonntag <benjamin@octopuce.fr> 2012-2014


Special cases:
--------------

Cases currently not handled:

- inverted video picture (white on black background) How can we detect that?
- how can we handle multilingual files? 


