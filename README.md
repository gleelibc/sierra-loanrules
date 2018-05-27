Sierra Loanrules
===============
Method for hosted Sierra sites to retrieve loanrule data

One issue with being hosted by iii is that the data files containing loanrule and determiner data are not easily accessible. Although the data is viewable in the client, it's not easy to navigate back and forth between the two displays, especially in a hurry.

We discovered that when Sierra desktop opens each of these two tables, the entirety of the two data files are read into java's standard output, which you can see in the iiirunner (console) window or a text file.

To set output to a text file:
1.  Open the location where the Sierra Desktop App is installed, e.g. C:\Sierra Desktop App\
2.  Open the **iiirunner.lax** file in your favorite text editor.
3.  Look for the line **lax.stdout.redirect=** and change it to redirect to a text file, e.g. **lax.stdout.redirect=C:\\\\temp\\\\iiirunner.txt** (Note the double backslashes). 
4.  Open Sierra Desktop App and open determiner and loan rule tables. You don't have to do anything other than opening and closing them.
5.  Close Sierra Desktop App and then open the text file that contains the output.
6.  Find the block(s) of text that start with **\*\*\*\*DATA FILE\*\*\*\*** and end with **\*\*\*\*\*\*\*\***
7.  You should see each table in a pipe-delimited format, which you can import into Excel or another utility.

* Note: Normally you may want to output the standard streams (stdout,stderr,stdin) for troubleshooting to the iiirunner console window, but we found that copying from the console buffer and then pasting into a file is kind of an annoyance with the defaults in Windows.

Tested on an iii-hosted site on Sierra 3.1. Please feel free to contact us about any problems or suggestions. Thanks!

TODO List:
- [ ] Script to extract the datafile sections automatically from the outputted file
- [ ] Scripts to manipulate table data (such as showing active/inactive determiners in LR table)
- [ ] Web-based UI for viewing/filtering table(s)
