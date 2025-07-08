## This directory contains the following files:
- **demographic_trends.png**: Visualizations from the scrapped data
- **somerville_school_data.csv**: Scrapped data in csv format, output from the step 4 in the [codes](..codes/somerville_school_demographics.Rmd)
- **somerville_school_data.rds**: Scrapped data in rds format, output same as above

# Data Dictionary

The final dataset contains 966 observations with the following variables:

- **year**: Academic year (2005-2024)
- **schoolID**: Massachusetts Department of Education school identifier (7-digit numeric code)
- **school**: School name (Healey, Argenziano, Brown, Kennedy, EastSomerville, SomervilleHigh, WestSomerville)
- **Category**: Racial/ethnic demographic category as reported by MA DOE
  - American Indian or Alaska Native
  - Asian
  - Black or African American
  - Hispanic or Latino
  - Multi-Race, Not Hispanic or Latino
  - Native Hawaiian or Other Pacific Islander
  - White
- **School**: Percentage of school enrollment in this demographic category
- **District**: Percentage of district-wide enrollment in this demographic category (for comparison)
- **State**: Percentage of statewide enrollment in this demographic category (for comparison)
- **total**: Total school enrollment for this year
- **category_abrv**: Abbreviated demographic labels (AIAN, Asian, Black, Latino, Multi-Race, NHPI, White)

