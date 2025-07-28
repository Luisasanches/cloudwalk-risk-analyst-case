# CloudWalk Risk Analyst – Technical Challenge

This repository contains my submission for the Risk Analyst I technical challenge at **CloudWalk**. The project is divided into three main parts:

## Part 2.1 – Understanding the Payment Industry

Theoretical explanations about:  
- The money and information flow in the acquiring market  
- Differences between acquirers, sub-acquirers, and gateways  
- What chargebacks are and how they relate to fraud  

See: [Part 2.1 - Industry](./2.1_theory/part-2.1-industry.md)

---

## Part 2.2 – Case Analysis and Response

In this section, we analyze the chargeback case presented by the client and provide a professional response addressing the situation, explaining the outcome, and suggesting next steps.

See: [Reply.md](./2.2-Case Analysis/Reply.md)

---

## Part 3.1 / 3.2 – Analysis and Anti-Fraud Strategy

### Data Exploration

Using `pandas`, I conducted exploratory data analysis to understand the characteristics and patterns in the transaction dataset. Key insights include:

- **Fraud Concentration**: Fraudulent transactions represent a small portion of the total but are concentrated in specific user behaviors and time patterns.  
- **Transaction Value**: Fraudulent transactions tend to have slightly higher average amounts compared to legitimate ones.  
- **Transaction Frequency**: Some users attempt several transactions within short time frames, which is a potential red flag for bot-like or malicious behavior.  
- **User History**: Users involved in fraud often have earlier signs of suspicious behavior, such as repeated small-value transactions or sudden increases in volume.

### Anti-Fraud Strategy

Based on the insights above, I designed a strategy combining data-driven rules and modeling:

#### Behavioral Rules

- Block users making **5 or more consecutive attempts**.  
- Block transactions if a user exceeds **R$5,000 within 24 hours**.

#### Historical Flagging

- If a user has **previous chargebacks**, future transactions are flagged automatically.

#### Score-Based Risk Evaluation

- Transactions not caught by rules are evaluated using a **Logistic Regression model**, trained to identify high-risk behavior patterns.

This hybrid approach aims to prevent fraud while keeping false positives low. The analysis phase was essential to define thresholds and patterns to be enforced during the transaction flow.

See:  
- [part-3.1-analysis.py](./3.1_Analysis/part-3.1-analysis.py)  
- [part-3.2-antifraud.py](./3.2_Antifraud/part-3.2-antifraud.py)

---

## Part 3.3 – Final Conclusions

### Overview

The proposed fraud detection strategy combines **rule-based checks** and a **score-based model** to identify and block suspicious transactions. This hybrid approach balances fraud prevention with user experience and operational efficiency.

### Main Findings

- **Rule-Based Efficiency**: Simple rules, such as blocking users with repeated attempts or exceeding daily thresholds, catch a significant portion of fraud with minimal computational cost.  
- **Model Performance**: The logistic regression model achieved good overall accuracy (~91%), but showed lower recall for fraud cases, reflecting the challenge of class imbalance.  
- **Precision vs. Recall Trade-Off**: High precision means few false positives, but recall can be improved with oversampling (e.g., SMOTE) or additional features.

### Strategy Summary

- **Latency**: The use of rules ensures near real-time response.  
- **Security**: Chargeback history and user patterns are key indicators used to prevent fraud.  
- **Architecture**: The solution can be scaled to a microservice architecture, with rules applied first and model predictions as fallback.  
- **Coding Style**: Clean code, modular structure, and consistent documentation make the project easy to maintain and expand.

### Final Thoughts

This task demonstrated how structured analysis, simple heuristics, and machine learning can work together to create an effective fraud detection pipeline. While the current approach performs well, opportunities remain to improve recall with advanced modeling, feature engineering, and continuous retraining using real feedback.

---


