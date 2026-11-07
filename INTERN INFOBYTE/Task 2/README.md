# INIB - Task 2: Exploratory Data Analysis (Sports - IPL)

Intern Infobyte internship project. Python, Pandas, Matplotlib, Seaborn in Jupyter Notebook.

## Objectives
- EDA of the Indian Premier League dataset (2008-2019)
- Success analysis: top teams, top players, factors behind wins and losses
- Endorsement recommendations (performance + popularity)
- Storyboard with annotations, images and audio

## Files
- `IPL_EDA_Task2.ipynb` - full analysis
- `matches.csv`, `deliveries.csv` - dataset (756 matches, 179,078 deliveries)
- `images/` - charts saved by the notebook

## Key findings
- Mumbai Indians: most wins (109) and titles (4); Chennai Super Kings: best win % (61.0%), 3 titles
- Top run scorers: V Kohli (5,429), SK Raina (5,407); most sixes: CH Gayle (326)
- Top wicket taker: SL Malinga (170)
- Toss winner won only 52.3% of matches; chasing teams won 55.2%
- Winners scored more in every phase and lost fewer wickets (4.5 vs 7.2)
- Batting first, 200+ wins 83.1% of matches
- Endorsement picks: AB de Villiers, CH Gayle, MS Dhoni (batsmen); A Mishra, SL Malinga, Harbhajan Singh (bowlers); Mumbai Indians, Chennai Super Kings (teams)

## How to run
```bash
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook IPL_EDA_Task2.ipynb
```
Keep `matches.csv` and `deliveries.csv` in the same folder as the notebook.
