# College Major Selection \& Shift Analysis

**Author:** Kanit Mann
**MS Data Science | University of Arizona**

## Overview

This project investigates how the most popular and lucrative college majors in the U.S. have changed from 2009–2023, with a special focus on whether wage growth predicts shifts in major popularity.

Leveraging nationally representative microdata from IPUMS USA, the analysis explores trends in graduate numbers and median earnings by major, and examines how changes in pay influence students’ choices over time.

## Research Questions

- **How have the most popular college majors changed over time in the U.S.?**
- **Do changes in major popularity correspond to changes in typical post-graduation earnings?**
- **Is there evidence that increases in pay drive major selection, or vice versa?**


## Data Source

- **IPUMS USA Microdata**
[IPUMS USA](https://usa.ipums.org/usa/) | University of Minnesota
    - American Community Survey (ACS) data, 2009–2024
    - ~45 million records
    - Detailed fields on degree, employment, earnings, and demography

**Note:** 2020 data is excluded due to pandemic-era survey disruptions and experimental weighting per Census Bureau guidelines.

## Variables Used

- `YEAR` — Census/survey year
- `AGE`, `SEX`, `RACE` — Demographics
- `EDUC`, `EDUCD` — Educational attainment
- `DEGFIELD`, `DEGFIELDD` — College major (broad/detailed)
- `EMPSTAT` — Employment status
- `CLASSWKR` — Class of worker
- `INCWAGE` — Annual wage and salary income
- `PERWT` — Person-level weight (for national representativeness)


## Methodology

- **Data Cleaning:** Filtered for employed graduates with valid (positive) wage.
- **Label Mapping:** Used code-to-name mappings for degree fields.
- **Aggregation:** Weighted counts and median wages per major per year.
- **Visualization:** Seaborn/Matplotlib line plots to show temporal trends.
- **Interpretation:** Linked shifts in student preferences to wage signals.


## Key Results

- **Accounting** remained a favorite and grew by 16.6% over ten years, even as other business majors declined.
- **Computer Engineering** had the highest median wage and saw a 40% pay increase, with student interest rising alongside wage growth.
- Majors with the fastest wage growth attracted the most students, suggesting college major choice closely tracks pay trends.
- Shifts in broad fields (like decline of General Business and rise of Psychology/Biology) may reflect broader socio-economic or cultural factors.


## Actionable Insights

- **Universities:** Should consider investment in Computer Engineering and Accounting programs—both show strong and growing student demand plus high wage outcomes.
- **Students:** Choosing majors in fast-growing, high-wage fields is supported by historical data.
- **Further Research:** Explore causal inference or lag effects, disaggregate by race/gender/degree level, analyze recent vs. older grads.


## Usage

### Prerequisites

- Python 3.x
- `pandas`, `seaborn`, `matplotlib`


### Data Access

1. **Request \& Download:**
    - Register and download ACS microdata from [IPUMS USA](https://usa.ipums.org/usa-action/variables/group)
    - Required variables are specified in the project notebook/script.
2. **Place Data File:**
    - Put CSV (e.g., `usa_00001.csv`) inside `data/` folder at project root.

### Running the Analysis

Open and run `analysis.ipynb` after the `degfield_map.py` script:

```bash
# Example:
python degfield_map.py
```

Edits to variable/path may be required based on data download.

## Repository Structure

- `analysis.ipynb` - Main exploratory data analysis and visualization
- `degfield_map.py` - Degree field code-to-name dictionary
- `IPUMS_codebook.pdf` - Codebook PDF provided by IPUMS 
- `README.md` - Project documentation (this file)


## Limitations

- 2020 data omitted due to COVID-19 survey disruptions.
- Analysis does not formally test causality or lagged effects.
- Undergraduate and graduate degrees not separated in current cuts.


## References

- IPUMS USA, University of Minnesota. [www.ipums.org](https://usa.ipums.org/usa/)
- ACS PUMS COVID-19 Methodology Guidance

***

**Contact:**
For questions or collaboration, reach out via [LinkedIn](https://www.linkedin.com/in/kanitmann) or via [GitHub Issues](https://github.com/kanitmann01/college-major-shift-analysis/issues).
