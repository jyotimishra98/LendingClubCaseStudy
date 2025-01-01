# Lending Club Case Study

#####################
## Problem Statement
#####################

######
* The company needs to improve its loan approval process to identify applicants likely to default.  This involves balancing two competing risks:
    * Rejecting a loan application from a creditworthy individual, leading to lost business.
    * Approving a loan application from an individual likely to default, leading to financial loss.
######
* **Dataset and Objective:** The dataset contains information on past loan applicants, including their loan characteristics and whether they defaulted ("charged-off").  The objective is to use EDA to identify patterns and "driver variables" that strongly indicate default risk.
######
* **Business Implications:** Identifying risky applicants allows the company to take mitigating actions such as:
    * Denying the loan application.
    * Reducing the approved loan amount.
    * Charging a higher interest rate to compensate for increased risk.
######
* **Data Scope:**  The dataset *only* includes applicants who were *approved* for a loan.  It does *not* include rejected applications because there is no subsequent loan performance data for these individuals.  The included loan statuses are:
    * **Fully Paid:** Loan repaid successfully.
    * **Current:** Loan repayment in progress.
    * **Charged-off:** Loan defaulted.
######
* **Company Background:**  The company is the largest online loan marketplace, offering various loan types (personal, business, medical).  Its online platform provides borrowers with access to lower interest rates.
######
* **Key Goal:** The primary goal is to reduce credit loss – the financial loss incurred when borrowers default – by identifying risky applicants *before* loan approval.  This involves understanding the factors that contribute to default and using this knowledge to improve the company's risk assessment strategies. This case study uses EDA to address the challenge of loan default prediction for a consumer finance company.  
######


#################
# Table of Contents
#################

######

* **Problem Statement** <br><br>

* **Task 1: Data Understanding and Dimensionality Reduction** <br><br>

    * 1.1 Import Libraries
    
    * 1.2 Load loan data from CSV file 
    
    * 1.3 **Dimensionality Reduction (Dropping Uninformative Features)**:
        
        * 1.3.1 Removing Features with Excessive Missing Values 
        * 1.3.2 Removing Redundant Features (High Cardinality)
        * 1.3.3 Feature Exclusion Based on Domain Expertise:   
        
            * 1.3.3.1 Removing Unique Identifiers
            * 1.3.3.2 Removing Post-Approval Features
            * 1.3.3.3 Removing Other Irrelevant Features <br><br>
   
    * 1.4 Dropping Irrelevant Records <br><br><br>
        


* **Task 2: Data Cleaning and Manipulation** <br><br>

    * 2.1 **Convert Columns Formats**:
    
        * 2.1.1 Remove percentage (%) sign from the data (`int_rate` and `revol_util`) and convert them to float
        * 2.1.2 Convert `issue_d` column in `yyyy-mm-dd` format
        * 2.1.3 Remove 'months' from all the values from the column `term`
        * 2.1.4 Convert `emp_length` into int (First format it correctly then convert it) <br><br>

    * 2.2 **Missing values imputation**

    * 2.3 **Outliers Detection and Mitigation**
    
    * 2.4 **Derived Metrics / Variables**: 
    
        * 2.4.1 Creating Date Based Features 
        * 2.4.2 Creating Binned/Bucketed Features <br><br><br>



* **Task 3: Data Analysis** <br><br>
    
    * 3.1 **Univariate Analysis** ('Charged Off' as well as 'Fully Paid' data): 
        * 3.1.1 Univariate Analysis of Numerical Variables and their Respective bins/buckets ('Charged Off' as well as 'Fully Paid' data)
        * 3.1.2 Univariate Analysis of Categorical Variables ('Charged Off' as well as 'Fully Paid' data) 
        * Summary of Univariate Analysis ('Charged Off' as well as 'Fully Paid' data) Plot Interpretations <br><br>
        
    * 3.2 **Univariate Analysis** ('Charged Off' data only):
        * 3.2.1 Univariate Analysis ('Charged Off' data only) of Numerical Variables and respective bins/buckets 
        * 3.2.2 Univariate Analysis ('Charged off' data only) of Categorical Variables
        * Summary of **Univariate Analysis** ('Charged Off' data only) Plot Interpretations <br><br>
    
    * 3.3 **Segmented Univariate Analysis** ('Charged Off' as well as 'Fully Paid' Data): 
        * 3.3.1 Loan Status (`loan_status`) Segmentation
        * 3.3.2 Annual Income Segmentation 
        * 3.3.3 DTI (Debt-to-Income Ratio) Segmentation 
        * 3.3.4 Interest Rate Segmentation
        * 3.3.5 Loan Amount Segmentation
        * 3.3.6 Employment Length Segmentation
        * 3.3.7 Home Ownership Segmentation 
        * Summary of Segmented Univariate Analysis Plot Interpretations <br><br>
        
    * 3.4 **Bivariate Analysis**:
        * 3.4.1 Core Financial Relationships (with Loan Status Integration)
        * 3.4.2 Loan Characteristics and Grade (with Loan Status Integration)
        * 3.4.3 Loan Purpose and Risk
        * 3.4.4 Time-Based Analysis
        * 3.4.5 Employment Length and Loan Characteristics
        * 3.4.6 Correlation Analysis:
        * 3.4.7 Loan Status vs. Numerical Variables bins/buckets 
        * 3.4.8 Loan Status vs. Categorical Variables (Bivariate Analysis) 
        * Summary of Bivariate Analysis Plot Interpretations <br><br><br>
        
        
* **Driver Variables** <br><br>
* **Summary of Plot Interpretations** <br><br>



#####
############################################################################
## Conclusion / Summary: Loan Default Patterns of Lending Club Case Study
############################################################################

######

 1.  **Loan Amount and Interest Rate:** Smaller loans (4k-12k) with mid-range interest rates (9-17%) are common among defaults, suggesting borrowers may be overextending their finances.  Larger loans, particularly those with higher interest rates, also present elevated risk due to the increased repayment burden. This highlights the combined effect of loan amount and interest rate in assessing default risk.

 2.  **Financial Health (Income and DTI):** Defaults are concentrated among borrowers with annual incomes of 25k-75k, indicating that income alone is not a reliable predictor of default.  DTI plays a crucial role, with moderate to moderately high DTIs (10-20) being prevalent among defaulters.  High DTI, even with a reasonable income, is a significant risk factor, suggesting potential difficulty managing debt and financial overextension.

 3.  **Credit History (Open Lines, Utilization, Total Accounts):** Defaulters typically have a moderate number of open credit lines (5-11), indicating established credit but possible challenges in managing multiple accounts.  High revolving credit utilization (68-85%) is a risk factor, although defaults also occur at lower utilization levels, suggesting other contributing factors.  A moderate to high total number of accounts (8-24) is also common, potentially reflecting a history of seeking credit.

 4.  **Loan Characteristics (Grade, Term, Purpose):** Several loan characteristics are associated with increased default risk.  These include lower loan grades (B, C, F, G), sub-grades B5 and C1, 36-month loan terms, and debt consolidation as the loan purpose.  Longer terms (60 months), while less frequent among defaults, carry higher risk due to potentially larger loan amounts and accumulated interest.  Small business loans are particularly risky due to their larger amounts, higher rates, and inherent business uncertainties.

 5.  **Employment Length:** Both very short (<1 year) and very long (10+ years) employment histories show elevated default rates.  Short employment may indicate instability, while long employment might lead to overconfidence in borrowing capacity.  This counterintuitive finding warrants further investigation.

 6.  **Time of Loan (Year, Month):** Most defaults occurred in 2011, possibly due to economic conditions or lending practices specific to that period.  Increased defaults in November and December suggest seasonal influences, such as financial pressures related to holiday spending.

 7.  **Home Ownership and Loan Purpose:** Renters and individuals with non-traditional homeownership ("OTHER") experience higher default rates, potentially due to lower financial stability.  Debt consolidation is a frequent loan purpose among defaulters, often indicating a last-resort attempt to manage existing debt.  Small business loans remain a high-risk category.

 8.  **Interaction of Loan Grade and Loan Amount:** Lower loan grades are associated with both higher default rates and larger loan amounts.  This combination significantly increases the risk of default, as borrowers with weaker credit profiles take on more substantial debt.

 9.  **Risk Factors for Small Business Loans:** Small business loans are inherently risky due to factors such as larger loan amounts, higher interest rates, and the general uncertainties of business ventures.  These factors contribute to the elevated default rates observed in this category.

10. **DTI and Loan Grade Interaction:** While DTI is a risk factor across all loan grades, its influence is amplified for lower grades.  Borrowers with lower loan grades and higher DTIs are particularly vulnerable to default.  Lenders should carefully consider the combined effect of these two factors.


##


###############################################################################
## Driver Variables for identifying potential loan defaulters:
###############################################################################

######

1. **Grade (`grade` (and `sub_grade`)):** Loan grade is a strong predictor of default, with lower grades (B-G) showing significantly higher default rates. This is because lenders assign grades based on their assessment of borrower risk, considering factors like credit history and existing debt levels.  Sub-grades offer even finer granularity for risk differentiation.

2. **Interest Rate (`int_rate`):** High interest rates are a key indicator of risk, and the analysis confirms a strong positive relationship between interest rate and default rate. Higher rates often reflect the lender's perception of increased borrower risk and contribute to a heavier repayment burden, making default more likely.

3. **Term (`term`):** Longer loan terms (60 months) have a substantially higher default *rate* compared to shorter terms (36 months).  While 36-month loans may have more defaults in absolute numbers due to higher volume, the proportional risk is greater with longer terms, possibly due to increased exposure to financial hardship over time.

4. **Debt-to-Income Ratio (`dti`):** A high debt-to-income ratio (DTI), particularly in the 15-25 range, is a strong predictor of default.  This indicates that a large portion of the borrower's income is already allocated to debt repayment, leaving less room to handle unexpected expenses or financial shocks, thus increasing their vulnerability to default.

5. **Loan Purpose (`purpose`):** Certain loan purposes are associated with higher default risk. Small business loans, for instance, have the highest default rate due to the inherent risks of business ventures, coupled with often larger loan amounts and higher interest rates.  Debt consolidation loans also signal elevated risk, as they often indicate borrowers are already struggling to manage existing debt.

6. **Loan Amount (`loan_amnt`):** Larger loan amounts, especially those above 16k, correlate with higher default rates.  This is likely because larger loans result in higher monthly payments and a greater overall repayment burden, increasing the financial strain on borrowers and making them more susceptible to default.

7. **Home Ownership (`home_ownership`):** Renters and those with "OTHER" homeownership status exhibit higher default rates compared to homeowners.  This suggests that homeownership may serve as a proxy for greater financial stability and access to alternative financial resources in times of hardship.

8. **Annual Income (`annual_inc`):** While not a strong standalone predictor, annual income plays a role in default risk. Lower annual incomes (<25k) are associated with higher default rates, indicating that borrowers with limited financial capacity may be more vulnerable to unforeseen circumstances that lead to default.  It's important to consider income in conjunction with other factors like DTI and loan amount.


    These 8 variables, when considered together and in their interactions, provide a comprehensive view of a borrower's default risk profile.  Other factors, like credit history details and specific sub-grades, can further refine this assessment.


## Technologies Used
pandas==2.0.3
numpy==1.24.4
matplotlib==3.7.3
seaborn==0.12.2

######
################
# Collaborators:
################

*  Saurabh Tayde (saurabhtayde2810@gmail.com)
*  Jyoti Kumari (jyotimishra05021987@gmail.com)
