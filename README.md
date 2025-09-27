# UK Household Income and Expenditure Analysis (2005–2024)

## 📌 Project Overview
This project was inspired by a headline claiming:  
> *“Families in Britain are £20,000 worse off than 20 years ago.”*  

The article lacked data sources or clear numbers, so I set out to investigate this claim using publicly available datasets from the [Office for National Statistics (ONS)](https://www.ons.gov.uk/).  

The analysis covers the period **2005–2024 (20 years)** and explores trends in:  
- Gross household earnings  
- Disposable household income  
- Household final consumption expenditure  
- Household size and population trends  

The goal was to compare how income and spending evolved over two decades and estimate the "savings gap" available to the average UK household.

---

## 📂 Data Sources
All datasets are freely available from ONS. Versions I used are included in this repo for reproducibility.

- **Gross Earnings** (`earnings.xlsx`)  
  [Average Weekly Earnings (AWE), Total Pay](https://www.ons.gov.uk/employmentandlabourmarket/peopleinwork/earningsandworkinghours/datasets/averageweeklyearningsearn01)  
  → Represents gross pay from employment before deductions.

- **Disposable Income** (`disposable_income_per_head.xls`)  
  [Gross Disposable Household Income per head (CRXS)](https://www.ons.gov.uk/economy/grossdomesticproductgdp/timeseries/crxs/ukea)  
  → Includes employment and non‑employment income, net of direct taxes and NI.

- **Consumption (Expenditure)** (`consumer_trends.xlsx`)  
  [Household Final Consumption Expenditure](https://www.ons.gov.uk/economy/nationalaccounts/satelliteaccounts/datasets/consumertrendscurrentpriceseasonallyadjusted)  
  → Includes rent and all household spending categories; values in £ millions.

- **Rent (Sense Check)** (`rent.xlsx`)  
  [Private rents price index](https://www.ons.gov.uk/economy/inflationandpriceindices/datasets/priceindexofprivaterentsukhistoricalseries)  
  → Checked against consumption data but excluded from final model to avoid double counting.

- **Household Size** (`household_size.xlsx`)  
  [Families and households statistics](https://www.ons.gov.uk/peoplepopulationandcommunity/birthsdeathsandmarriages/families/datasets/familiesandhouseholdsfamiliesandhouseholds/current)

- **Population** (`uk_population.xlsx`)  
  [Mid‑year population estimates](https://www.ons.gov.uk/peoplepopulationandcommunity/populationandmigration/populationestimates/timeseries/ukpop/pop)  

Household size and population were used to transform *per head* data into **per household** estimates, comparable with expenditure.

---

## 🛠 Tools and Methods
- **Environment**: Jupyter Notebook (Google Colab)  
- **Libraries**: `pandas`, `numpy`, `matplotlib`, `seaborn`  
- **Steps**:
  1. Data ingestion and cleaning  
  2. Column renaming & standardisation  
  3. Conversion of *per head* metrics into *per household*  
  4. Data visualization of 20‑year nominal trends  
  5. Estimation of the household savings gap (Disposable − Expenditure)  

---

## 📊 Key Findings
- **Nominal income and expenditure nearly doubled** since 2005:  
  - Gross earnings ↑ ~81%  
  - Disposable income ↑ ~86%  
  - Household expenditure ↑ ~70%

- **Savings gap** in 2024 is larger than in 2005 → in nominal cash terms, households have more potential to save today.

- **Inflation‑adjusted (real) disposable income** paints a different story: once adjusted for prices, growth in living standards has been flat for much of this period. This helps explain the contrast between “higher incomes” and the feeling of being “worse off”.

---

## 📈 Example Visualisations
- Gross vs Disposable Income vs Expenditure per household
  <img width="1209" height="598" alt="Screenshot 2025-09-27 at 17 07 07" src="https://github.com/user-attachments/assets/9c719e47-dc26-4311-9e00-81b27d3616fc" />

- Indexed Growth Trends (2005 = 100)
<img width="1207" height="592" alt="Screenshot 2025-09-27 at 17 07 20" src="https://github.com/user-attachments/assets/0f71fedc-a784-495a-8b4c-7c0e69c302d1" />

- Savings Gap over time
<img width="1202" height="591" alt="Screenshot 2025-09-27 at 17 07 32" src="https://github.com/user-attachments/assets/70254a56-752a-4a2b-832e-6bdd8b31d779" />


*(You can view outputs in the Jupyter notebook or generate them with the included scripts.)*

---

## 🧩 Conclusion
The claim that UK families are “£20,000 worse off” over 20 years is **not supported by nominal ONS data**.  

- In **cash terms**, households now earn and spend substantially more.  
- In **real terms** (after adjusting for inflation), disposable income growth has stagnated, which aligns more closely with the perception of being worse off.  



