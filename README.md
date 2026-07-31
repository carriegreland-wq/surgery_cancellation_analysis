# 🏥 Day-of Surgery Cancellation Analysis

This project analyzes same-day surgery cancellations to identify leading 
causes, high-risk specialties, and cost impact — helping OR scheduling 
teams target interventions that reduce wasted OR time and improve patient 
outcomes.

## Problem Statement
Same-day surgery cancellations waste critical OR time, delay patient care, 
and create significant financial losses for hospitals. With 11 years of OR 
scheduling experience, I designed this analysis to quantify what drives 
cancellations and where interventions will have the greatest impact.

## Stakeholder Questions
1. What are the leading reasons for same-day cancellations?
2. Which surgical specialties have the highest cancellation rates?
3. Do cases scheduled later in the day have higher cancellation rates?
4. Is there a relationship between patient age, ASA status, and cancellation reason?
5. What is the estimated cost impact of cancellations by reason?

## Tools & Technologies
- **Python (pandas, numpy)** — synthetic data generation
- **SQLite** — SQL analysis written in MySQL syntax
- **Tableau Public** — operational dashboard
- **Google Colab** — project notebook

## Dataset
Two synthetic datasets generated to simulate real OR scheduling records,
with cancellation reason distributions informed by published clinical research:
- `scheduled_surgeries` — 1,200 surgeries with specialty, scheduled time,
  age, ASA status, and interpreter needed flag
- `cancellations` — 1,200 records with cancellation reason and estimated
  cost impact

Tables joined on `surgery_id`. Overall cancellation rate: 12.25%

## SQL Concepts Demonstrated
- `JOIN` — connecting two tables on a shared key
- `GROUP BY` + `COUNT` + `AVG` — aggregating by reason, specialty, time
- `CASE WHEN` — bucketing scheduled hours into Morning/Midday/Afternoon
- `WHERE` + `IN` — filtering by cancellation status and reason
- **Subquery** — calculating percentage of total cancellations per reason
- `ROUND` + `AVG` — average cost per cancellation reason

## Key Findings
- Lack of OR Time drives 63.3% of cancellations — a scheduling and block
  management issue, not a patient behavior problem
- Gynecologic surgery has the highest cancellation RATE at 22.1% — nearly
  double the next specialty despite not having the highest raw volume
- Cancellation rates are consistent across time of day (11.1%–13.9%),
  suggesting time of day is not a primary driver
- Medical cancellations (NPO violations, medications, BP) are evenly
  distributed across all age groups — not concentrated in elderly patients
- Lack of OR Time generates $362,989 in estimated cost impact — nearly
  5x more than the next highest reason (Patient No-Show at $74,213)

## Recommendation
Prioritize block scheduling review and realistic case duration estimates
to address the 63.3% of cancellations driven by Lack of OR Time. Implement
multi-touch patient reminder protocols to reduce the $74,213 in No-Show
costs. Conduct a focused review of Gynecologic scheduling practices given
its 22.1% cancellation rate — nearly 1 in 4 cases cancelled.

## Dashboard
[View on Tableau Public](https://public.tableau.com/app/profile/carrie.greland/viz/SameDaySurgeryCancellationAnalysis/Dashboard1)

## Notebook
[View in Google Colab](https://colab.research.google.com/drive/14LmKSBxCzGECo6up2uwFrFZrkD7jmXOp)

## Files
- `surgery_cancellation_analysis.ipynb` — full project notebook
- `Surgery_Cancellation_Dashboard.png` — dashboard screenshot
