## Fraud Risk Scoring (Rule-Based Approach)

This project implements a rule-based fraud risk scoring system to estimate the probability of a transaction being fraudulent based on key risk factors. The risk score ranges from 0 (low risk) to 1 (high risk) and is computed using predefined business rules.

### Risk Factors Considered:

1. **High Transaction Amount**: Transactions above $1,000 receive a higher risk score.
2. **Late-Night Transactions**: Transactions made between 12 AM and 4 AM are flagged as potentially suspicious.
3. **Frequent Transactions Per User**: Users making more than 5 transactions in a short period may indicate fraud.
4. **Age-Based Risk Adjustments**:
    - Young Customers (18-25): Large transactions (>$500) are considered unusual.
    - Older Customers (60+): Digital transactions (e.g., online purchases, cryptocurrency) may indicate fraud.
5. **High-Risk Locations**: Transactions originating from known high-risk regions are given a higher score.
6. **Rapid Transaction Frequency**: If a transaction occurs within 1 hour of a user’s previous one, it is flagged as suspicious due to potential bot or automation behavior.

### How It Works:
- Each transaction starts with a base fraud risk score of `0`.
- Risk points are added based on the conditions above.
- A flag `HighRiskFlag` is set to `True` for transactions scoring 4 or more points before normalization.
- The final `FraudRiskScore` is normalized between 0 and 1 to ensure comparability across transactions.

# Output:
The processed dataset includes a new column: 

- `FraudRiskScore`: A normalized score from 0 to 1.
- `HighRiskFlag`: A boolean indicator for clearly high-risk transactions.
- Other engineered features like `UserTransactionCount` and `TimeSinceLastTransaction` for further analysis.