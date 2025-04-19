# Product-Data-Cleaning-Preparation-and-Title-Optimization
## 1. Introduction
In today’s digital marketplace, clean and well-structured product data is essential for effective marketing and improved search engine visibility. This report documents the data cleaning and preparation task, which focuses on enhancing data quality and optimizing product titles for SEO and readability of the Product dataset. The dataset contains 3848 rows (Column title/header inclusive) and 6 key variables/columns.

## 2. Objective
The primary objectives of this task are to:
1.	Resolve data quality issues, including missing values, duplicate records, and inconsistent formatting. 
2.	Standardize key attributes to ensure consistency across the dataset.
3.	Generate a new short_title feature, creating concise and optimized product titles that retain essential details while improving clarity and searchability. 
This report outlines the data cleaning process, the methodology used for title optimization, and the impact of these improvements on the dataset’s overall quality.

## 3. Data Cleaning
The cleaning process focused on ensuring the dataset was accurate, consistent, and free from errors. Several key steps were taken to improve data quality and prepare it for further analysis. 
1.	Handling Missing Values: Missing values were identified from critical columns using Conditional Formatting. Depending on the column’s importance, different strategies were applied. 
•	For the “Bullet_points” column, the missing values were replaced with “Not Available”.
•	For the “Description” column, the missing values were replaced with “No Description Available”.
•	For the “Product_ID and Title” column, 88*2 values/entries were repeated but had all other features missing thereby could not be treated as duplicates and were then removed. 

2.	Removing Duplicate Entries: Duplicate records were checked and removed to avoid redundancy. The Remove Duplicates feature in excel was used to eliminate identical product entries while ensuring unique and relevant data remained. A total of 216 duplicate records were removed while 3630 unique values remained. After removing duplicates and handling missing values a total of 3542 remained.

3.	Standardizing Column Formats: To maintain consistency across the dataset;
•	Column names were formatted uniformly (Example; converting “PRODUCTID” to “PRODUCT_ID” and “PRODUCTTYPEID” to “PRODUCT_TYPE_ID”).
•	Text Formatting inconsistencies such as capitalization on each key variable were corrected. 

4.	Verifying Data Accuracy: Critical variables such as the Product_id, Product_length and product_type_id were checked for;
•	Negative and unrealistic values, none were found except the product_type_id with the value “0” that occurred 72 times which required no change as it was considered to be a correct input.
•	Incorrect data such as number stored as text, none were found.
•	Inconsistent product length decimal placing which was then rounded up to the nearest whole numbers.
Through these steps, the dataset was cleaned and structured to ensure accuracy, consistency, and reliability for further analysis and optimization.

## 4. Short_title creation
The short title feature was introduced to enhance product readability and improve SEO effectiveness. The goal was to create concise yet informative product titles while retaining essential details. 
1.	Methodology for Short Title Optimization: The short titles were generated using the following structured approach;
•	Identifying key product components: Essential details such as product name, category, size and quantity were retained.
•	Removing Redundant words: Common unnecessary phrases like “includes”, “set of”, “features”, and excessive descriptions were eliminated using = TRIM(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(M7,"for"," "),"include"," "),"features"," "))
•	Maintaining clarity and brevity: Title were limited to 45 characters using =IF(LEN(B11)>45,LEFT(B11,45)&" ",B11) while ensuring the products, movies and book titles remained meaningful and informative.
•	Using =SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(A1, ",", ""), "-", ""), "(", ""), ")", ""), "  ", " ") to remove commas, hyphens, extra spaces and brackets.
•	Using TEXT TO COLUMN USING SPACE AS DELIMITER to extract unwanted word from the first few words but was later discovered to be non-feasible.
•	Using =IF(ISNUMBER(FIND(" ", A1)), IF(LEN(TRIM(RIGHT(A1, LEN(A1)-FIND("#", SUBSTITUTE(A1, " ", "#", LEN(A1)-LEN(SUBSTITUTE(A1, " ", "")))))))<4, LEFT(A1, FIND("#", SUBSTITUTE(A1, " ", "#", LEN(A1)-LEN(SUBSTITUTE(A1, " ", ""))))-1), A1), A1) to extract the last words after the last space characters if they are less than 4 and could not make up a complete sentence.

2.	Implementation Examples
Original Title                                                                                             	Optimized Short_Title
PRIKNIK Horn Red Electric Air Horn Compressor Interior Dual Tone Trumpet Loud Compatible with SX4      	Electric Air Horn Compressor

BaronHong Seamless Underwear Half Length Chest Binder for Tomboy Trans Lesbian(Black,2XL)         	    BaronHong Seamless Underwear Half Length

Floor Mats Compatible With 1998-2006 BMW 3 Series E46 | Nylon Black Let Right Front Rear 4PCS Set     	Floor Mats Compatible With 19982006 

Ungifted: My Life and Journey                                                                              	Ungifted: My Life and Journey


3.	Automation and Manual Refinement
•	Excel formulas: IF, LEFT, SUBSTITUTE, LEN, TRIM and TEXT TO COLUMN were used to automate part of the process.
•	A manual review was conducted to ensure accuracy and alignment with the required format.
Through this approach, the short titles became more concise, structured, and SEO-friendly, improving both user readability and search ranking potential.  

## 5. Clean Dataset Overview
After the data cleaning and short title optimization processes, the dataset was transformed into a structured, high-quality format suitable for further analysis. The improvements addressed key data quality issues, ensuring accuracy, consistency, and readability. 
1.	Summary of Improvements
•	Missing values resolved
•	Duplicate entries removed
•	Standardized formatting
•	Anomalies corrected 
•	Short title added

2.	Key Statistics Before and After Cleaning

Metric                           	Before Cleaning       	After Cleaning
Total Records                     	3847               	3541
Duplicates                        	216                 	0
Repeated Values (Column A and B)   	176                 	0
Empty Cells/Missing values (%)    	32.59               	0
Average Product Title Length	4 – 403 Characters    	30 – 50 characters


3.	Impact on Data Usability
•	Enhanced search optimization: Short titles improve discoverability on search engines.
•	Improved Readability: Users can quickly understand product offerings.
•	More Reliable Insights: The clean dataset allows for accurate marketing analysis and decision-making.







## 6. VISUALIZATIONS
![image](https://github.com/user-attachments/assets/2375e277-d050-4f31-9794-59102f5269eb)
![image](https://github.com/user-attachments/assets/b1319e1b-2b71-479b-b2b7-d78251edc319)
![image](https://github.com/user-attachments/assets/fc3e2fa9-e903-4122-8139-e30086e32872)
![image](https://github.com/user-attachments/assets/e786411d-4c1f-4c65-a9a4-85e4ed261002)




 








 

 










