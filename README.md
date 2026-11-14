# DSC563 - Visualization Work for Module 3 & 4

Author: Jeffrey Sirard (MBA student, class of 2027)

Purpose: For Data Visualization (DSC-563)

Instructor: Professor Michael McCarthy

Purpose & Structure: This README.md serves as a guide from the student to assist the professor in navigating a GitHub repository containing graduate work for a data visualization course. For clarity, this will be written as an FAQ.

Questions: Email jasirard@utica.edu.

Background:
- The purpose of this data visualization is to demonstrate skills learned in DSC-563 Modules 3 and 4; The audience and questions are hypothetical.
- Learning Objective: Chart analysis and repair.
- Intended audience: CDC’s High Obesity Program (HOP) leadership team.
- Question 1: How does adult obesity prevalence vary across U.S. states?
- Question 2: How strongly does this track with other prevalent comorbidities?

Relevant Links:
- Collab URL: https://colab.research.google.com/drive/1bmKgFBiojkP8T30XcCcNvGV3XvvbYhUb?usp=sharing​
- GitHub Repository URL: https://github.com/jasirard/DSC563_M03
- GitHub Profile URL: https://github.com/jasirard
- Tableau Evidence URL: https://public.tableau.com/views/sirard_jeffrey_CDC_data_Tableau_FINAL/Comparison?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

File Directory:
- sirard_jeffrey_M03_Preparation_and_Self_Checks.ipynb: Module 3 preparation and self-check Colab workbook where code cells 1–4 were executed to generate the simulated dataset (workshop_data_23.csv).
- workshop_data_23.csv: CSV file containing the simulated dataset used for Module 3 practice exercises.
- sirard_jeffrey_m03_practice.twbx: Tableau practice packaged workbook for Module 3 using simulated dataset.
- PLACES__Local_Data_for_Better_Health,_County_Data,_2025_release_20261105.zip: Compressed CDC "PLACES" dataset used for Modules 3 and 4 analysis and Tableau visualization work.
- sirard_jeffrey_CDC_data_Tableau V1.twb: First draft Tableau workbook created for CDC dataset analysis.
- sirard_jeffrey_CDC_data_Tableau V2.twb: Second draft Tableau workbook created for CDC dataset analysis.
- sirard_jeffrey_CDC_data_Tableau V3.twb: Third draft Tableau workbook created for CDC dataset analysis.
- sirard_jeffrey_CDC_data_Tableau_FINAL.twb: Penultimate Tableau workbook created for CDC dataset analysis.
- sirard_jeffrey_CDC_data_Tableau_FINAL_edit.twbx: Final Tableau packaged workbook created for CDC dataset analysis.
- DSC 563 Module 4 Presentation.pptx: Initial draft of PowerPoint presentation for DSC 563 Module 4 VoiceThread.
- DSC 563 Module 4 Presentation V2.pptx: Final draft of PowerPoint presentation used in DSC 563 Module 4 VoiceThread.
- README.md: This document!

Dataset Summary (CDC PLACES 2023):

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

Instructions to open, run, and check work:

i. GitHub:
   - GitHub Repository (Public): https://github.com/jasirard/DSC563_M03
   - GitHub Profile: https://github.com/jasirard
   - All project files are located in the repository; Click to open each file.

ii. Colab:
   - Access should be granted; If not, please email me at jasirard@utica.edu for access.
   - Open this link: https://colab.research.google.com/drive/1ozcFiaCcGRx2CII_QP4NbQdvwEikjcyd
   - IMPORTANT: Confirm that the assigned variable is set to "23".
   - Click "Run All' from the commands near the top of the page.
   - Simulated data should be present in the "Outputs" folder under "Files" on the right pane.
   - Note: This simulates the data used in Module 3 practice; The assessed work dataset must be extracted from the CDC PLACES .zip file (see File Directory).
   - Find "Files" on the left pane and open.
   - Find "Outputs" sub-folder and open.
