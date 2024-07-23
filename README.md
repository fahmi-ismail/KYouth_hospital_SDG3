# K-Youth Capstone Project
- The objective of this project is to identify potential vulnerable groups requiring assistance for access to healthcare based on synthetic data collected Massachusetts General Hospital ("MGH"), USA. As part of the project requirements, a Sustainable Development Goal ("SDG") must be used as a basis for the analysis. I have selected SDG 3: Good Health and Wellbeing for this purpose.
  - To guide the analysis and thought process, we will apply indicator 3.8 of the above SDG i.e. Achieve universal health coverage, including financial risk protection, access to quality essential health-care services and access to safe, effective, quality and affordable essential medicines and vaccines for all.
  - The end product of the analysis should assist the management of the hospital to focus their attention on the identified potential vulnerable groups in their patient population.

## References:
**Mode of data collection, cleaning, analysis, and visualization:** Microsoft Excel <br />
**Data Source:** [Hospital Patient Records](https://mavenanalytics.io/data-playground) <br />

## Instructions:
1. Choose a dataset that aligns with one of the SDGs (e.g., No Poverty, Zero Hunger, Good Health and Well-being, Quality Education, etc.).
2. Formulate a clear and concise problem statement based on the dataset you have chosen. Your problem statement should reflect a specific aspect or challenge within the chosen SDG.
   Explain why this problem is important to address and how solving it could contribute to achieving the SDG.
3. Describe the initial state of your dataset. Are there any missing values, duplicates, or outliers?
   Outline the steps you took to clean the data. This may include handling missing values, removing duplicates, correcting data types, and addressing outliers.
   Perform necessary data transformations/manipulations. Describe any new variables you created, data aggregations, or any other manipulation techniques applied to prepare the data for analysis.
4. Conduct exploratory data analysis using the visualization techniques you have learned. This should include creating at least five different types of visualizations (e.g., histograms, bar charts, scatter plots, box plots, heatmaps).
   For each visualization:
   - Describe what the visualization is showing.
   - Explain the insights gained from each visualization in the context of your problem statement.
5. Connect your visualizations and findings back to your problem statement.
   Interpret the results and discuss how they address the problem you identified.
   What are the potential implications of your findings for the chosen SDG?
   Provide recommendations or next steps based on your analysis.

### Problem Statement:
Does MGH provide adequate access to health coverage to vulnerable groups in its surrounding servicing population?

### Solution:
To analyse and design metrics and visualizations to aid in identifying vulnerable groups in MGH's patient population based  on data collected from 2011-2022.

### Result:
Development of a responsive and data-driven dashboard which highlights potential vulnerable groups for MGH's management and related stakeholders to ensure adequate access to health coverage to its surrounding population.

### Data Cleaning and Transformations:
- Masterdata headers adjusted to indicate which table it was taken using the following naming format: table_[header name]
- Reformatted start and stop date time for procedures and encounters
- Further adjusted date formulas to show "N/A" if lookup result is 0
- Patients age data adjusted to calculated age as of 31/12/2022 (end of dataset date) if no death date identified
- Multiple tables were provided. Combined into one master data but left the individual tables available for finetuned data analysis. 'procedures_clean' table not included as no appropriate key to combine with masterdata and noted multiple procedures performed on one encounter

## Analysis Workflow and Thought Process Documentation
#### 1. Gain an understanding of the demographics of the patients seeking healthcare at the hospital. Visualized basic demographics for:

   - Location: No odd patterns or outliers noted. Understandable for MGH to serve Eastern areas of Massachusettes ("MA") with higher concentration in Suffolk where MGH is located. Possibly serving neighboring state to the east as well but no data available for this in the dataset.

      ![image](https://github.com/user-attachments/assets/5ef3eda0-28ac-48b9-ab86-ae41aa5abdc9)
      ![image](https://github.com/user-attachments/assets/16cd589d-2c93-4db5-a7ae-86eed7fdba77)


   - Gender: Roughly equal number of patients. No odd patterns or outliers noted.

     ![image](https://github.com/user-attachments/assets/d33fd4be-021e-4598-b4bc-2b0859374178)

   - Race: Being a US state, expected to see Whites as the highest percentage followed by Blacks and then Others. No odd patterns or outliers noted.

     ![image](https://github.com/user-attachments/assets/c58e0cd9-945f-4c8a-89e7-bb3150803d9d)

   - Age: Noted a higher number of patients are in the 76-95 age brackets. 372 patients in total or 38% of the total patient population. Considering that elderlies are a high risk category, I then decided to explore this group further to identify possible vulnerable groups.

     ![image](https://github.com/user-attachments/assets/edf2e783-b412-4ca2-a640-6df882f74321)


#### 2. A possible restriction to healthcare access would be financial constraints. Following this thought process, I looked into the costs for procedures (encounters) throughout the years.

   - Total and average costs per year varied year-on-year. Average costs are plotted on the orange trend line and there is a gradual increase of average costs by encounter through the years at a CAGR of 1.14%. 
   ![image](https://github.com/user-attachments/assets/53c679a9-a203-4e9c-90e2-ba72db478434)

   - Noted that the year 2014 had a significant increase in total costs however this aligns with the higher number of procedures performed in that year as shown below.
   
  ![image](https://github.com/user-attachments/assets/7658a284-9733-4062-b3a8-ad3e70046c88)

   - While an increase of 1.14% is not substantial when compared to an inflation rate of 3%, what should be highlighted is the initial high cost of procedures that will continue to increase. In other words, considering that the elder population would most likely be retired without a steady stream of income, the need to pay for the costs of healthcare will place a huge burden on this group. This will be especially true if they are uninsured.
     
   - Surprisingly despite the high costs for treatment, only 68% of the total patients in MGH are insured leaving 8,807 of the patients having to pay out of pocket for each procedure required.

     ![image](https://github.com/user-attachments/assets/fce5e21c-c142-4579-a7bb-ec055938820a)
   - When looking at the top 5 average encounter costs, we can see that the highest average cost for the top encounter would leave you with a $22,573 bill. We will take this as a more aggresive approach to how well the average American would be able to pay for their own healthcare costs.

     ![image](https://github.com/user-attachments/assets/f48e6d0e-dd82-4f78-9ea9-bb0721f943d2)
   - The real median household annual income for in the US is $74,580, which when used as coverage basis for the largest average cost would result in 3.30x

     ![image](https://github.com/user-attachments/assets/96922702-bb4f-4486-916d-787cb732527e)
     ![image](https://github.com/user-attachments/assets/3f05ec80-493e-454f-bc1b-5370a8f69ae7)

     Data Source: [United States Census Bureau](https://www.census.gov/library/publications/2023/demo/p60-279.html#:~:text=Real%20median%20household%20income%20was,and%20Table%20A%2D1)
   - This would be even further exacerbated when considering a monthly salary of $6,215 resulting in coverage ratio of 0.28x

     ![image](https://github.com/user-attachments/assets/2bec6c1e-a630-4d9c-b9fa-1355a2741b40)

#### 3. Quantifying the financial impact to the vulnerable group identified

   - Previously, I wanted to get a grasp of the costs in general taking account of all the patients in MGH. Since this project is to identify the actual vulnerable group, I will narrow down the population size to the most affected individuals.
   - When looking at the insurance coverage for the elder patients (above 50 years old), it is fortunate to see that a large propoertion of them are actually insured (87%). The remaining 13% or 81 patients will need to be monitored for any difficulties in obtaining healthcare.

     ![image](https://github.com/user-attachments/assets/fff51854-7081-407d-bc43-8376cbab6015)
   - For the elderly patients, the top 5 average costs per procedure are as follows:

     ![image](https://github.com/user-attachments/assets/07315890-c475-494d-8f37-ce595b56dbb9)
   - To quantify the total impact of the costs for all 81 patients, I have compiled a brief table below on an aggresive basis to understand the real monetary value of financial assistance required. If full financial assistance is required, the total financial impact for all 81 patients would amount to $8.08 million or roughly $100k per patient.

     ![image](https://github.com/user-attachments/assets/bbe83bca-016e-498b-968a-afa804e91363)

**Recommended Action Points**: Possible action points for MGH and healthcare in the US in general:
  1. Co-pay arrangements for identified vulnerable groups
  2. MGH and insurance companies to work together and assume a fiduciary duty to minimise the costs of healthcare
  3. MGH and other healthcare providers to lobby for national policies to subsidise healthcare costs for vulnerable groups.
