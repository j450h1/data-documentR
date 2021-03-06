# data-documentR
An idea for an R package to help your write metadata for .csv files and data.frames

The idea is to make it as easy as possible for researchers to document their data.  The output would ideally be a .md file.  The input could be an entire data folder, a single (or multiple) .csv files, or R objects.  To use it on .csvs, the function(s) would read in the .csv with `read_csv()` and then prompt the user for a short description reminding them to include info like date and location of the data and maybe a licence or something?  Then, it would go through each column in the tibble and prompt the user for metadata.  For numeric columns, it would ask for a description and units (maybe this could work with the `units` package?), for character columns it would ask for a description and then ask if it should be a factor.  For factors, it would prompt a description for each level (if there were, say <5 levels).  All of this would be converted to a nicely formatted .md file and output to the same directory as the .csv file.  If run on R objects, the function would write both the metatdata .md and the R objects as .csv or .rds files.

## Example output

### File: dataset1.csv
### Description: plant growth data that was collected between june 2011 and july 2012 at the boston area climate experiment in Waltham, MA.
### Columns:

- `species`: The plant species used.  
    Levels:
     - `AM`: Achillea milfolium
     - `PL`: Plantago lanceolata
- `height`: Plant height from ground to longest leaf in cm
- `date`: Date of measurment in ISO 8601 format \[this could be autmatically generated if the column is class `date`\]
- `plot`: A plot ID to be used as a blocking factor

### File: dataset2.csv
...
     
## additional related ideas:

- metadata for .R scripts (descriptions, what to they read in, what do they output--this could be automated)


