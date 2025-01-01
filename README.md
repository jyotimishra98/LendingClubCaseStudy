# Lending Club Case Study

Lending Club, a consumer finance marketplace, specializes in providing various loan options to urban customers. The company faces a significant challenge in managing its loan approval process, as it must carefully evaluate applications to minimize financial losses. These losses primarily arise from loans granted to "risky" borrowers who fail to repay or default on their loans.

This case study aims to identify key factors contributing to loan defaults, enabling Lending Club to improve its risk management and lending strategies.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Objectives](#objectives)
3. [Conclusions](#conclusions)
4. [Technologies Used](#technologies-used)
5. [Acknowledgements](#acknowledgements)
6. [Collaborators](#collaborators)

---

## Introduction

Financial losses, known as **credit losses**, occur when borrowers fail to fulfill their repayment obligations. Borrowers classified as "charged-off" pose the greatest risk to Lending Club. This study focuses on addressing two primary challenges:  
1. Identifying applicants likely to repay loans to maximize profits from interest payments.  
2. Avoiding approval of loans for applicants at high risk of default, which can lead to significant financial losses.

This study uses **Exploratory Data Analysis (EDA)** to uncover the key drivers behind loan defaults, helping the company refine its risk assessment and underwriting process.

---

## Objectives

The primary objective is to assist Lending Club in minimizing credit losses by:  
1. Identifying applicants at higher risk of default.  
2. Understanding the variables most indicative of a borrower’s likelihood to default.

This analysis will empower Lending Club to implement more robust risk assessment strategies and make data-driven decisions in loan approvals.

---

## Conclusions

1. **Risk Assessment by Loan Grades**  
   - Applicants from Grades B, C, and D have the highest default rates. Stricter underwriting criteria should be applied to these grades.

2. **Critical Subgrades**  
   - Subgrades B3, B4, and B5 are particularly high-risk. Lending Club should consider risk mitigation measures, such as offering lower loan amounts or higher interest rates.

3. **Loan Term Length**  
   - Borrowers opting for 60-month loans are more prone to default. The company should evaluate risks associated with longer-term loans and adjust terms or rates accordingly.

4. **Borrower Experience**  
   - Applicants with 10+ years of work experience show higher default rates, indicating that experience alone is not a reliable creditworthiness indicator.

5. **Market Growth**  
   - A steady increase in loan applications from 2007 to 2011 highlights market growth. Robust risk management practices are essential to sustain this growth.

6. **Seasonal Trends**  
   - Loan applications peak in December and Q4 due to the holiday season. Efficient loan processing during this period is crucial.

7. **Debt Consolidation Risk**  
   - Debt consolidation loans show the highest volume and high default rates. The company should assess these applicants more thoroughly, adjust interest rates, or offer financial counseling.

8. **Housing Status**  
   - Borrowers living in rented or mortgaged homes show a higher likelihood of default. Housing stability should be factored into the risk assessment process.

9. **Verification Process**  
   - Verified applicants have higher default rates. The verification process should be reviewed and enhanced to improve creditworthiness assessment.

10. **Geographic Risk**  
    - Applicants from California (CA), Florida (FL), and New York (NY) are at higher risk of default. Regional risk trends should inform lending strategies and interest rates.

11. **Loan Amounts**  
    - Loans of $15,000 or more have higher default rates. More thorough assessments and caps on high-risk loan amounts may help mitigate risks.

12. **DTI and Interest Rates**  
    - High Debt-to-Income (DTI) ratios and interest rates in the 13%-17% range are linked to higher defaults. Interest rate policies should align more closely with DTI ratios.

13. **Annual Income**  
    - Borrowers with annual incomes below $40,000 are at higher risk of default. Setting income-based loan limits and offering financial education resources can reduce defaults.

---

## Technologies Used

The following technologies and tools were used in this project:

- [Python](https://www.python.org/) - version 3.11.4
- [Matplotlib](https://matplotlib.org/) - version 3.7.1
- [Numpy](https://numpy.org/) - version 1.24.3
- [Pandas](https://pandas.pydata.org/) - version 1.5.3
- [Seaborn](https://seaborn.pydata.org/) - version 0.12.2

---

## Acknowledgements

This project was inspired by:
- Live sessions on Exploratory Data Analysis (EDA) hosted by **UpGrad**.
- UpGrad tutorials on EDA concepts available on the learning platform.

---

## Collaborators

Created by **[Jyoti Kumari](https://github.com/jyotimishra98/LendingClubCaseStudy)**  
Feel free to contribute to this project or provide feedback!
