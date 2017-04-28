text_to_CAMEO
=============

This Python3 program takes data in the text-oriented ICEWS files and converts 
this to a more conventional data format using the CAMEO codes. The conversion process is described in detail 
in the file *text_to_CAMEO_documentation.pdf*. 

To run: python text_to_CAMEO.py [-F] [-c] [-t \<filename\>]

Options:
--------

-F: Files are in FOUO format. Default: Files are in Dataverse format

-c: Include COW numerical country codes in addition to ISO-3166 code. Default: Include only the ISO codes

-t: \<file-name \> Process the files listed one per line in the text file  \<file-name\>. Default: process all of the files in the working directory that end in “.csv” (Dataverse format) or “.tab” (FOUO format)

Requires:
---------

    CAMEO_codefile.txt [FOUO only]
    countrynames.txt
    agentnames.txt

Comments on the April-2017 modifications
----------------------------------------

1. This program merges two earlier versions I'd used separately for the two formats. Both of those were used successfully in large-scale projects so I'm confident they were working, but I've not done that sort of testing on this merged version (I have done *basic* testing on it...really...). So definitely check and make sure the output makes sense.

2. The fact that there are at least two incompatible formats of the ICEWS data suggests the possibility that there might be others: again, check to make sure your output makes sense.

3. There's an assortment of “commented out” code in the program that was used earlier to do some basic marginals on the code: this could be reactivate but is in Python 2.6 and will also need a bit of updating to Python 3.5.
