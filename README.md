# ⚽ Football Player Scouting & Similarity Tool

### Data Science | Machine Learning | Football Analytics

A data-driven football scouting tool that identifies statistically similar players, discovers potential replacements, and explores cost-effective transfer targets across Europe's Big Five football leagues using Python and machine learning.

---

## 📌 Project Overview

Football clubs must identify players who fit their tactical requirements while working within transfer budgets. Traditional scouting relies heavily on observation and expert judgement, while statistical analysis can provide additional evidence to support recruitment decisions.

This project uses player performance statistics and market valuation data to build a scouting tool that compares players based on their playing styles, performance metrics, and estimated market values.

The system uses dimensionality reduction, clustering, and similarity analysis to identify players with comparable statistical profiles and highlight potentially cheaper alternatives.

## 🎯 Project Objectives

* Identify players with similar statistical performance and playing styles.
* Group players into distinct positional roles using unsupervised machine learning.
* Compare players using per-90-minute performance metrics.
* Discover younger players who could be alternatives to established footballers.
* Identify potentially cost-effective transfer targets.
* Visualise player strengths and weaknesses through radar charts.

## 📊 Dataset

The project analyses outfield players from the 2024–25 season across Europe's Big Five leagues:

* Premier League — England
* La Liga — Spain
* Bundesliga — Germany
* Serie A — Italy
* Ligue 1 — France

Three CSV files are required:

| Dataset                      | Purpose                                 |
| ---------------------------- | --------------------------------------- |
| `players_data-2024_2025.csv` | Player performance statistics           |
| `players.csv`                | Player information and identification   |
| `player_valuations.csv`      | Historical and latest market valuations |

**Data sources:** FBref-style player statistics and Transfermarkt player and valuation data.

The actual files and their sources should be documented in the repository. Check the applicable terms and licensing conditions before redistributing datasets.

## 🛠️ Technologies Used

* **Python** — Core programming language
* **Pandas & NumPy** — Data cleaning and feature engineering
* **Scikit-learn** — Machine learning and similarity analysis
* **PCA** — Dimensionality reduction
* **K-Means Clustering** — Player role identification
* **Cosine Similarity** — Player comparison
* **Matplotlib** — Data visualisation
* **RapidFuzz** — Fuzzy player-name matching
* **Google Colab / Jupyter Notebook** — Development environment

## ⚙️ Methodology

### 1. Data Cleaning and Preparation

* Load and consolidate the three datasets.
* Exclude goalkeepers and focus on outfield players.
* Merge records for players who represented multiple clubs during the season.
* Apply a minimum playing-time threshold of 900 minutes.
* Convert relevant counting statistics into per-90-minute metrics.

### 2. Feature Engineering

Create performance features covering attacking output, passing, progression, ball carrying, and defensive contributions.

Per-90 statistics help make comparisons between players with different amounts of playing time more meaningful.

### 3. Dimensionality Reduction

Apply feature standardisation and Principal Component Analysis (PCA) to reduce dimensionality while retaining 90% of the variance.

### 4. Player Role Clustering

Use K-Means clustering to group defenders, midfielders, and forwards into statistical profiles.

The project explores silhouette scores to help assess cluster quality and assigns football-oriented role labels based on the resulting profiles.

Examples include:

* Ball-playing centre-back
* Attacking full-back
* Defensive midfielder
* Deep playmaker
* Attacking creator
* Penalty-box striker
* Creative wide forward

### 5. Player Similarity Analysis

Use cosine similarity in PCA-transformed feature space to identify players with comparable statistical profiles.

The tool supports filters for age, league, position, and playing role.

### 6. Player Visualisation

Generate radar charts that compare selected players using performance percentiles relative to others in the same positional group.

### 7. Cost-Effective Recruitment

Match player records with Transfermarkt data and compare market valuations to identify statistically similar players with lower recorded valuations.

The analysis includes similarity thresholds, valuation ratios, potential savings, and contract-expiry information where available.

## 🔍 Key Features

| Feature                    | Description                                           |
| -------------------------- | ----------------------------------------------------- |
| Player Role Classification | Groups players into statistical playing profiles      |
| Similar Player Finder      | Finds players with comparable performance metrics     |
| Young Talent Discovery     | Filters potential alternatives by age                 |
| Player Comparison          | Visualises strengths using radar charts               |
| Transfer Value Analysis    | Identifies lower-valued players with similar profiles |
| Recruitment Filters        | Refines results by league, age, and role              |

## 🚀 Getting Started

### Option 1: Run in Google Colab

1. Upload the Jupyter Notebook to Google Colab.
2. Prepare the three required CSV files.
3. Run the notebook cells in order.
4. Upload the three CSV files when prompted.
5. Review the generated clusters and inspect the player-role assignments.
6. Experiment with the player similarity and cheaper replacement functions.

### Option 2: Run Locally

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

Install the required packages:

```bash
pip install pandas numpy matplotlib scikit-learn rapidfuzz jupyter
```

Open the notebook:

```bash
jupyter notebook
```

**Note:** The notebook currently uses Google Colab's file-upload functionality. For local execution, replace that section with local file paths.

## 💡 Example Use Cases

* Find players with statistical profiles similar to Cole Palmer.
* Discover younger alternatives to established forwards.
* Compare midfielders across different European leagues.
* Identify potential replacements for expensive players.
* Examine how players differ from others in the same position.
* Support recruitment shortlists with quantitative evidence.

## 🔮 Future Improvements

* Develop an interactive scouting dashboard using Streamlit.
* Introduce possession-adjusted performance metrics.
* Improve positional and tactical role classification.
* Add contract-expiry filters to identify potential recruitment opportunities.
* Develop a value-for-money scoring system.
* Integrate additional licensed or open football datasets.
* Incorporate match-event data for deeper tactical analysis.

## ⚠️ Limitations

* Statistical similarity does not guarantee tactical or behavioural equivalence.
* Market valuations are estimates, not confirmed transfer fees.
* Player-name matching can introduce errors and requires validation.
* Per-90 statistics do not account for every contextual factor, such as team possession or opposition strength.
* Cluster labels are interpretations of statistical profiles rather than official football positions.
* Results depend on dataset coverage, feature selection, and model parameters.

The tool is intended to support scouting decisions, not replace professional scouting judgement.

## 👨‍💻 Author

**Abhijith Nair**

Aspiring Sports Analyst | Data Science | Machine Learning | Football Analytics

Interested in applying data science and machine learning to football performance analysis, player recruitment, and evidence-based scouting.

---

*Built to explore how data science can support smarter football recruitment.* ⚽📊
