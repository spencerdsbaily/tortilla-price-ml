Predicting Municipal Tortilla Prices in Mexico

This project applies a supervised machine learning workflow in Python to model municipality–month variation in average tortilla prices between 2011 and 2017. The goal is to evaluate whether incorporating infrastructure-disruption indicators (in this case illegal oil tap counts), improves out-of-sample predictive performance relative to a baseline model using traditional economic predictors.


Project Motivation

Tortillas are a staple of Mexican cuisine and a central component of daily consumption for a large share of households. Changes in tortilla prices therefore have broad economic implications, particularly for lower-income populations where food expenditure represents a significant portion of total spending.

At the same time, Mexico experiences ongoing organized violence and infrastructure-related disruptions. One contemporary phenomenon is illegal oil tapping (fuel theft), which may reflect broader regional instability, market uncertainty, and supply-chain disruptions.

This project adopts a machine learning perspective to evaluate whether illegal oil tap activity contains predictive information about local tortilla prices beyond standard economic inputs. The emphasis is on predictive performance rather than causal interpretation.

I compare:

A baseline model using:

National maize price

Municipality population (log-transformed)

Year and month indicators

An extended model that additionally includes:

Illegal oil tap counts

Fuel pipeline indicator

The objective is to determine whether incorporating disruption-related indicators improves out-of-sample prediction accuracy.

This project does not claim that illegal oil taps cause tortilla price changes. Instead, it evaluates whether such indicators provide additional predictive signal within a machine learning framework.

Data

The analysis uses municipality–month panel data (2011–2017) including:

Average tortilla price (avg_tort_ppk)

National maize price per ton (Price_MXN_per_Ton)

Municipality population totals (log-transformed)

Illegal oil tap counts (illegal_tap_count)

Fuel pipeline indicator 

Year and month identifiers

Note: Raw data files may not be included in this repository. Scripts assume that data are placed in a data/ directory at the project root.

Methods

Outcome:

Average tortilla price at the municipality–month level

Model:

Gradient Boosting (XGBoost)

Predictors (Baseline Model):

National maize price

Log population

Year and month indicators

Predictors (Extended Model):

All baseline predictors

Illegal oil tap count

Fuel pipeline indicator (Franco 2023)

Validation Strategy:

Time-based train/test split

Train: 2011–2015

Test: 2016–2017

Evaluation Metrics:

Root Mean Squared Error (RMSE) on held-out test data

All preprocessing, feature engineering, model fitting, and evaluation are implemented in Python using pandas, scikit-learn, and XGBoost.

The focus of the project is workflow design, validation strategy, and transparent comparison between models rather than algorithmic complexity.

Key Result

Adding illegal oil tap indicators improved out-of-sample predictive performance by approximately 6% (measured by RMSE) relative to the baseline model.

This suggests that infrastructure-disruption indicators may contain additional predictive information about local tortilla prices beyond traditional economic inputs.