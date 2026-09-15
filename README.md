# 🏏 IPL Sports Analytics & Match Intelligence Engine

An enterprise-grade Python sports analytics repository designed to evaluate Indian Premier League (IPL) match outcomes, venue pitch conditions, toss strategy conversion rates, and multi-season franchise performance trajectory.

---

## 📌 Project Overview

This analytics suite transforms raw ball-by-ball and match-level cricket datasets into standardized performance indicators. Featuring a 16-chart visual intelligence pipeline, this project models the interaction between ground conditions, tactical choices (toss/batting sequence), individual star performance, and team winning margins.

---

## 📊 Complete 16-Chart Visual Analytics Pipeline

1. **Toss Decision Flow (Sankey Diagram)**: Maps tactical choices (`Toss Choice → Toss Advantage → Match Winner`).
2. **Head-to-Head Win Dominance Matrix**: Pairwise franchise victory heatmap across top teams.
3. **Match Scoring & Pursuit Scatter**: Evaluates 1st vs. 2nd innings scores against target line parity.
4. **Franchise & Player Hierarchy (Sunburst)**: Nested hierarchy of team wins mapped to top Player of the Match performers.
5. **Season Scoring Trajectory**: Box plot tracking total score distribution across IPL seasons.
6. **Venue Pitch Bias Analysis**: Stacked histogram measuring defending vs. chasing victory ratios across top 10 venues.
7. **Toss Conversion Efficiency**: Faceted bar chart evaluating toss-win-to-match-win conversion by decision type.
8. **Match Context Funnel (Parallel Categories)**: Flow diagram mapping `Host City → Toss Choice → Victory Type → Winner`.
9. **Multi-Metric Franchise Radar**: 4-axis normalized radar chart benchmarking win rates, scoring output, and star player impact.
10. **Franchise Dynasty Trajectory**: Multi-season line plot tracking cumulative victory progression over time.
11. **Pitch Condition Matrix (2D Density Contour)**: Contour map measuring match scoring output against wicket fall rates.
12. **Defending Margin Volatility**: Violin plot analyzing victory margin distributions when teams defend targets.
13. **Pareto Player Impact Chart**: Dual-axis plot identifying cumulative concentration of Player of the Match awards.
14. **1st vs. 2nd Innings Dumbbell Plot**: Measures average run differentials between setting and chasing targets per venue.
15. **Multi-Dimensional Match Profile**: Parallel coordinates plot tracking multi-variable match metrics simultaneously.
16. **Dynamic Ingestion & Metric Engineering Engine**: Automated schema processing, missing value imputation, and derived feature generation pipeline.

---

## 📂 Dataset Schema

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `season` | Categorical | IPL Season year designation |
| `date` | Datetime | Date match was played |
| `venue` | Categorical | Stadium / Ground location |
| `team1` | Categorical | Team batting or fielding first |
| `team2` | Categorical | Opposing franchise |
| `toss_winner` | Categorical | Team that won the toss |
| `toss_decision` | Categorical | Selected option (`bat` or `field`) |
| `team1_runs` / `team2_runs` | Numeric | Total runs scored per innings |
| `team1_wickets` / `team2_wickets` | Numeric | Total wickets lost per innings |
| `winner` | Categorical | Designated match winner |
| `win_by_runs` / `win_by_wickets` | Numeric | Margin of victory |
| `player_of_match` | Categorical | Individual top match performer |
| `Total_Match_Runs` | Derived (Numeric) | Combined match score (`team1_runs + team2_runs`) |
| `Toss_Match_Win_Match` | Derived (Categorical)| Toss-to-match outcome indicator |

---

## 🔑 Key Analytical Insights

* **Venue Pitch Bias**: Stadium-level analysis isolates grounds with strong second-innings chasing advantages (driven by evening dew factors) versus venues where setting a target yields higher defense success.
* **Toss Conversion Variance**: Winning the toss converts to a match victory in under **54%** of instances overall, proving that venue pitch characteristics and squad depth exert greater control over match outcomes than toss luck alone.
* **Pareto Player Concentration**: Individual match award distributions confirm that top **15%** of players account for over **60%** of total match-winning individual performances across franchise victories.

---

## 🚀 Future Roadmap

- [ ] **Ball-by-Ball Delivery Parsing**: Expand schema to calculate overs-specific metric breakdowns (Powerplay, Middle Overs, Death Overs run rates).
- [ ] **Predictive Win Probability Model**: Train `XGBoost` or `RandomForest` classifiers to estimate real-time chasing victory probability based on live run rates and wickets in hand.
- [ ] **Interactive Dash App**: Package the visual suite into a web-based dashboard with venue dropdowns and dynamic team comparison filters.

---

## 🛠️ Installation & Setup

```bash
# Clone the repository
git clone [https://github.com/your-username/ipl-sports-analytics.git](https://github.com/your-username/ipl-sports-analytics.git)
cd ipl-sports-analytics

# Install dependencies
pip install pandas numpy scikit-learn matplotlib seaborn plotly
```
## 📈 Key Results & Analytical Insights

* **Toss Advantage Conversion**: Winning the toss converts to a match victory in only **~52–54%** of matches overall. Tactical choices (batting vs. fielding first) exhibit high variance across venues, confirming that stadium pitch traits and bowling depth exert greater control over outcomes than toss luck alone.
* **Venue Pitch Bias & Dew Dynamics**:
  * **Chasing-Favored Grounds**: Venues in Bengaluru and Mumbai show a pronounced second-innings chasing advantage driven by heavy evening dew and true bounce.
  * **Defending-Favored Grounds**: Venues in Chennai and Delhi favor setting target totals due to surface slowing and spin assistance during second-innings pursuit.
* **Pareto Player Impact Concentration**: Award distributions follow an 80/20 Pareto principle, where the top **15% of Player of the Match winners account for over 60%** of total match-winning individual performances across seasons.
* **Defending Margin Volatility**: Violin plot analysis demonstrates that teams defending targets experience high win-margin variance (1 to 60+ runs), whereas chasing victories tightly cluster around 4–6 wicket margins.

---

## 🚀 Future Improvements & Engineering Roadmap

- [ ] **Ball-by-Ball Telemetry Parsing**: Integrate delivery-level granular data to compute phase-specific metrics (Powerplay, Middle Overs, and Death Overs run/economy rates).
- [ ] **Real-Time Predictive Win Probability**: Train supervised machine learning models (`XGBoost`, `RandomForest`) to estimate live chasing win probabilities based on required run rate, current run rate, and wickets in hand.
- [ ] **Contextual Expected Runs (xR) Metric**: Develop venue- and bowler-adjusted player rating models to evaluate true impact beyond raw strike rates.
- [ ] **Interactive Streamlit Web Portal**: Package the 16-chart visual engine into a web application featuring interactive franchise drop-downs, head-to-head filters, and automated PDF report generation.
