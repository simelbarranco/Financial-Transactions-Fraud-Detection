## Fraud Risk Scoring (Rule-Based Approach)

This project implements a rule-based fraud risk scoring system to estimate the probability of a transaction being fraudulent based on key risk factors. The risk score ranges from 0 (low risk) to 1 (high risk) and is computed using predefined business rules.

### Risk Factors Considered:

1. **High Transaction Amount**: Transactions above $1,000 receive a higher risk score.
2. **Late-Night Transactions**: Transactions made between 12 AM and 4 AM are flagged as potentially suspicious.
3. **Frequent Transactions Per User**: Users making more than 5 transactions in a short period may indicate fraud.
4. **Age-Based Risk Adjustments**:
    - Young Customers (18-25): Large transactions (>$500) are considered unusual.
    - Older Customers (60+): Digital transactions (e.g., online purchases, cryptocurrency) may indicate fraud.

### How It Works:
- Each transaction starts with a base fraud risk score of 0.
- Based on the conditions above, points are added to the score.
- The score is then normalized between 0 and 1 to make it comparable across all transactions.

# Output:
- The processed dataset includes a new column: `FraudRiskScore`, which helps analyze fraud trends in Power BI.








