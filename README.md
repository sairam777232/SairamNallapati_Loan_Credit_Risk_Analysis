# Loan Default & Credit Risk Analysis

## Project Overview
This project analyzes customer loan data to identify patterns associated with loan default and credit risk using Python and Power BI.

## Project Objective
The objective is to transform loan and customer financial data into meaningful credit-risk insights that can support risk monitoring and business decision-making.

## Dataset
The dataset contains **255,347 loan records** and **18 original columns**.

### Main Columns
`LoanID`, `Age`, `Income`, `LoanAmount`, `CreditScore`, `MonthsEmployed`, `NumCreditLines`, `InterestRate`, `LoanTerm`, `DTIRatio`, `Education`, `EmploymentType`, `MaritalStatus`, `HasMortgage`, `HasDependents`, `LoanPurpose`, `HasCoSigner`, `Default`.

Four analytical fields were added:
- `CreditScore_Group`
- `DTI_Group`
- `InterestRate_Group`
- `LoanAmount_Group`

## Tools & Technologies
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook / VS Code
- Microsoft Power BI Desktop
- Power Query
- DAX
- GitHub

## Data Cleaning
1. Loaded the dataset using Pandas.
2. Checked shape, columns and data types.
3. Generated descriptive statistics.
4. Checked missing values.
5. Checked duplicate records.
6. Verified the cleaned dataset.
7. Created analytical risk groups.

The final cleaned dataset contains **255,347 rows and 22 columns**.

## Analysis Performed
- Total loans, defaulted loans and non-defaulted loans
- Overall default rate
- Average income
- Average loan amount
- Average credit score
- Average interest rate
- Average DTI ratio
- Default rate by credit-score group
- Default rate by DTI group
- Default rate by interest-rate group
- Default rate by loan-amount group
- Default rate by education
- Default rate by employment type
- Default rate by marital status
- Default rate by co-signer status
- Default rate by loan purpose
- Credit Score vs Loan Amount
- Loan-level details

## Key Results

| Metric | Result |
|---|---:|
| Total Loans | 255,347 |
| Defaulted Loans | 29,653 |
| Non-Defaulted Loans | 225,694 |
| Default Rate | 11.61% |
| Average Income | 82,499.30 |
| Average Loan Amount | 127,578.87 |
| Average Credit Score | 574.26 |
| Average Interest Rate | 13.49% |
| Average DTI Ratio | 0.50 |

## Python Visualizations
- Loan Default Distribution — Pie Chart
- Loan Count / Default Rate by Category — Bar Charts
- Credit Score Distribution — Histogram
- Loan Amount Distribution — Histogram
- Annual Income Distribution — Histogram
- Credit Score vs Loan Amount — Scatter Plot
- Income vs Loan Amount — Scatter Plot
- Loan Amount by Default Status — Box Plot
- Credit Score by Default Status — Box Plot
- Debt-to-Income Ratio by Default Status — Box Plot
- Default Rate by Income Group — Bar Chart
- Correlation Heatmap

## Power BI Dashboard
### Title
**Loan Default & Credit Risk Analytics Dashboard**

### Page 1 — Executive Dashboard
- Total Loans
- Defaulted Loans
- Non-Defaulted Loans
- Default Rate %
- Average Loan Amount
- Average Credit Score
- Average Income
- Average Interest Rate
- Default Distribution
- Default Rate by Credit Score Group
- Default Rate by Interest Rate
- Loan Purpose, Employment Type, Credit Score Group and DTI Group slicers

### Page 2 — Risk Analysis
- Default Rate by DTI Group
- Default Rate by Loan Amount Group
- Default Rate by Loan Purpose
- Default Rate by Employment Type
- Default Rate by Marital Status
- Default Rate by Co-Signer
- Credit Score vs Loan Amount scatter plot
- Loan Details table

## DAX Measures
```DAX
Total Loans =
COUNTROWS(Loan_Credit_Risk_Cleaned)

Defaulted Loans =
CALCULATE(
    COUNTROWS(Loan_Credit_Risk_Cleaned),
    Loan_Credit_Risk_Cleaned[Default] = 1
)

Non-Defaulted Loans =
CALCULATE(
    COUNTROWS(Loan_Credit_Risk_Cleaned),
    Loan_Credit_Risk_Cleaned[Default] = 0
)

Default Rate % =
DIVIDE([Defaulted Loans], [Total Loans], 0)

Average Loan Amount =
AVERAGE(Loan_Credit_Risk_Cleaned[LoanAmount])

Average Credit Score =
AVERAGE(Loan_Credit_Risk_Cleaned[CreditScore])

Average Income =
AVERAGE(Loan_Credit_Risk_Cleaned[Income])

Average Interest Rate =
AVERAGE(Loan_Credit_Risk_Cleaned[InterestRate]) / 100
```

## Key Business Insights
- The overall default rate is **11.61%**.
- Higher interest-rate groups show higher observed default rates.
- Higher loan-amount groups show higher observed default rates.
- Lower credit-score groups show higher observed default rates than higher credit-score groups.
- Higher DTI groups show a gradual increase in observed default rate.
- Default rates vary across employment and education segments.
- Customers without a co-signer show a higher observed default rate than customers with a co-signer.
- These patterns can help identify segments requiring closer credit-risk monitoring.

## Project Structure
```text
SairamNallapati_Loan_Credit_Risk_Analysis
│
├── Dataset
│   └── Loan_default.csv
│
├── Python
│   └── Loan_Credit_Risk_Analysis.ipynb
│
├── Power BI
│   └── SairamNallapati_Loan_Credit_Risk_Analysis.pbix
│
├── Report
│   └── Loan_Credit_Risk_Project_Report.pdf
│
└── README.md
```

## Conclusion
The project demonstrates how Python and Power BI can be used together for credit-risk analysis. The analysis identifies differences in default rates across financial and customer segments, while the Power BI dashboard provides an interactive way to explore these patterns.

## Author
**SaiRam Nallapati**

**Project:** Loan Default & Credit Risk Analysis
