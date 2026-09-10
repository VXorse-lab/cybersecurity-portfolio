# Transaction Threat Detection and Fraud Risk Assessment

## Project Overview

This project analyzes a fictional financial transaction dataset to identify suspicious activity and assess potential fraud risks.

The analysis focused on risk scores, transaction amounts, transaction frequency, device changes, failed attempts, transaction channels, locations, and customer activity. The goal was to identify patterns that could help a security analyst decide which transactions or accounts require further investigation.

## Dataset

The dataset contains 1,500 fictional financial transactions.

Key fields analyzed included:

- Transaction amount
- Transaction type
- Transaction channel
- Region
- Device ID
- Transaction status
- One-hour transaction velocity
- Device changes
- Failed attempts
- Risk score

## Analysis Approach

I first reviewed the dataset for missing values and inconsistent data. I then grouped transactions by risk level and examined high-risk transactions in greater detail.

Rather than relying only on the risk score, I compared it with behavioural indicators such as transaction velocity, failed attempts, device changes, customer activity, channel, and region.

I also reviewed repeated activity at the customer level to identify accounts that could require further investigation.

## Key Findings

- 308 transactions, representing 20.5% of the dataset, had a risk score of 80 or higher.
- 237 high-risk transactions were recorded as successful, with a combined value of GHS 55,282.48.
- CUST0099 showed repeated high-risk activity combined with multiple risk indicators and was identified as an investigation lead.
- Transaction velocity, failed attempts, and device changes provided useful supporting signals.
- Missing information reduced the confidence of some automated detection rules.

## Investigation Logic

A risk score of 80 or higher was treated as an investigation trigger, not proof of fraud.

Priority increased when high risk was combined with:

- High transaction velocity
- Multiple failed attempts
- Device changes
- Repeated high-risk activity
- Unusual combinations of channels or regions

Successful high-risk transactions were also reviewed because they may indicate gaps between detection and transaction prevention.

## Security Recommendations

Based on the analysis, I recommended:

- Step-up authentication for high-risk transactions.
- Monitoring transaction velocity and repeated failed attempts.
- Alerts for unusual device changes.
- Account-level investigation of repeated suspicious behaviour.
- Maintaining an audit trail for incident investigation.
- Testing detection rules against confirmed legitimate and fraudulent transactions.

## Limitations

The dataset is fictional and does not contain confirmed fraud labels. Therefore, the analysis identifies risk patterns rather than proving that a transaction or customer is fraudulent.

The dataset also lacks important investigation fields such as IP addresses, authentication details, beneficiary history, precise location data, and confirmed incident outcomes.

## Skills Demonstrated

- Cybersecurity analysis
- Fraud and anomaly detection
- Risk assessment
- Pattern recognition
- Transaction analysis
- Threat investigation
- Security monitoring
- Data analysis

## Future Improvements

With additional time, I would build a small detection pipeline, introduce customer and device baselines, and test the detection rules against confirmed legitimate and fraudulent transactions.

The goal would be to measure false positives, missed attacks, and detection performance.
