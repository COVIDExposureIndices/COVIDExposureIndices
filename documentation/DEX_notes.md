
## Notes for users of the DEX dataset

### Data layout

- The indices are reported in a [state-level file](../dex_data/state_dex.csv), a [CBSA-level file](../dex_data/cbsa_dex.csv), and a [county-level file](../dex_data/county_dex.csv).
- The number of rows in the DEX file is the number of geographical units (51 states, 904 CBSAs, or 2,018 counties) times the number of days that we report.
- The columns of the DEX are described in the [state-level codebook](state_dex_codebook.csv), [CBSA-level codebook](cbsa_dex_codebook.csv), and [county-level codebook](county_dex_codebook.csv).
- The geographic identifiers accompanying the state-level DEX are [two-letter postal abbreviations](https://en.wikipedia.org/wiki/List_of_U.S._state_abbreviations).
The District of Columbia is the 51st geographic entity.
- The geographic identifiers accompanying the CBSA-level DEX are [five-digit CBSA codes](https://www.census.gov/programs-surveys/metro-micro/about/delineation-files.html) per OMB definitions of April 2018.
- The geographic identifiers accompanying the county-level DEX are [five-digit FIPS county codes](https://en.wikipedia.org/wiki/FIPS_county_code).
- When reporting DEX values by a device's residential "neighborhood" characteristic, a "neighborhood" is a census block group.
- For DEX indices by census-block-group income quartile, 1 indexes the poorest quartile, and 4 the richest.
- For DEX indices by census-block-group education quartile, 1 indexes the lowest college share quartile, and 4 the highest.

### Data update frequency

- DEX indices are updated every weekday.
- The state-level and CBSA-level DEX indices for specific demographic groups (DEX-income, DEX-education, DEX-race) are retrospectively updated once per week to incorporate devices newly assigned to a residential block group.

### Data release history

- Version 0.8: a fresh release of all indices from January 2020. 
    - This refresh aims to provide a consistent sample of movement and devices that addresses some substantial shifts in underlying smartphone movement data sources.
    - We no longer publish the "DEX-adjusted" indices.
    - We will cease publishing all indices on 1 September 2021.
- Version 0.6.6: Added state-level density DEX and state-level residential DEX through 3 June 2020 to archive.
    - See Appendix C in 
        [the manuscript](../CDGHW.pdf)
        for definitions of state-level density DEX and state-level residential DEX.
- Version 0.6.5: CBSA-level DEX indices are added.
- Version 0.6.1: State-level DEX indices for specific demographic groups are now retrospectively updated once per week to incorporate devices newly assigned to a residential block group, starting 13 November 2020.
- Version 0.6 DEX values reflect two changes relative to version 0.5:
(1) an updated underlying basemap of residential locations
and
(2) the assignment of devices to block groups of residence based on their first available weekly residences after November 1, 2019.
- Version 0.5 was the initial release.
