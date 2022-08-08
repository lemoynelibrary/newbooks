# New Books by Call Number

A Perl script is used to process new book items each month. The data file is made using Create Lists in Sierra and exported as a text file. The only thing you need to remember to do is update the year in the HTML template section of the script. 

## Note on running Perl

On my Le Moyne PC, I was using ActivePerl. No Perl program is currently available in AJ Apps, so ActivePerl (or any reasonable equivalent) will probably need to be installed directly on your computer by the College IT Systems group. Put in a ticket with the Service Desk.

Since the onset of Covid, I switched to using the Perl that comes installed on my personal Macintosh and which is accessible through Terminal. 

On my machine, I am running Perl version 5.18.4, but I suspect any version of Perl will be sufficient, since `CALL_LIST_ACQ.pl` is simple and standard; the script itself dates back to the late 1990s and Mike's first implementation for Le Moyne was done on June 2000.

## Local cataloging practice

Since BIBFRAME was implemented in Sierra, bibliographic records in Sierra sometimes have extra PUBLISHER fields that map to the the copyright date, but have no actual imprint information.

So, the Create List file you generate in Sierra might have a record like this, where `PUBLISHER = {u00A9}2021.` appears:

```
CALL NO. = D1056.2.R9 F66 2021. 
TITLE = Political dissent and democratic remittances : the activities of Russian
migrants in Europe / Joanna Fomina. 
PUBLISHER = {u00A9}2021. 
PUBLISHER = Abingdon, Oxon ; New York, NY : Routledge, 2021. 
RECORD # = b28193167. LOCATION = lbks. 
```

When that line appears first, before the full imprint line -- e.g., `PUBLISHER = Abingdon, Oxon ; New York, NY : Routledge, 2021.` -- it will be used instead of the imprint. The solution is to remove these copyright lines. I wrote an [AppleScript that runs with BBedit](https://github.com/tomkeays/newbooks/blob/master/utility-files/BBEDIT_newbooks-trim.scpt.txt) that strips all such lines from Create List file. You run it before you run the Perl script.

## PLS Test 8-8-22