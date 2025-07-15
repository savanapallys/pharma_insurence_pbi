Introduction
Datamatrix-ml Pharmaceuticals is one of the leading Pharmaceutical Manufacturing companies with a global presence.
Their Markets are divided into different regions across the world. One of those regions manages the German and Poland Markets.
Company does not sell directly to customers. Instead, they work with a couple of Distributors in all their regions.
They have an agreement with each distributor to share their Sales Data. This is to enable them to gain insights up to the retail level. This data is made available to them in CSV format.
Objectives
The firm has asked us to perform in-depth data analysis to get insight into company sales performance. Specifically, below are the essential requirements to be satisfied…

Requirement ID	For Whom	Requirement Description
DM-DA01-REQ-1	Executive Committee	A high-level overview showing company’s overall sales performance by yearbymonth,bycustomer cities,bychannel,bysub-channel .Should be able to quickly see top drug class by sales, top drug by sales, top customer city by sales`
DM-DA01-REQ-2	Sales Manager/Sales Rep	A detailed overview showing sales by distributors and product, top 5 product, customer and cities, sales numbers split by channels and sub-channels.
DM-DA01-REQ-3	Head of Sales	A detailed report of sales by sales-team split by product and sales by sales-team split by product class.
A detailed analysis showing Top sales managers, Top sales reps, Top product split by sales team contributions answering.
An ability to filter/slice data by year and months.
Table-1 : Requirements

Dataset
The dataset is sourced from each distributor. It contains Pharmaceutical Manufacturing Company’s, Wholesale-Retail Data. The field description of the raw data is given below. The raw dataset pharma-data.csv can be downloaded from here

Field	Description
Distributor	Name of Wholesaler
Customer Name	Name of customer
City	Customer's city
Country	Customer's country
Latitude	Customer's Geo Latitude
Longitude	Customer's Geo Longitude
Channel	Class of buyer (Hospital, Pharmacy)
Sub-channel	Sector of the buyer (Government, Private, etc.)
Product Name	Name of Drug
Product Class	Class of Drug (Antibiotics, etc.)
Quantity	Quantity purchased
Price	Price product was sold for
Sales	Amount made from sale
Month	Month sale was made
Year	Year sale was made
Name of Sales Rep	Name of the Sales rep who facilitated the sale
Manager	Sales rep's Manager Name
Sales Team	Sale rep's team
Table-2 : Data Definition	
Solution Approach
Requirement ID	Solution ID	Proposed Solution
DM-DA01-REQ-1	DM-DA01-SOL-1	An Executive Summary PowerBI dashboard/report page will be built to show a high-level overview of sales data in interactive visuals per the requirements. A year filter will be provided to filter the data by a particular or combination of years
DM-DA01-REQ-2	DM-DA01-SOL-2	A Distributor & Customer Analysis PowerBI dashboard/report page will be provided with interactive visuals showing data as per the requirement
DM-DA01-REQ-3	DM-DA01-SOL-3	A Sales Team Performance PowerBI dashboard/report page will be provided with interactive visuals showing data as per the requirement. year and month slicers will be provided to slice/filter data by year and/or months
Table-3 : Proposed Solution

Exploratory Data Analysis (EDA) [pandas]
To understand, be familiar with and check the sanity of the given data, the first step is EDA. This project's initial data exploration has been carried out using the pandas python package. Here, in general, we are checking...

Presence of any missing values
Any unusual value (outliers)
Incorrect values (e.g., sales column, we see -ve numbers)
Determine categorical and numeric columns
Determine dimensions of categorical columns and range of numeric columns Note that these steps can be performed using PowerQuery Editor and/or excel; however, pandas makes it much easier and faster; on top of that, pandas can handle massive datasets.
EDA steps can be found in the data-exploration.ipynb notebook.

Data Cleaning and Transform [PowerQuery Editor]
The provided dataset was relatively clean and well organized; hence only a little work was required in this step; the following steps were carried out...

Correct column heading provided
Correct data type is assigned to columns
Data Model Creation [PowerBI Desktop]
The provided data is in a single table format. The exploration revealed that it contains both categorical (dimensions) and numeric (facts) data.
We build a data model where dimensions and facts are separated, then they are linked together by logical relationship to form a star schema. The resultant data model is shown below...
<img width="1360" height="763" alt="data-model" src="https://github.com/user-attachments/assets/29b45da5-557a-41b8-b386-1157b06feb9d" />
The tables with the prefix DIM are dimension tables, and FACT is the fact table.

Report Creation [PowerBI Desktop]
Three interactive reports/dashboards (report pages) will be created to implement the proposed solution. Refer to Table-3: Proposed Solution for detailed requirements and the corresponding proposed solution.

1. Executive Summary Report [DM-DA01-SOL-1]
This high-level report shows the overall sales figures and elements at a glance.
<img width="1441" height="772" alt="Screenshot 2025-07-15 0854301" src="https://github.com/user-attachments/assets/ef90b49b-9ff0-4d2e-94f5-4b9edf5e5244" />
<img width="1450" height="810" alt="Screenshot 2025-07-15 0854582" src="https://github.com/user-attachments/assets/1c7cb21e-f95a-44b7-9e1e-3636457e178f" />
<img width="1408" height="722" alt="Screenshot 2025-07-15 0855543" src="https://github.com/user-attachments/assets/f4553a25-2dab-43ae-b5da-ba5069b8aff1" />
