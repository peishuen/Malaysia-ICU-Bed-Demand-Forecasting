# Malaysia ICU Bed Demand Forecasting

## Overview

Hospitals need to know ahead of time if they are about to run out of ICU beds. If they can see this coming a week early, they can move patients, call in extra staff, or free up beds in time. Most of the time, this planning is done by looking at today's numbers and guessing.

This project builds a model that looks at recent trends (case counts, hospital admissions, testing, vaccination) and predicts how many ICU beds will likely be needed in Malaysia over the next 7 days. It works at the national level, using daily totals, not individual patient data.

## What This Project Predicts

**Main target:** Daily national ICU bed occupancy in Malaysia, 7 days into the future.

**Framing options** (starting with the first, the second is a stretch goal):
- **Regression:** predict the actual number of ICU beds occupied 7 days ahead
- **Classification:** predict a strain level (Low / Medium / High) based on how close occupancy is to total ICU capacity

Regression is the starting point since it is more standard and easier to evaluate. The classification version can be added later, since a risk level is easier to explain to a non-technical audience than a raw bed count.

## Why This Project Matters

- Uses real, official government operational data, not a cleaned Kaggle competition set
- Time-series forecasting is a different skill from typical classification portfolio projects
- Has a clear real-world impact story: this could help hospitals plan ICU capacity a week ahead
- Malaysia-specific, so it is not a copy of a common global dataset

## Data Sources

All data is free and comes from the official Ministry of Health Malaysia GitHub repository:
`https://github.com/MoH-Malaysia/covid19-public`

Key files used:
- `icu.csv` — daily ICU bed capacity and usage, national and state level
- `hospital.csv` — daily hospital admissions and discharges, national and state level
- `cases_malaysia.csv` — daily new case counts, national level
- `tests_malaysia.csv` — daily testing numbers
- `vax_malaysia.csv` — daily vaccination numbers
- `population.csv` — population figures, useful for normalizing numbers

Since this project works at national level, only the "Malaysia" rows are used from each file, and state-level columns are set aside.

## Tools and Tech Stack

- Python, pandas, numpy for data handling
- matplotlib or seaborn for plots
- statsmodels for classic time-series models
- scikit-learn and XGBoost or LightGBM for the main model
- Jupyter Notebook for the main workflow
- Git and GitHub to host the project publicly

## Project Status

Ongoing, no fixed deadline. See `tasks.md` for the full task breakdown and current progress.
