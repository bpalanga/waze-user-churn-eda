# Waze User Churn EDA

Exploratory data analysis of Waze user data for a user churn project, done in Python as part of a Coursera data course. The notebook follows the PACE framework (Plan, Analyze, Construct, Execute).

## Notebook

* `waze_eda.ipynb`: data loading and cleaning, distributions of each variable, churn comparisons by device, distance and driving days, engineered features, and outlier handling

## What it covers

* Summary statistics and missing data checks
* Box plots and histograms for sessions, drives, kilometers driven, driving time, activity days and driving days
* Churn rate by device, by kilometers driven per driving day, and by number of driving days
* New features: `km_per_driving_day`, `percent_sessions_in_last_month`, `monthly_drives_per_session_ratio`
* Outlier handling by capping values at the 95th percentile

## Key findings

* The dataset has 14,999 users, and 700 rows are missing the churn `label`
* The overall churn rate is about 17%, and it is consistent between iPhone and Android users
* There are nearly twice as many iPhone users as Android users
* Sessions, drives, total sessions, kilometers driven and driving time are all right-skewed with large outliers, and the heaviest users drove far more than is typical
* The churn rate rises as the average distance driven per driving day increases
* The churn rate falls as users drive on more days: about 40% of users who did not drive at all in the month churned, and no users who drove 30 days churned
* About 1,000 users did not drive at all in the month, versus about 250 who did not open the app, so people open the app more than they drive
* Driving days never exceed activity days, which is a useful validity check
* Half of users had 40% or more of their sessions in just the last month, even though the median time since onboarding is almost five years, which is worth asking Waze about
* Sessions and drives are strongly correlated, so they may be redundant in a model
* Retained users tend to have fewer drives than churned users

## Open questions

* Why is the churn label missing for 700 users?
* Who are the users with extremely high drive counts, such as rideshare or commercial drivers?
* Why do long-distance users churn more, while frequent drivers churn less?

## Tools

Python, pandas, numpy, seaborn, matplotlib, Jupyter Notebook



