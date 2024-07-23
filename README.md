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

    ![image](https://github.com/user-attachments/assets/e1c5fd12-c1b0-44cc-a85c-cfcdc2f92887)

#### 2. A possible restriction to healthcare access would be financial constraints. Following this thought process, I looked into the costs for procedures (encounters) throughout the years.

   - Total and average costs per year varied year-on-year. Average costs are plotted on the orange trend line and there is a gradual increase of average costs by encounter through the years at a CAGR of 1.14%. 
   ![image](https://github.com/user-attachments/assets/53c679a9-a203-4e9c-90e2-ba72db478434)

   - Noted that the year 2014 had a significant increase in total costs however this aligns with the higher number of procedures performed in that year as shown below.
   
  ![image](https://github.com/user-attachments/assets/7658a284-9733-4062-b3a8-ad3e70046c88)

   - While an increase of 1.14% is not substantial when compared to an inflation rate of 3%, what should be highlighted is the initial high cost of procedures that will continue to increase. In other words, considering that the elder population would most likely be retired without a steady stream of income, the need to pay for the costs of healthcare will place a huge burden on this group. This will be especially true if they are uninsured.

   - The median annual income in 2021 in the US is $45,760, or $3,813 per month.


## Overview of the Dashboard:
This dashboard consists of 3 parameters and 4 main analysis sections:
### Parameters:
1. Date: The analysis displayed on the dashboard corresponds to the chosen date.
2. Date Type: The dashboard analysis is determined by the selected date type, including daily, weekly, monthly, and yearly.
3. No. of Periods: This parameter controls the display of past periods for trend chart analysis.

### Analysis Sections:
1. Key Performance Indicators
2. Charts
3. Map
4. Trend Charts

![image](https://github.com/rnlow22/shopping_mall_sales_dashboard/assets/30455582/34ab63ef-961f-4712-b8eb-12c4f0d1e8d3)

### Dashboard Functionality:
1. Analysis can be interactively filtered by clicking on any item within the chart.
![Screenshot 2024-05-29 at 10 05 10 PM](https://github.com/rnlow22/shopping_mall_sales_dashboard/assets/30455582/e5aab19f-7fab-41f5-b337-a8ed07bbc908)

2. Business users can tailor the number of past periods for trend chart analysis according to their needs.
![Screenshot 2024-05-29 at 10 06 36 PM](https://github.com/rnlow22/shopping_mall_sales_dashboard/assets/30455582/908311f1-65f5-4aac-b61e-2a21a4b5c355)

3. Various trend charts analyzing different Key Performance Indicators can be accessed by selecting from the dropdown menu.
![Screenshot 2024-05-29 at 10 07 32 PM](https://github.com/rnlow22/shopping_mall_sales_dashboard/assets/30455582/2ea29f34-1228-4149-814e-b27bd50926d7)

4. Month-on-Month Growth for Key Performance Indicators is displayed in a single view on the dashboard when selecting Date Type as "Monthly". This functionality extends to Day-on-Day, Week-on-Week, and Year-on-Year Growth as well.
![Screenshot 2024-05-29 at 10 08 41 PM](https://github.com/rnlow22/shopping_mall_sales_dashboard/assets/30455582/1ce4e04a-5afa-4461-b286-4cf66589e12d)

## BI Monthly Reporting for January 2023:
![image](https://github.com/rnlow22/shopping_mall_sales_dashboard/assets/30455582/63def021-41fb-4b26-a06b-27da0e0e2016)

1. January 2023 witnessed consistent **sales volumes** compared to historical data across all Key Performance Indicators, resulting in a total of **12k sales**, contributing to **TL 2.6 million**.
2. The **average sales amount per customer** in January 2023 was TL 667, with a total **customer count** of **3.9k**.
3. **Female** customers dominate the customer base, making up **60%**. The age distribution is relatively balanced, with adults **aged 25 to 64** comprising the **majority**, while customers **over 65** represent **only 9%** of the total.
4. The **top three categories by sales count** are **Clothing (34%)**, **Cosmetics (17%)**, and **Food & Beverage (15%)**. However, the **top three categories by sales amount** are **Clothing (45%)**, **Shoes (26%)**, and **Technology (23%)**.
5. **Shoes** and **Technology** achieve higher sales amounts despite not being in the top three for sales count, due to their **high average sales amounts per item (TL 1,050 for Technology and TL 600 for Shoes)**.
6. The **top three shopping malls** generating the **most sales revenue** in Isbantul are **Kanyon (TL 538k)**, **Mall of Isbantul (TL 528k)** and **Metrocity (TL 424k)**.

## Key Dashboard Business Insights for January 2023:
1. The number of customers **aged 55 to 64** purchasing **Cosmetic products** has gradually increased from **99 to 133 (34%)** over the past 7 months, resulting in a **50% increase in both sales count and sales amount (TL)**.
<p float="center">
  <img src="https://github.com/rnlow22/shopping_mall_sales_dashboard/assets/30455582/b0563fe5-8b3f-410a-a815-c534a5e5a3c8" width="45%" />
  <img src="https://github.com/rnlow22/shopping_mall_sales_dashboard/assets/30455582/3ade4b63-fcc0-4dfd-9ad0-2d92f0bcafa9" width="45%" /> 
  <img src="https://github.com/rnlow22/shopping_mall_sales_dashboard/assets/30455582/6973b600-f550-4e63-a108-2d5af1279abf" width="45%" />
</p>

**Recommended Business Decision**: The marketing team should conduct targeted personalized campaigns for customers aged 55 to 64, specifically focusing on Cosmetic products. Before launching the campaigns, A/B testing should be conducted to evaluate their effectiveness in boosting Sales Revenue (TL).

2. There has been a **sudden drop** in the number of **young adult customers aged 25 to 34** purchasing **Technology products** in January 2023 compared to the past 7 months, **decreasing from 39 to 26 (33%)**. Consequently, there was a corresponding **24% decrease** in **both sales count and sales amount (TL)** in January 2023.
<p float="center">
  <img src="https://github.com/rnlow22/shopping_mall_sales_dashboard/assets/30455582/3dae8337-fd3c-4db7-b8ff-a9236ffe7f6a" width="45%" />
  <img src="https://github.com/rnlow22/shopping_mall_sales_dashboard/assets/30455582/493632ef-c9d7-4979-b0aa-daf8f0a115bc" width="45%" /> 
  <img src="https://github.com/rnlow22/shopping_mall_sales_dashboard/assets/30455582/863a8c32-cdb7-4f6d-bb96-a5697158a2ba" width="45%" />
</p>

**Recommended Business Decision**: The product team should conduct an investigation into the root cause of the sudden drop in Technology product sales among young adult customers aged 25 to 34. Possible causes to investigate include:
  1. Insufficient stocks in the shopping mall
  2. Launch in virtual technology stores
  3. Other potential factors
