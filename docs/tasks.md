# Tasks

See `README.md` for the full project introduction. This file tracks the task breakdown by phase.

## Phase 0: Setup
- [ ] Create a project folder and a Git repository
- [ ] Set up a Python environment (pandas, numpy, scikit-learn, matplotlib, seaborn)
- [ ] Clone or download the MoH Malaysia GitHub repository

## Phase 1: Get and Understand the Data
- [ ] Load each CSV file and check the date range covered
- [ ] Check what each column means (read the repository's README)
- [ ] Confirm which rows are national level versus state level
- [ ] Merge the files together into one table, joined by date

## Phase 2: Clean the Data
- [ ] Check for missing dates or missing values in each file
- [ ] Decide how to handle gaps (forward fill, interpolation, or drop)
- [ ] Check for reporting errors or odd spikes (for example, a data correction day)
- [ ] Make sure all dates are in the same format and sorted correctly

## Phase 3: Explore the Data (EDA)
- [ ] Plot ICU occupancy over time to see waves and trends
- [ ] Plot cases, hospital admissions, and ICU occupancy together to see how they relate and how much of a delay there is between them
- [ ] Check correlation between testing rate, case counts, and ICU occupancy
- [ ] Look at how vaccination rollout changed the relationship between cases and ICU occupancy over time
- [ ] Write down 3 to 5 clear findings from this step, these will be useful later for the write-up

## Phase 4: Build Features
- [ ] Create lag features (for example, cases 7, 14, 21 days ago)
- [ ] Create rolling averages (for example, 7-day average of new cases)
- [ ] Create a feature for ICU capacity utilization rate (occupied beds divided by total beds)
- [ ] Add vaccination coverage as a feature
- [ ] Add day-of-week or seasonal indicators if relevant
- [ ] Split the data into training and test sets by time (never shuffle randomly for time series, always split by date)

## Phase 5: Build Models
- [ ] Build a simple baseline model first (for example, "tomorrow's ICU occupancy equals today's occupancy") to have something to compare against
- [ ] Try a classic time-series model (for example, ARIMA or exponential smoothing)
- [ ] Try a tree-based model (for example, XGBoost or LightGBM) using the lag and rolling features
- [ ] Optional stretch: try a simple LSTM or other sequence model if you want to show deep learning skills

## Phase 6: Check How Good the Model Is
- [ ] Use time-based cross-validation (train on earlier dates, test on later dates), not random splits
- [ ] Measure error using MAE and RMSE, compare against the baseline
- [ ] Check where the model does worst (for example, during a sudden wave) and think about why
- [ ] If the classification version was built, check precision and recall for the "High strain" class specifically, since missing a high-strain warning matters more than a false alarm

## Phase 7: Explain the Results
- [ ] Show which features matter most to the model (feature importance)
- [ ] Write a short plain-English summary of what the model can and cannot do
- [ ] Be honest about limitations (for example, the model cannot predict a brand new variant or a policy change)
- [ ] Write up the project as a notebook or report, including EDA findings, model comparison, and conclusions

## Phase 8: Optional Extensions (only if there is extra time)
- [ ] Add the classification "strain level" version as a second model
- [ ] Build a simple dashboard (for example, using Streamlit) to show the forecast visually
- [ ] Extend the model to forecast hospital admissions as well as ICU occupancy
- [ ] Write a short blog-style article about the project for a portfolio site or LinkedIn

## Final Deliverables
- [ ] A public GitHub repository with clean code and a clear README
- [ ] A notebook or report covering the full process from raw data to final model
- [ ] A short summary section explaining the problem, approach, and result, written so a recruiter with no ML background can understand it
