# III

Assorted expect scripts for getting our marc records out of Millennium.

### Searching Ranges of Records

Search for marc records created during a certain time frame, expressed in MMDDYY, and download them to the your ftp server.
For example, to get all the records in the year 2012:

    search-range 010112 123112
    download axw-range-1

### Searching Latest Records

Search and download records from a month before the current date:

    search-updated
    download

### Using Timeouts

If your Innopac server hangs, you can terminate the script after a given amount of time.  Specify the total time to wait and a
a check interval, both in minutes.  For example, to wait 2 hours for the search-updated script to run, and check every half hour
to see if it's done:

    timeout3 -t 3600 -i 30 search-updated

