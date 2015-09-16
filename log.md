# Log
This is a log of all steps taken in the data analysis for this project. Including any other important information.

## Data source
The original data `data/scrobbles.tsv` is an export of my scrobbles from [my last.fm account](http://www.last.fm/user/drzax).

There isn't a data dictionary or much metadata at all attached to the export, the details of each column are, to some extent assumed.

## Subset the data
As a starting point for analysis I've created a subset of the original data with only the columns I'm interested in.

Done using [csvkit](https://github.com/onyxfish/csvkit).

```
csvcut -t -c 2,3,5 data/scrobbles.tsv > module-1/scrobbles-cut.csv
```

This gets me just the 'unixtime' 'track name' and 'artist name' columns.

## Module 2 - The beatles

Just so I'm not duplicating 4MB of data all over the place, I thought I'd subset it for the Module 2 exercise. So now we have all of The Beatles plays.

```
csvgrep -c 3 -m "The Beatles" module-1/scrobbles-cut.csv > module-2/the-beatles.csv
```
