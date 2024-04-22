# Road Accident Analysis

## Project Goals

- Primary KPI - Total Casualties and Total Accident values for the Current Year and YoY growth
- Primary KPIs - Total Casualties by Accident Severity for the Current Year and YoY growth
- Secondary KPI - Total Casualties concerning vehicle type for the Current Year
- Monthly trend showing a comparison of casualties for the Current Year and the Previous year
- Casualties by Road Type for Current Year
- Current Year Casualties by Area / Location & by Day / Night

## Stakeholders

- Ministry of Transport
- Road Transport Department
- Police Force
- Emergency Service Department 
- Transport Operators
- Public
- Media

### Steps followed 

- Step 1: Load data into Power BI Desktop, the dataset is an Excel file.
- Step 2: Data Transformation - rename column values
- Step 3: Data Processing using DAX function (Time Intelligence Function) - Create a new table 'Calendar' with the columns 'Date', 'Year', and 'Month' concerning the original dataset.
- Step 4: Go to Model View < Manually connect the two tables i.e, Road Accident data (' Accident_Date) & Calendar( 'Date')
- Step 5: Create dynamic fields using DAX:

    CY casualities = TOTALYTD(SUM(Data[Number_of_Casualties]), 'Calendar'[Date])\
    PY Casualities = CALCULATE(SUM(Data[Number_of_Casualties]), SAMEPERIODLASTYEAR(('Calendar'[Date])))\
    YOY = (Data[CY casualities] - Data[PY Casualities]) / Data[PY Casualities]\
    CY accident = TOTALYTD(COUNT(Data[Accident_Index]), 'Calendar'[Date])\
    PY accident = CALCULATE(COUNT(Data[Accident_Index]), SAMEPERIODLASTYEAR('Calendar'[Date]))\
    YOY acc = ([CY accident] - [PY accident]) / [PY accident]

- Step 6: Dashboard design and Layout
- Step 7: Add interactivity

## Report Snapshot (Power BI DESKTOP)

![Road accident](https://github.com/SnehaNatraj/Road-Accident-Analysis/assets/163089747/8d3862b6-19f5-49cb-8fb4-e3b3c8554ae5)

## Inference

- CY Casualties and Accident is down by **~ 11.9%** in comparison to Previous Year
- CY Fatal Casualties is down by **33%** in comparison to Previous Year
- CY Severe Casualties is down by **16.2%** in comparison to Previous Year
- CY Slight Casualties is down by **10.6%** in comparison to Previous Year




