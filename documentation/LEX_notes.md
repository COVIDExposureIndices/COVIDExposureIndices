
## Notes for users of the LEX matrices

- The geographic identifiers accompanying the state-level LEX are [two-letter postal abbreviations](https://en.wikipedia.org/wiki/List_of_U.S._state_abbreviations).
- The geographic identifiers accompanying the county-level LEX are [five-digit FIPS county codes](https://en.wikipedia.org/wiki/FIPS_county_code).
- Please remember that these are not transition matrices because a phone can visit multiple counties in a 14-day period. The columns do not sum to one.
- We report the LEX data as square matrices in CSV files.
If you want to reshape them to be "long" (N<sup>2</sup> rows with two identifier columns and one column of data), this can be done quickly. 
[Stata](http://www.stata.com)'s "reshape" command will not do this quickly for a 2000-by-2000 matrix.
Try something like this Python script:
```
import pandas as pd
url = 'https://github.com/COVIDExposureIndices/COVIDExposureIndices/blob/master/lex_data/county_lex_2020-01-20.csv.gz?raw=true'
df 	= pd.read_csv(url, compression='gzip', header=0)
countys = df.columns.values[1:]
col_names = dict(zip(countys, ["a" + lab for lab in countys]  ))
df 	= df.rename(columns = col_names)
df_long	= pd.wide_to_long(df, stubnames="a", i=['COUNTY_PRE'], j='col')
df_long = df_long.reset_index(drop=False)
df_long = df_long.rename(columns = {"col" : "COUNTY", "a" : "LEX"})
df_long.to_csv(r'reshaped.csv',index=False)
```