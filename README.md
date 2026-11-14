# DSC563 - Visualization Work for Module 3 & 4

Author: Jeffrey Sirard (MBA student, class of 2027)

Purpose: For Data Visualization (DSC-563)

Instructor: Professor Michael McCarthy

Purpose & Structure: This README.md serves as a guide from the student to assist the professor in navigating a GitHub repository containing graduate work for a data visualization course. For clarity, this will be written as an FAQ.

Questions: Email jasirard@utica.edu.

A. Relevant Links:

- Collab URL: https://colab.research.google.com/drive/1bmKgFBiojkP8T30XcCcNvGV3XvvbYhUb?usp=sharing​
- GitHub Repository URL: https://github.com/jasirard/DSC563_M03
- GitHub Profile URL: https://github.com/jasirard
- Tableau Evidence URL: https://public.tableau.com/views/sirard_jeffrey_CDC_data_Tableau_FINAL/Comparison?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

B. Dataset Summary:

i. Basic Information:
- Title: CDC PLACES 2023 County Data
- Columns: 22 
- Rows: 229,298 
- Units: Percentage (%)

ii. Assessment/Handling of Null Values: 
- LocationName is NULL on the national "US" summary row (LocationID = "59"). 
- Data_Value_Footnote_Symbol and Data_Value_Footnote are NULL on standard county rows and populated only where estimates are suppressed or based on partial state reporting 
- All calculated fields exclude missing values using NOT ISNULL([Data_Value]) and NOT ISNULL([LocationID]). 

iii. Data Preparation, Calculations, and Filters:
- Excluded National Summary Row ([StateAbbr] != "US"): Prevents the U.S. total row from double-counting population or skewing county/state averages. 
- Isolated Prevalence Type ([DataValueTypeID] = "CrdPrv"): Separates crude prevalence from age-adjusted prevalence (AgeAdjPrv) so the two are never averaged together. 
- Deduplicated Population Denominator: Weighted rates multiply [Data_Value] * [TotalPop18plus] strictly within a single MeasureId and DataValueTypeID so TotalPop18plus is counted once per county rather than ~70+ times (i.e., dataset is long-form structure) 
- Population Classification: Categorized counties by TotalPopulation into Rural (<50k), Suburban (50k–250k), and Urban (>250k)

iv. Data Source and Reuse Information

   - Data source: Centers for Disease Control and Prevention (CDC). (2026). PLACES: Local Data for Better Health, County Data 2023 release [Dataset]. U.S. Department of Health and Human Services.
   - URL: https://data.cdc.gov/500-Cities-Places/PLACES-Local-Data-for-Better-Health-County-Data-20/h3ej-a9ec/about_data
   - Status: Last updated September 2026.
   - Reuse: Free public-domain access; Required attribution (credit CDC as the free source); No endorsement or alteration.
   - Note: Due to this dataset being model-based adult estimates, the CDC recommends against using this data to evaluate policies or programs and suggests avoiding time-series comparisons or rankings. In the case of this repository, the dataset is being used for educational purposes only.

FAQ:

1. What is the purpose of this data visualization (i.e., what is the question and intended audience)?
   - Question 1: How does adult obesity prevalence vary across U.S. states?
   - Question 2: How strongly does this track with other prevalent comorbidities?
   - Intended audience: CDC’s High Obesity Program (HOP) leadership.
   - Goal: Chart analysis and repair.

2. What are the filenames and what does each file contain?
   - See GitHub repository and descriptions.

3. How do I open, run, and check your work?
   - GitHub Repository (Public): https://github.com/jasirard/DSC563_M03
   - GitHub Profile: https://github.com/jasirard
   - All project files are located in the repository; Click to open each file.

4. What are the steps to open the student's Module 03/04 notebook in Colab, run it, and locate the outputs?
   - Access should be granted already. If not, please email me at jasirard@utica.edu for access.
   - Open this link: https://colab.research.google.com/drive/1ozcFiaCcGRx2CII_QP4NbQdvwEikjcyd
   - Click "Run All' from the commands near the top of the page.
   - Find "Files" on the left pane and open.
   - Find "Outputs" sub-folder and open.
