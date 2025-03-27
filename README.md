# Fraudulent-Transactions
A machine learning project to detect and classify fraudulent financial transactions. This repository contains data exploration, feature engineering, and model building steps aimed at identifying potential fraud with high accuracy and recall.

## Project Overview
The goal of this project is to develop a robust fraud detection system using historical transaction data. The notebook applies several classification algorithms, including Random Forest, XGBoost, Logistic Regression, and others. Through feature engineering and data preprocessing, we aim to identify the key factors contributing to fraudulent behavior.

## Key Objectives
- Explore and understand transaction patterns.
- Engineer meaningful features to improve fraud detection accuracy.
- Evaluate multiple machine learning models and select the best performer.
- Deploy or integrate the final model for practical use cases in detecting fraud in real-time or batch processes.

## Data Description
We used a large dataset of financial transactions. Each row includes:
- step: Time step of the transaction (in hours).
- type: Transaction type (e.g., CASH_IN, CASH_OUT, PAYMENT, TRANSFER).
- amount: The amount of the transaction.
- oldbalanceOrg, newbalanceOrg: Original account’s balance before and after the transaction.
- oldbalanceDest, newbalanceDest: Destination account’s balance before and after the transaction.
- isFraud: Binary label indicating whether the transaction is fraudulent (1) or not (0).
- isFlaggedFraud: Flag raised by the system for transactions over a certain threshold.

## Feature Engineering
1. Balance Difference Flags: `orig_diff` and `dest_diff` detect inconsistencies in how much money leaves the sender’s account vs. how much is received by the destination.
2. High-Value Transactions (Surge Indicator): Flags transactions that exceed a certain threshold (e.g., 75th percentile).
3. Frequency Indicator: Flags destination accounts receiving money from many different senders (e.g., more than 20).
4. Merchant Indicator: Identifies merchant accounts (IDs starting with 'M') which have different transaction patterns.

## Modeling
Multiple classification algorithms were tested:
1. Logistic Regression
2. K-Nearest Neighbors
3. Support Vector Machine
4. Naive Bayes
5. Random Forest
6. XGBoost

The best-performing model in cross-validation was Random Forest, achieving near 100% accuracy on the validation set with high recall for fraud cases.

## Results
- The Random Forest model demonstrated near-perfect accuracy (close to 100%) on the validation dataset, with ~98% recall for fraudulent cases.
- The feature engineering approach (balance difference flags, surge indicators, etc.) significantly improved detection of suspicious transactions.
- The final model is effective at catching fraudulent transactions while minimizing false alarms.

## Contributing
- Contributions are welcome! To propose changes:
- Fork the repository.
- Create a new branch for your feature or bug fix.
- Commit and push your changes.
- Open a pull request with a detailed explanation.
