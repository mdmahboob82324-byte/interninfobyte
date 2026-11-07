# Task 3: Unemployment Analysis in India

**Intern Infobyte | Data Science Internship**

Analysis of unemployment trends across Indian states using Python (Pandas, Matplotlib, Seaborn, SciPy, scikit-learn), with a focus on the impact of the COVID-19 lockdown in 2020 and the recovery that followed.

## Objective
Analyze unemployment trends using demographic data to identify patterns and potential causes, and turn the findings into policy recommendations.

## Datasets
| File | Period | Description |
|---|---|---|
| `data/Unemployment_in_India.csv` | May 2019 to Jun 2020 | State-wise monthly unemployment rate, estimated employed, labour participation rate, split by **Rural / Urban** |
| `data/Unemployment_Rate_upto_11_2020.csv` | Jan 2020 to Oct 2020 | Same indicators by state, with **Zone** (North, South, East, West, Northeast) and coordinates |

## Methodology
1. Load and inspect both datasets
2. Clean the data: trim column names, remove 28 empty rows, parse dates, fix a duplicated column name, correct swapped latitude and longitude
3. Feature engineering: month, year and COVID phase (Pre-COVID, Lockdown, Unlock)
4. Exploratory data analysis: national trend, rural vs urban, states, zones, heatmaps, recovery, geographic view
5. Statistical tests: Welch t-test and Mann-Whitney (rural vs urban), ANOVA and Kruskal-Wallis (zones), Pearson correlation
6. Bonus: KMeans clustering of states by unemployment behaviour
7. Insights and policy recommendations

## Key Findings
- **Sharp temporary shock:** the average state unemployment rate was about 9 to 10% before the lockdown, jumped to **23.6% in April and 24.9% in May 2020**, fell to about 11.9% in June 2020, and reached **8.0% by October 2020**.
- **Urban hit harder than rural:** 13.2% vs 10.3% on average (p = 0.0003). In the lockdown urban reached 21.6% vs 17.7% rural.
- **Uneven across states:** the largest lockdown increases were in Puducherry (+44 pp), Jharkhand (+27 pp), Tamil Nadu (+27 pp) and Bihar (+23 pp).
- **Zones:** East (+18.5 pp) and South (+17.6 pp) were hit hardest; differences between zones are statistically significant.
- **Chronic problem states:** Haryana, Tripura and Delhi already had high unemployment before COVID.
- **Jobs lost:** the median state lost about 31.5% of its estimated employed between Feb and Apr 2020.
- **Labour participation** and unemployment rate are essentially uncorrelated (r = 0.003).

## Charts
![National trend](images/02_national_trend.png)
![Rural vs Urban](images/03_rural_vs_urban_trend.png)
![State x month heatmap](images/06_state_month_heatmap.png)
![COVID impact by state](images/07_covid_impact_states.png)
![Recovery through Oct 2020](images/11_trend_2020_recovery.png)
![Zone trend](images/12_zone_trend.png)
![State recovery](images/14_state_recovery.png)
![Geographic view](images/16_geo_bubble.png)

## Policy Recommendations
1. Targeted urban employment and wage support for future shocks
2. Keep rural job guarantee schemes funded and ready
3. Prioritise the worst-hit states (Puducherry, Jharkhand, Tamil Nadu, Bihar, Delhi)
4. Treat chronic high unemployment (Haryana, Tripura, Rajasthan, Himachal Pradesh, Jammu & Kashmir) as a skills and job-creation problem
5. Publish unemployment by age, gender, education and industry
6. Build a monthly state-level early-warning dashboard

## Limitations
- The datasets have **no age, gender, education or industry columns**, so those breakdowns are not possible. The demographic dimensions used are Rural/Urban, State, Zone and Time.
- State averages are **unweighted** (a small state counts as much as a large one).
- Some state-months are missing, so a few comparisons use slightly different numbers of states.
- The two datasets overlap in Jan to Jun 2020 but come from separate sources, so they are analysed separately.
- The analysis is descriptive: it shows patterns, not proven causes.

## Project Structure
```
Task3_Unemployment_Analysis/
├── data/
│   ├── Unemployment_in_India.csv
│   └── Unemployment_Rate_upto_11_2020.csv
├── images/                      (charts saved by the notebook)
├── unemployment_analysis.ipynb  (full analysis)
├── requirements.txt
└── README.md
```

## How to Run
```bash
git clone https://github.com/mdmahboob82324-byte/INIB.git
cd INIB/Task3_Unemployment_Analysis

python -m venv venv
venv\Scripts\activate            # Windows  (Mac/Linux: source venv/bin/activate)

pip install -r requirements.txt
jupyter notebook unemployment_analysis.ipynb
```
In VS Code: open the notebook, select the `venv` kernel, and click **Run All**. Run it from inside the `Task3_Unemployment_Analysis` folder so the `data/` and `images/` paths work.

## Author
**Md Chinna Mahaboob**
B.Tech CSE, Holy Mary Institute of Technology and Science
[LinkedIn](https://www.linkedin.com/in/m-d-mahaboob-006527380) | [GitHub](https://github.com/mdmahboob82324-byte)

#interninfobyte
