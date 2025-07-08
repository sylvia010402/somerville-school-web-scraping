# Tracking Demographics in Somerville Schools: Two Decades of Change

## Repository Structure

```
somerville-school-demographics/
├── README.md
├── docs/
│   ├── final_report.pdf
├── code/
|   ├── README.md
│   └── somerville_school_demographics.Rmd
└── results/
    ├── README.md
    ├── demographic_trends.png
    ├── somerville_school_data.csv
    └── somerville_school_data.rds
```

As an education policy student, I kept hearing debates about school choice—whether giving families options leads to better outcomes or just creates new forms of segregation. But most research looks at snapshots or short time periods. I wanted to see what actually happens when a community tries to balance choice with equity over twenty years.

Somerville, Massachusetts gave me the perfect case study. It's a progressive city that lets families apply to any school regardless of where they live. The story begins with the [Arthur D. Healey School](https://profiles.doe.mass.edu/profiles/student.aspx?orgcode=02740075&orgtypecode=6&&fycode=2022), which underwent a significant transformation during this period. Originally divided into two programs within one building—a "choice" school with active parent involvement, project-based learning, and arts integration alongside a traditional neighborhood school—the Healey merged these programs in pursuit of educational equity. I wondered: Does this kind of intentional integration work? Do we see "white flight" when schools become more diverse? How do enrollment patterns evolve when families have genuine choice? This web scraping project provided an opportunity to track how demographic patterns respond to programmatic changes, offering insights valuable for educators, administrators, and education technology platforms seeking to understand enrollment dynamics.


## What I Built

To answer these questions, I needed data that didn't exist in a convenient format. So I built a web scraping system to systematically collect enrollment demographics from the Massachusetts Department of Education's school profiles—140 pages covering 7 schools across 20 years (2005-2024). 

The technical challenge was more complex than I initially expected. Each year used slightly different web formats, demographic categories changed over time, and I had to be respectful to state servers while collecting nearly a thousand data points. But the result was a comprehensive longitudinal dataset that reveals patterns invisible in typical annual reports.


## What the Data Reveals

![alt text](results/demographic_trends.png)

The story that emerged was more nuanced than simple "choice leads to segregation" narratives. There is a clear demographic sorting—some schools remain predominantly white while others serve primarily Hispanic or Latino students. But the Healey School's transformation shows that intentional integration efforts can work. After merging its programs, it became one of the most diverse schools in the district and stayed that way.

The data also reveals broader demographic shifts reshaping the district. Hispanic or Latino enrollment grew from 30% to over 40% district-wide, while white enrollment declined correspondingly. But this wasn't uniform "white flight"—some schools maintained stable demographics even as others changed dramatically.

Perhaps most importantly, the analysis suggests that structural factors beyond formal policies drive family choices. Transportation, information access, and program placement all seem to influence which families end up at which schools, even in a system designed to provide equal access.


## Technical Approach

The project required building a robust web scraping framework that could handle:
- **Evolving website structures** across 20 years of state data systems
- **Inconsistent formatting** in government data tables
- **Respectful data collection** with appropriate delays and error handling
- **Longitudinal harmonization** to ensure apples-to-apples comparisons over time

I used R with rvest for scraping, implementing retry logic and systematic validation to ensure data quality. The final dataset includes demographic percentages, absolute enrollment numbers, and comparative state/district context for each school-year combination. Detailed methodology can be found in the [final report](docs/final_report.pdf).

## Policy Implications

The findings suggest that achieving meaningful integration in choice systems requires more than good intentions. Successful diversity—like at the Healey School—seems to require:
- **Proactive demographic planning** rather than hoping choice naturally creates balance
- **Addressing structural barriers** like transportation and information access
- **Distributing attractive programs** across schools to reduce sorting incentives
- **Continuous monitoring** to catch problematic trends early

For education technology companies and policy organizations, this analysis demonstrates the value of longitudinal demographic tracking and suggests opportunities for tools that help districts monitor and maintain integration goals.

## Dataset

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

## Lessons Learned

This project reveals that meaningful education research often requires building your own datasets. Government data exists, but not always in analysis-ready formats. The technical challenges of web scraping, handling errors, ensuring data quality, mirroring the broader challenges of education policy research: being systematic, patient, and careful about drawing conclusions from messy real-world data. It reinforced the fact that behind every data point are real families making choices about their children's education. The patterns we see in enrollment numbers reflect complex decisions about identity, opportunity, and belonging that deserve both rigorous analysis and deep empathy. 

**Methods**: Web scraping, longitudinal data analysis, demographic trend visualization  
**Tools**: R, rvest, tidyverse, ggplot2  
**Data Source**: Massachusetts Department of Elementary and Secondary Education
