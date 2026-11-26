# Task 1: Business Understanding and Problem Framing

## The problem
PowerCo, an energy provider serving small and medium-sized businesses, is losing customers to competitors faster than average. This is called churn. The goal is to find out what is driving it.

## What we are measuring
Whether each customer churned (yes or no).

## Hypotheses
Our main suspect is a price increase. We should also check other factors, so we are not looking at price alone:
- Price increases
- Customer service problems (complaints)
- Power outages

## Data needed
For both customers who left and customers who stayed:
- Prices over time, and how much they went up
- Complaints and the problems customers faced
- Power outage records
- Business size
- How long each customer has been using the service
- Energy consumption

## How each hypothesis would be tested
- **Price:** compare the price increases of customers who left against those who stayed.
- **Outages:** compare outage counts of customers who left against those who stayed.

## Work plan
1. Collect the data and clean it
2. Explore it (EDA)
3. Create new useful columns from the raw data (feature engineering)
4. Build a model that predicts churn (yes or no) and shows how much each factor changes the chance of leaving
5. Report the insights and recommend actions
