# III

Assorted expect scripts for getting our marc records out of Millennium.

### Searching By Date

Search by creation date, given various parameters, expressed as MMDDYY.

##### Date Range

Search for marc records created between two dates and download them to the your ftp server.
All dates are 21st-century. For example, to get all the records in the year 2012:

    search-range 123111 010113
    download axw-range-1

Note: dates are exclusive.

##### Before Date

Return records created before a given date. For example:

    search-before 010200

This will return records created on or before January 1, 2000.

### Searching Latest Records

Search and download records from a month before the current date:

    search-updated
    download

### Using Timeouts

If your Innopac server hangs, you can terminate the script after a given amount of time.  Specify the total time to wait and a
a check interval, both in minutes.  For example, to wait 2 hours for the search-updated script to run, and check every half hour
to see if it's done:

    timeout3 -t 3600 -i 30 search-updated

### Download All Records

Innopac limits the size of downloaded files to 5000 records, so we have to split them up by date to ensure that no single file
exceeds that number of records.  Use the `download-all` script to download all marc records in batches, each less than
50000 in size.  The date ranges are all arbitrary, but 3-6 month intervals seems to be a good metric.
