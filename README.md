# Exposure indices derived from PlaceIQ movement data

## Summary

This repository contains indices describing exposure on the basis of smartphone movements.
These indices are produced by
[Victor Couture](https://economics.ubc.ca/faculty-and-staff/victor-couture/),
[Jonathan Dingel](http://www.jdingel.com),
[Allison Green](https://github.com/awasgreen), 
[Jessie Handbury](http://www.jessiehandbury.com/),
and 
[Kevin Williams](http://www.kevinrwilliams.com/),
with assistance from
Hayden Parsley,
Serena Xu,
and Shih Hsuan Hsu.
They are derived from anonymized, aggregated smartphone movement data provided by [PlaceIQ](https://www.placeiq.com/).

We are making these indices publicly available to all researchers in the context of the spread of COVID-19.
The indices, which describe (potential) exposure varying across locations and time within the United States, could be useful in a variety of applications.
The indices published here cover January 2020 to present, with a seven-day lag.

When using these indices, please cite "[Measuring movement and social contact with smartphone data: a real-time application to COVID-19](CDGHW.pdf)" ([*JUE*](https://doi.org/10.1016/j.jue.2021.103328), [BibTeX](http://www.jdingel.com/research/CDGHW.bib)) by Couture, Dingel, Green, Handbury, and Williams.
The paper describes properties of smartphone data, compares the residential distribution and movement patterns of devices to those in traditional data sources, and discusses potential measurement issues that arise in the context of the ongoing pandemic.

We thank Drew Breunig, Nicholas Sheilas, Stephanie Smiley, Elizabeth Cutrone, and the team at PlaceIQ for their ongoing help.
This data release was approved by the University of California, Berkeley Office for Protection of Human Subjects under CPHS Protocol No 2018-05-11122
and the University of Chicago Institutional Review Board under protocol IRB20-0967.

## June 2021 Update

Version 0.8 (released 10 June 2021) is a complete refresh of the exposure indices covering January 2020 to present.
This refresh aims to provide a consistent sample of movement and devices that addresses some substantial shifts in underlying smartphone movement data sources.
While the sample of devices differs, the indices in this release are computed exactly as previous versions were.

Spatial and temporal variation in the number and characteristics of devices underlying these indices is inevitable.
As noted in the documentation below and the companion research paper, we recommend research designs that incorporate date and place fixed effects to address temporal and cross-sectional variation that may reflect idiosyncratic smartphone patterns.

We will discontinue publication of all our indices on 1 September 2021.
Version 0.8 no longer includes the adjusted device exposure index ("DEX-adjusted").
That series was created to address devices sheltering in place and dropping out of our sample early in pandemic.
Given substantial fluctuations in the number of devices in the more than 16 months of data published thus far,
that concern is no longer relevant.

## Data description

The following indices are available as (compressed) CSV files in this GitHub repository.

### [Location exposure indices](lex_data)

Currently version 0.8.

- **State-level location exposure index (LEX)**: 
Among smartphones that pinged in a given state today,
what share of those devices pinged in each state at least once during the previous 14 days?
The daily state-level LEX is a 51-by-51 matrix in which each cell reports,
among devices that pinged today in the column state,
the share of devices that pinged in the row state at least once during the previous 14 days.

- **County-level location exposure index (LEX)**: 
Among smartphones that pinged in a given county today,
what share of those devices pinged in each county at least once during the previous 14 days?
The daily county-level LEX is an approximately 2000-by-2000 matrix in which each cell reports,
among devices that pinged today in the column county,
the share of devices that pinged in the row county at least once during the previous 14 days.

In version 0.8, LEX values are available for each Wednesday and Saturday since January 20, 2020.

For tips on downloading and processing these data, please read the [notes for users](documentation/LEX_notes.md).
For a full description of how we compute the LEX measures, please read the [LEX documentation PDF](documentation/LEX.pdf).

### [Device exposure indices](dex_data)

Currently version 0.8.

- **State-level device exposure index (DEX)**: 
For a smartphone residing in a given state, how many distinct devices also visited any of the commercial venues that this device visited today?
The state-level DEX reports the state-level average of this number across all devices residing in the state that day.
The DEX values are necessarily only a fraction of the number of distinct individuals that also visited any of the commercial venues visited by a device, 
since only a fraction of individuals, venues, and visits are in the device sample.
	- DEX-income reports the state-level average of this number for the four groups of devices residing in each of four neighborhood-income quartiles.
	- DEX-education reports the state-level average of this number for the four groups of devices residing in each of four neighborhood-college-share quartiles.
	- DEX-race reports the state-level average of this number for four ethnic/racial demographic groups, weighting each device by the share of its neighborhood residents who belong to the ethnic/racial demographic group.

- **CBSA-level device exposure index (DEX)**:
For a smartphone residing in a given core-based statistical area (CBSA), how many distinct devices also visited any of the commercial venues that this device visited today?
CBSA-level counterparts of the state-level measures listed above are available.

- **County-level device exposure index (DEX)**: 
For a smartphone residing in a given county, how many distinct devices also visited any of the commercial venues that this device visited today?
The county-level DEX reports the county-level average of this number across all devices residing in the county that day.
The DEX values are necessarily only a fraction of the number of distinct individuals that also visited any of the commercial venues visited by a device, 
since only a fraction of individuals, venues, and visits are in the device sample.

These indices are reported in a [state-level file](dex_data/state_dex.csv), a [CBSA-level file](dex_data/cbsa_dex.csv), and a [county-level file](dex_data/county_dex.csv).
For a codebook and tips on downloading and processing these data, please read the [notes for users](documentation/DEX_notes.md).
For a full description of how we compute the DEX measures, please read the [DEX documentation PDF](documentation/DEX.pdf).

State-level density DEX and residential DEX values through 3 June 2020 are available in the [archive](archive) folder.
See Appendix C of [the manuscript](CDGHW.pdf) for details of these indices.

## Further information and feedback

- This is ongoing work released rapidly in the context of the ongoing pandemic. The release version less than "1.0" signals that these indices have only passed basic sensibility checks.
- Please read the documentation to understand relevant caveats.
- If you have questions, suggestions, or spot a bug, please file an issue at the GitHub repository. We welcome opportunities to improve the documentation and to better understand how you might want to use these and related indices that we are developing.

## Acknowledgments

These indices are based upon work supported by the National Science Foundation under Grant No. 2030056.
Victor Couture thanks the Fisher Center for Real Estate and Urban Economics at Berkeley for generous financial support.
Jonathan Dingel thanks the James S. Kemper Foundation Faculty Research Fund and Initiative for Global Markets at the University of Chicago Booth School of Business.
Jessie Handbury thanks the Research Sponsors Program of the Wharton Zell-Lurie Real Estate Center and the Wharton Dean's Research Fund.
Kevin Williams thanks the Yale School of Management.

For helpful feedback and reactions to our data and documentation,
we thank Gabriel Kreindler.
