# Exposure indices derived from PlaceIQ movement data

## Summary

This repository contains indices describing exposure on the basis of smartphone movements.
These indices are produced by
[Victor Couture](http://faculty.haas.berkeley.edu/couture/index.html), 
[Jonathan Dingel](https://github.com/jdingel/),
[Allison Green](https://github.com/awasgreen), 
[Jessie Handbury](http://www.jessiehandbury.com/),
and 
[Kevin Williams](http://www.kevinrwilliams.com/),
with assistance from
Hayden Parsley
and
Serena Xu. 
They are derived from anonymized, aggregated smartphone movement data provided by [PlaceIQ](https://www.placeiq.com/).

We are making these indices publicly available to all researchers in the context of the spread of COVID-19.
The indices, which describe (potential) exposure varying across locations and time within the United States, could be useful in a variety of applications.
The indices published here cover January 2020 to present, with a seven-day lag.
We will update them every weekday.

We thank Drew Breunig, Nicholas Sheilas, Stephanie Smiley, Elizabeth Cutrone, and the team at PlaceIQ for their ongoing help.
This data release was approved by the University of California, Berkeley Office for Protection of Human Subjects under CPHS Protocol No 2018-05-11122.

## Data description

The following indices are available as (compressed) CSV files in this GitHub repository.

### Location exposure indices

Currently version 0.5.

- **State-level location exposure index (LEX)**: 
Among smartphones that pinged in a given state today,
what share of those devices pinged in another state at least once during the previous 14 days?
The daily state-level LEX is a 51-by-51 matrix in which each cell reports,
among devices that pinged today in the column state,
the share of devices that pinged in the row state at least once during the previous 14 days.
The District of Columbia is the 51st geographic entity in this LEX.

- **County-level location exposure index (LEX)**: 
Among smartphones that pinged in a given county today,
what share of those devices pinged in another county at least once during the previous 14 days?
The daily county-level LEX is an approximately 2000-by-2000 matrix in which each cell reports,
among devices that pinged today in the column county,
the share of devices that pinged in the row county at least once during the previous 14 days.

For tips on downloading and processing these data, please read the [notes for users](documentation/LEX_notes.md).
For a full description of how we compute the LEX measures, please read the [LEX documentation PDF](documentation/LEX.pdf).

## Further information and feedback

- This is ongoing work released rapidly in the context of the ongoing pandemic. The release version less than "1.0" signals that these indices have passed basic sensibility checks but are not a peer-reviewed research product.
- Please read the documentation to understand relevant caveats.
- If you have questions, suggestions, or spot a bug, please file an issue at the GitHub repository. We welcome opportunities to improve the documentation and to better understand how you might want to use these and related indices that we are developing.
- The SQL code to produce the indices will soon be available on the data warehouse [Snowflake](https://www.snowflake.com/). Researchers will be able to modify these queries to produce related indices derived from PlaceIQ's smartphone movement data.

## Coming soon

**Work in progress**:
Venue-level exposure index, Device-level exposure index, Device network-overlap index


## Acknowledgments

Victor Couture thanks the Fisher Center for Real Estate and Urban Economics at Berkeley for generous financial support.
Jonathan Dingel thanks the James S. Kemper Foundation Faculty Research Fund at the University of Chicago Booth School of Business.
Jessie Handbury thanks the Research Sponsors Program of the Wharton Zell-Lurie Real Estate Center and the Wharton Dean's Research Fund.
Kevin Williams thanks the Yale School of Management.