# Fintech Onboarding A/B Test

**Status:** In progress (2 of 11 steps complete)

An end-to-end analytics project testing whether a redesigned onboarding flow gets more new users of a simulated fintech app to fund their accounts, and how that result shows up in financial KPIs.

## Business question

An banking app has created a new sign-up process and wants to test it out with its users. Half of the users of the app will be assigned the new version of the sign-up process while the other half remains with the old one. I wanted to see if I can notice an increase in users who put money into their account, and if they did how much of the money comes from the new sign-up process.

## What's built so far

- Reproducible synthetic dataset of 10,000 users, generated with pandas and Python random module
- Weighted sampling for a realistic mix of acquisition channel, device, age band and state
- Random assignment of every user to control or treatment
- Validation checks before saving: unique IDs, matching row counts, no missing values

## Roadmap

- [x] Setup
- [x] Generate users and experiment assignments
- [ ] Generate sessions, events (signup → ID check → first deposit), accounts and transactions
- [ ] Load into MySQL with primary and foreign keys
- [ ] SQL analysis: funnel by variant, cohorts and KPIs
- [ ] A/B test: two-proportion z-test at 95% confidence, confidence intervals and a power check
- [ ] Python charts with seaborn and matplotlib
- [ ] AI-assisted data validation with the Claude API, with every flag verified by hand
- [ ] AWS S3 storage with boto3
- [ ] Power BI dashboard with 6+ financial KPIs
- [ ] Findings memo and data dictionary

## Tech stack

**Current:** Python (pandas), Jupyter, Git

**Planned:** MySQL, statsmodels, SciPy, seaborn, matplotlib, Anthropic Python SDK, AWS S3 (boto3), Power BI

## How to run

```
git clone https://github.com/natemelendez42-ui/fintech-ab-test.git
cd fintech-ab-test
pip install pandas numpy jupyter
jupyter notebook stage1_generate_data.ipynb
```

Run all cells. The notebook creates `data/users.csv` and `data/experiment_assignments.csv`.

## About the data

All data is synthetic. No real customer information is used. The generated CSV files are not committed to the repo; running the notebook with the fixed seed (42) recreates them exactly.

## Author

Nathan Melendez, B.S. Information and Decision Sciences (Business Analytics), University of Illinois Chicago
