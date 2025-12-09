# Las Vegas Tourism Analysis (1970–2024)
*A 50+ year exploration of visitor trends, disruptions, and recovery patterns.*

---

## 🔎 TL;DR
This project analyzes **annual Las Vegas visitor data from 1970–2024** to uncover long-term trends, major disruptions (economic recessions, COVID-19), and recovery cycles.

**Key takeaways:**
- Long-term growth from **~6.8M → ~42.5M visitors**
- Clear downturns during **2008–2009** and a historic **-55% collapse in 2020**
- Strong post-pandemic rebound approaching pre-2020 levels by 2023
- Year-over-year growth highlights volatility and the city’s resilience

**Tech:** Python, Pandas, NumPy, Matplotlib, Seaborn, Google Sheets, Google Colab

---

## Introduction & Goal
This project undertakes an analysis of historical tourism data for Las Vegas, examining annual trends over more than five decades, from 1970 to 2024. The primary data source is the comprehensive "Las Vegas Historic Tourism Statistics" report provided by the Las Vegas Convention and Visitors Authority (LVCVA). The data was originally in a PDF format and was subsequently processed and cleaned for this analysis.

The main objective of this project is to:
* Identify and visualize the long-term trends in annual visitor volume to Las Vegas.
* Pinpoint key periods of significant growth, stagnation, or decline.
* Discuss how these trends might visually correlate with known major economic events or significant local developments (e.g., the COVID-19 pandemic, economic recessions).

This exploratory analysis aims to provide a clear overview of the evolution of Las Vegas as a major tourist destination based on its historical visitor data.

## Data Sourcing & Preparation
The primary data for this analysis was sourced from the "Las Vegas Historic Tourism Statistics (1970-2024)" report, a PDF document published by the Las Vegas Convention and Visitors Authority (LVCVA). This report contains annual data for various tourism indicators crucial for understanding long-term trends.

The data preparation process involved several stages to transform the raw PDF data into a clean, analyzable format:

1. **Initial Extraction & Manual Cleaning:** Due to the complexities of directly parsing the PDF programmatically for all tables, the PDF was first converted to a CSV file. This CSV was then meticulously reviewed and cleaned in Google Sheets. This manual step addressed initial parsing issues, corrected header alignment, removed irrelevant non-data rows, and ensured a more structured tabular format suitable for import.

2. **Loading into Pandas & Further Refinement:** The cleaned CSV file was subsequently uploaded to Google Drive and loaded into a Pandas DataFrame within a Google Colab environment for final programmatic cleaning and preparation.

3. **Header Correction & Row Trimming (in Pandas):**
    * The correct row containing the column headers (e.g., "Year", "Visitor Volume", "Convention Attendance") was identified and programmatically set as the DataFrame's column headers.
    * Any remaining non-data rows at the beginning (above the true header) and footer rows (containing notes, sources, or compilation information) were removed to isolate the core data spanning from 1970 to 2024.

4. **Column Name Standardization:** Column names were standardized by stripping any leading/trailing whitespace. Typographical errors in column names (such as "Vistitor Volume" being corrected to "Visitor Volume") were also addressed.

5. **Data Type Conversion & Cleaning (Key Columns):**
    * The **'Year'** column was converted to an integer data type.
    * The **'Visitor Volume'** column required cleaning to remove comma separators from the numerical strings. After cleaning, it was converted to an integer data type. It was verified that these numbers represent the actual visitor counts and did not require further scaling (e.g., multiplication by 1000).

6. **Final Verification:** After these steps, the resulting DataFrame used for analysis contained 55 entries, one for each year from 1970 to 2024, with no missing values in the critical 'Year' and 'Visitor Volume' columns.

## Analysis & Key Findings
The analysis of cleaned annual Las Vegas visitor data from 1970 to 2024 revealed significant long-term trends and specific periods of notable change.

### Overall Visitor Volume Trend
The annual visitor volume showed a strong general upward trend from approximately 6.8 million in 1970, reaching a peak of about 42.5 million in 2019 before the pandemic-induced drop. Key periods of accelerated growth were observed, particularly in the 1990s. There were also noticeable dips corresponding to economic downturns, such as around 2008-2009 (dropping to about 36.4 million), and a dramatic plunge in 2020 to approximately 19 million due to the COVID-19 pandemic. The subsequent years showed a strong recovery, with visitor numbers climbing back towards approximately 40.8 million by 2023.

![Las Vegas Visitor Trends](images/LVCVA_Plot.png)
*Figure 1: Visitor volume crash and recovery (2019-2023)*

### Year-over-Year (YoY) Growth Rate
To better understand the dynamics and volatility of visitor volume changes, the year-over-year (YoY) growth rate was calculated and analyzed. The YoY growth bar chart vividly illustrates periods of rapid change.

The most significant negative growth occurred in 2020, with an approximate drop of -55% due to the COVID-19 pandemic. This was followed by the largest positive growth in 2021, a rebound of around +68% to +70%. Other notable years of strong positive growth included 1996 (approx. +20%), 1992 (approx. +15%), and 2022 (approx. +20%). Periods of smaller decline were evident around 2008-2009 (approx. -4% to -5% each), corresponding to the financial crisis.

The chart clearly illustrates that while Las Vegas visitor numbers have experienced ups and downs, the impact of the 2020 event and the subsequent rebound in 2021 were unprecedented in scale over this period.

![Year-over-Year Growth Rate](images/LVCVA_Bar_Chart.png)
*Figure 2: Annual percentage change in visitor volume*
