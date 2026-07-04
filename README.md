# SpendDNA: UPI Transaction Analytics Engine 🧬

> A Python-based financial analytics pipeline that transforms raw, unstructured bank export data into a clean, behavioral "Spotify Wrapped" for personal finances. 

![SpendDNA Final Report Screenshot](link-to-your-screenshot-image.png)
*(Note: Replace the link above with a screenshot of your final ASCII console report)*

##  The Problem
Every Indian student opens a UPI app multiple times a day, yet tracking exact spending patterns remains difficult. Real-world fintech data does not arrive clean—it contains mixed date formats, messy currency strings, and vendor names buried under dozens of banking prefixes (e.g., `UPI-SWIGGY-1234@HDFCBANK`).

## The Solution
SpendDNA is an industry-grade data pipeline built to normalize this chaos. It parses raw CSV bank statements, extracts canonical vendors, categorizes spending, and runs statistical algorithms to flag anomalies and diagnose the user's financial personality.

### Core Features:
*   **The Parser:** Cleans and standardizes 4 different mixed date formats and 3 currency formats simultaneously.
*   **Vendor Normalization:** A custom extraction engine that maps highly varied banking string descriptions to ~35 canonical vendors (e.g., mapping `BUNDL Tech P L` to Swiggy, or `ANI Technologies` to Ola).
*   **Category Tagger:** Maps normalized vendors into 12 distinct macroeconomic categories (Food Delivery, Quick Commerce, Investments, etc.).
*   **Behavioral Analytics:** Computes time-of-day spending patterns (e.g., late-night food orders) and month-over-month category velocity.
*   **Anomaly Detection:** Calculates standard deviations and Z-scores from scratch to flag statistically anomalous transactions ($z > 2$) within specific categories.
*   **Archetype Profiling:** Uses multi-step business logic to assign behavioral profiles (e.g., *The Shopaholic*, *The Late-Night Snacker*, *The YOLO Spender*).

## 🛠️ Tech Stack & Technical Constraints
To demonstrate rigorous data manipulation skills, this project was built under strict technical constraints:
*   **Allowed:** Core Python, `Pandas`, `NumPy`.
*   **Forbidden:**  External Fintech APIs,  Regex (`re`),  Machine Learning models,  Auto-profiling tools (`pandas-profiling`),  Data Visualization libraries (`matplotlib`/`seaborn`—all output is strictly ASCII/text).

##  Key Findings (Test Dataset)
Running the engine on the provided 6-month synthetic dataset (`Data set for DADS June.csv`) yielded extreme behavioral insights:
*   **Severe Deficit:** A calculated savings rate of **-229.3%**, meaning the subject spent roughly 3.3x more than their incoming credits.
*   **E-commerce Dominance:** **36.0%** of total debits went entirely to E-commerce platforms (Amazon, Flipkart, Myntra).
*   **Archetypes Detected:** The algorithm successfully flagged the subject as **THE SHOPAHOLIC** and **THE YOLO SPENDER**.

##  How to Run
1. Clone this repository.
2. Ensure you have Python and `pandas`/`numpy` installed.
3. Place your raw bank export CSV in the root directory (or use the provided test dataset).
4. Run the Jupyter Notebook `SpendDNA.ipynb` cell-by-cell.
5. The final cell will print the formatted ASCII report to your console.

---
*Built as an Industry-Graded Minor Project for the Unlox Academy Data Science curriculum.*
