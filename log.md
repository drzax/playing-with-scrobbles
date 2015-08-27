# Log
This is a log of all steps taken in the data analysis for this project. Including any other important information.

## Data source
The original data `data/scrobbles.tsv` is an export of my scrobbles from [my last.fm account](http://www.last.fm/user/drzax).

There isn't a data dictionary or much metadata at all attached to the export, the details of each column are, to some extent assumed.

## Subset the data
As a starting point for analysis I've created a subset of the original data with only the columns I'm interested in.

Done using [csvkit](https://github.com/onyxfish/csvkit).

```
csvcut -t -c 2,3,5 data/scrobbles.tsv > data/scrobbles-cut.csv
```

This gets me just the 'unixtime' 'track name' and 'artist name' columns.
