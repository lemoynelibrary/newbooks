# New Books by Call Number

A Perl script is used to process new book items each month. The data file is made using Create Lists in Sierra and exported as a text file. The only thing you need to remember to do is update the year in the HTML template section of the script.

## Note on using Perl

On my Le Moyne PC, I was using ActivePerl. It is not currently available in AJ Apps, so it will probably need to be installed directly on your computer by the College IT Systems group. Put in a ticket with the Service Desk.

Since the onset of Covid, I switched to using the Perl that comes installed on my personal Macintosh and which is accessible through Terminal. On my machine, this is version 5.18.4, but I suspect any version of Perl will be sufficient, since CALL_LIST_ACQ.pl isn't doing anything non-standard; it dates back to the 1990s and Mike's first implementation was from June 2000.
