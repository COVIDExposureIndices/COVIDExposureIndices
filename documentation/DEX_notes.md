
## Notes for users of the DEX dataset

- The geographic identifiers accompanying the state-level DEX are [two-letter postal abbreviations](https://en.wikipedia.org/wiki/List_of_U.S._state_abbreviations).
The District of Columbia is the 51st geographic entity.
- The geographic identifiers accompanying the county-level DEX are [five-digit FIPS county codes](https://en.wikipedia.org/wiki/FIPS_county_code).
- The indices are reported in a [state-level file](dex_data/state_dex.csv) and a [county-level file](dex_data/county_dex.csv).
- The number of rows in the DEX file is the number of geographical units (51 states or 2,018 counties) times the number of days that we report.
- The columns of the DEX are described in [state-level codebook](state_dex_codebook.csv) and [county-level codebook](county_dex_codebook.csv)
- When reporting DEX values by a device's residential "neighborhood" characteristic, a "neighborhood" is a census block group.
- For DEX indices by census-block-group income quartile, 1 indexes the poorest quartile, and 4 the richest.
- For DEX indices by census-block-group education quartile, 1 indexes the lowest college share quartile, and 4 the highest.
