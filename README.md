text_to_CAMEO
=============

This Python3 program takes data in the text-oriented ICEWS files and converts 
this to a more conventional data format using the CAMEO codes. The conversion process is described in detail 
in the file *text_to_CAMEO_documentation.pdf*. 

To run: python text_to_CAMEO.py [-F] [-c] [-t \<filename\>] [-m]

Options:
--------

-F: Files are in FOUO format. Default: Files are in Dataverse format

-c: Include COW numerical country codes in addition to ISO-3166 code. Default: Include only the ISO codes

-t: \<file-name \> Process the files listed one per line in the text file  \<file-name\>. Default: process all of the files in the working directory that end in “.csv” (Dataverse format) or “.tab” (FOUO format)

-m: Output all of the substate agents in a concatenated string. Default: only a single agent is used, with the priority determined by the list agentcodes.

Requires:
---------

    CAMEO_codefile.txt [FOUO only]
    countrynames.txt
    agentnames.txt

JSON conversion
---------------

Template code---this is from an active and fully debugged program, but it has some project-specific quirks---for converting ICEWS to JSON can be found at https://github.com/philip-schrodt/ICEWS-to-jsonl: using JSON rather than `.csv` is highly recommended if you are planning to do anything complicated. 

Comments on the April-2017 modifications
----------------------------------------

1. This program merges two earlier versions I'd used separately for the two formats. Both of those were used successfully in large-scale projects so I'm confident they were working, but I've not done that sort of testing on this merged version (I have done *basic* testing on it...really...). So definitely check and make sure the output makes sense.

2. The fact that there are at least two incompatible formats of the ICEWS data suggests the possibility that there might be others: again, check to make sure your output makes sense.

3. There's an assortment of “commented out” code in the program that was used earlier to do some basic marginals on the code: this could be reactivate but is in Python 2.6 and will also need a bit of updating to Python 3.5.

Comments on the March-2020 modifications
----------------------------------------

Dataverse files for 2015 through 2019 have options for three different file formats: the one compatible with
this program is `Original File Format (Tab-Delimited)` which downloads as a file with a `.tsv` suffix. The new files
under the `Tab-Delimited` option (`.tab` file suffix) have the string data fields in quotes, which is cool but that format
change causes the actor names not to match, so these all produce "---". I've modified the program so that the default (no
command line options) codes all files with either `.tab` or `.tsv` as the suffix. 

ICEWS has been off-line for about nine
months and will be produced by Leidos rather than Lockheed when/if it returns, so I'm waiting to see if there are
additional changes under the new sponsorship; in the meantime this fix should work as long as you download the `.tsv` file
and not the `.tab` file for those years.

February-2021 modifications
----------------------------------------

* -m option for output of all substate actors
* -F now detects the format change in FOUO version ca. May-2020. If the CAMEO code is already in the data, this is used.
* 1951 and 1952 codes added to CAMEO_codefile.txt
* os.path.basename()  used for finding filename, generalizing beyond Unix
