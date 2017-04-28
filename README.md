text_to_CAMEO
=============

This program takes data in the text-oriented ICEWS files and converts 
this to a more conventional data format using the CAMEO codes. The conversion process is described in detail 
in the file `text_to_CAMEO_documentation.pdf`. 

To run: python text_to_CAMEO.py [[-F] [-c] [-t <filename>]

Options:
--------

::

-F: Process the FOUO format. Default: Process the Dataverse format

-c: Include COW numerical country codes in addition to ISO-3166 code. Default: Include only the ISO codes

-t: <file-name > Process the files listed one per line in the text file <file-name>. 
    Default: process all of the files in the working directory that end in “.csv” (Dataverse format) or “.tab” (FOUO format)

Requires:

::

    CAMEO_codefile.txt [FOUO only]
    countrynames.txt
    agentnames.txt
    filenames.txt

