# Lending Club Project
# Submitted by Dr. Parul Shah & Dhanshree Vyas

## INTRODUCTION 
In this case study, we are trying to solve a real business problems using EDA. This case study is to learn how to apply the techniques we have learnt in EDA. This will help us in developing a basic understanding of risk analytics in banking and financial services and understand how data is used to minimise the risk of losing money while lending to customers.

## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information

- BACKGROUND: This consumer finance company, 'Lending Club', specialises in lending various types of loans to urban customers. When the company receives a loan application, the company has to make a decision for loan approval based on the applicant’s profile. Two types of risks are associated with the bank’s decision:
1) If the applicant is likely to repay the loan, then not approving the loan results in a loss of business to the company
2) If the applicant is not likely to repay the loan, i.e. he/she is likely to default, then approving the loan may lead to a financial loss for the company

In this case study, we will use EDA to understand how consumer attributes and loan attributes influence the tendency of default.

- PROBLEM STATEMENT: This company is the largest online loan marketplace, facilitating personal loans, business loans, and financing of medical procedures. Borrowers can easily access lower interest rate loans through a fast online interface. 

    Like most other lending companies, lending loans to ‘risky’ applicants is the largest source of financial loss (called credit loss). Credit loss is the amount of money lost by the lender when the borrower refuses to pay or runs away with the money owed. In other words, borrowers who default cause the largest amount of loss to the lenders. In this case, the customers labelled as 'charged-off' are the 'defaulters'. 

    If one is able to identify these risky loan applicants, then such loans can be reduced thereby cutting down the amount of credit loss. Identification of such applicants using EDA is the aim of this case study.

    So our goal is to identify and understand the driving factors (or driver variables) behind loan default, i.e. the variables which are strong indicators of default.  The company can utilise this knowledge for its portfolio and risk assessment. 
 
- DATA USED:
The data given used (loan.csv) contains information about past loan applicants and whether they ‘defaulted’ or not. The aim is to identify patterns which indicate if a person is likely to default, which may be used for taking actions such as denying the loan, reducing the amount of loan, lending (to risky applicants) at a higher interest rate, etc.

    When a person applies for a loan, there are two types of decisions that could be taken by the company:
    1) Loan accepted: If the company approves the loan, there are 3 possible scenarios described below:
        a) Fully paid: Applicant has fully paid the loan (the principal and the interest rate)
        b) Current: Applicant is in the process of paying the instalments, i.e. the tenure of the loan is not yet completed. These candidates are not labelled as 'defaulted'.
        c) Charged-off: Applicant has not paid the instalments in due time for a long period of time, i.e. he/she has defaulted on the loan 

    2) Loan rejected: The company had rejected the loan (because the candidate does not meet their requirements etc.). Since the loan was rejected, there is no transactional history of those applicants with the company and so this data is not available with the company (and thus in this dataset)



## Conclusions from Univariate
- Loan Status: it is good to know that number of fully paid loans is significantly higher than num of defaulting loans.
- Term: It is clear that most loans have 36 months term, so we must dig deeper and learn more about Loan status of those who have 36 months terms.
- Loan Grade: Almost 1/3rd of total loans are of grade B and 1/4th are of Grade A, 1/5t is of Grade C. So together, Grade A, B, C and D is covering majority loans. We need to analyse them further to ensure these afre all 'low-risk' loans.
- Loan Sub-Grade: This is in sync with Grade. We need to dig deeper, especially for sub-grade A4, A5, B3, B4, B5 and ensure these are 'low-risk' loans.
- State: Some of the states significantly larger number of loans compared to others and hence need to study them further. e.g CA, NY, FL, TX.
- Zip Code: Some of the zip codes also show significantly larger number of loans compared to others, those zip codes need furter analysis.
- Purpose: A huge number of loan is taken for debt consolidation and credit card payments. Both these catogory fall into not-secured loans and hence it is very important to know that these loans are 'low-risk'. This needs further analysis.
"othher' also shows good number of loans, as there is no more information about thses loans, may be we can check their grades and sub-grades to understand them better.
- Home ownership status: This too indicates that most loans are not-secured as a huge majority given to borrowers who either do not own a ome or have already mortgaged it. NOT a good scenario and definitely need further investigations.

## Conclusions from Bi-variate
- Term: Ratio of fully paid to defaulters for 36 months term is much higher compared to 60 months. Which means, 36 months loans are far more less risky than 60 months loans
- Grade:
    Conclusion 1: First bar chart indicates that Grade A & B makes almost 50% of total fully paid loans. This is evident in the box plot too. If we examine second bar chart (of defaulters), Grade A makes less than half of Grade B and C. This shows that Grade A is one of the most safest and 'low-risk' loan.
    Conclusion 2: From bar charts we can see that ratio of defaulters to fully paid in grade B is approximately 0.14. Box plots sows that 25% of all defaulters are under Grade B.  This makes Grade B also relatively a low-risk loan
    Conclusion 3: 75% of fully paid loans are under Grade A, B & C, so Grade C  is a  moderate-risk loan
    Conclusion 3: Above Grade C is what needs more attention. 
    Conclusion 4: Box plot shows, maximum Grade of Fully paid is Grade F (not considering the outliers), which makes Grade G a very high-risk loan,  almost sure shot defaulters. 
This lead us in analysing further on what are the purposes that fall under Grade G and get more pointers on which catagories should be avoided. 
    Conclusion 5: debt_consolidation loans are high-risk loans and more likely to default. 
    Similarly, small_business and 'other' too are relatively high-risk and must be looked into properly before sanctioning the loan 
- Sub-Grades: 
    Conclusion 1: Once again it shows that Sub-Grades of A are less likely to default and hence they are some of the most low-risk grades.
    Conclusion 2: 75% of fully paid loans are below sub_grade C3 (Rank 13), so these grades are relatively low-risk loans
    Conclusion 3: 50% of defaulters are between sub_grade B4 to D4 (rank 8 to 18). A little more scrutiny needed for these grades before sanctioning the loan.
    Conclusion 4: Grade F3 (rank 27) and above are higly likely to default. Sub-Grades of G once again proves to be the riskiest sub-grades.
- Purpose of loan:
    Conclusion 1: Once again it shows that loans taken for debt_consolidation is highly likely to default and hence they are high-risk. Process to sanction them should be tightened.
    Conclusion 2: Same sould be done for 'Other', 'Credit_card' and 'small_business' catagories. They too look like high-risk loans
- Home Ownership:
    To our surprise, ratio of Fully paid / Defaulted for Mortgage is higher compared to other catagories pointing to low-risk. This might be because if the house is already on mortgage, defaulting means losing it completely and so the borrowers will try their best to repay.
- Interest rates: 
    Conclusion 1: 50% of fully paid loans av int_rate under 11 (approxximately) and 50% of defaulters have int_rate between 11 to 16. So we can safely conclude that int_rate of < = 11 can result into low-risk loans
    Conclusion 2: Maximum int_rate in fully-paid is 22 (not considering outliers). Which means loans with int_rate > 22 are high-risk and sure shot defaulters. 
- Monthly Installment Size:
    Conclusion 1: The 50% to 75% distribution of charged-off loan is sligtly larger than fully-paid loans. It shows that if monthly installement is larger, then chances of default is a little higher compared to smaller installments.
    Conclusion 2: Max installment of Fully paid is approximately 800 (not considering outliers). So installments > 800 are all high-risk loans and more likely to default.
- Employment length: It is difficult to draw any major insights here. However, median of defaulter is higher than fully paid, which kind of points that people who are longer in the job, are more likely to default. But this is a little contradicting with common logic and hence need further investigations.
- DTI: No major insights on effect of DTI on risk, which is surprising. However, 75% of fully paid loans hv DTI< = 18, which means loans to borrowers with DTI > 18 are risky. 
- Status of Verification:
    Conclusion 1:  The first plot indicates clearly that number of 'Not Verified' borrowers who have fully paid is siggnificantly higher than 'Source Verified' or 'Verified' catagory.
    Conclusion 2: Second graph shows that number of 'Non-verified' defaulters is very close to 'Verified' defaulters with slight higher number
    Conclusion 3: This is a very serious concern. It looks like the verification process itself is faulty and needs to be evaluated and revised.

## Summary
Exploratory Data Analysis of Lending Club data gave some very important insights which can help the company in reducing the risk while giving loans in future.
- Attributes of a Low-Risk Loan:
    - Grade A or B & Sub-grade - A1 to C3 
    - 36 months term, interest rate which is less than 11, monthly installments size which is less tan 400$
- Attributes of a high-risk Loan: 
    - Grade G, Sub-grades F3 and above
    - Purpose of taking loan as debt consolidation / credit card / small business / other
    - interest rate wich is more than 22, monthly installments which is greter than 800$ 
    
To our surprise, ratio of Fully paid / Defaulted for Mortgage is higher compared to other catagories pointing to low-risk. This might be because if the house is already on mortgage, defaulting means losing it completely and so the borrowers will try their best to repay.

The most important finding was that non-verified loans are more likelyy to fully pay tan the verified ones, which cannot be true for obvious reasons. The whole point of verifying borrower's information is to reduce risk. This indicates that the verification process that is followed is flawed and needs some major revision.


## Technologies Used
- Coding is done in python. We used jupyter notebook for that.
    Libraries used in python: pandas, numpy, matplotlib.pyplot, LabelEncoder, seaborn
- For collaboration, we used Github platform


## Acknowledgements
- This case study was done as part of our UpGrad course project for EDA


## Contact
Created by @DrParulShah and @DhanshreeVyas - feel free to contact me!
