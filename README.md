# Winning Space Race With Data Science

IBM **Applied Data Science Capstone** project. SpaceX Falcon 9 launches are far cheaper when the first stage lands and can be reused. This project builds a data pipeline and models that predict whether the first stage will land successfully.

## Project flow

The work is split into lab-style Python scripts (Colab exports) that follow the course sequence:

| Script | Stage |
|--------|--------|
| `Collecting the data.py` | Pull launch data from the SpaceX API |
| `Web scraping Falcon 9 and Falcon Heavy Launches Records from Wikipedia.py` | Scrape Falcon 9 / Heavy launch tables from Wikipedia |
| `Data wrangling.py` | Clean data and create a landing-class label |
| `Exploring and Preparing Data.py` | EDA and feature prep (one-hot encoding, etc.) |
| `SQL Notebook for Peer Assignment.py` | SQL analysis on launch data |
| `Python Notebook for Peer Assignment.py` | Peer-graded Python / SQL notebook |
| `Launch Sites Locations Analysis with Folium.py` | Map launch sites and success patterns with Folium |
| `SpaceX Falcon 9 First Stage Landing Prediction P4.py` | Interactive visual analytics / dashboard prep |
| `Space X Falcon 9 First Stage Landing Prediction P5.py` | ML classification with hyperparameter tuning |
| `spacex_dash_app.py` | Plotly Dash app for launch success exploration |

## Machine learning (P5)

Models compared with `GridSearchCV` (10-fold CV):

- Logistic Regression  
- Support Vector Machine (SVM)  
- Decision Tree  
- K-Nearest Neighbors (KNN)  

Each model is scored on validation accuracy; the notebook then evaluates the chosen configuration on a held-out test split. Re-run P5 locally to reproduce the best-model printouts (scores are not hard-coded into this README).

## Dashboard

`spacex_dash_app.py` provides:

- Launch-site dropdown  
- Success-rate pie chart  
- Payload-mass range slider  
- Scatter plot of payload vs. landing outcome  

You need the course Dash CSV (commonly `spacex_launch_dash.csv`) next to the app, or update the data path inside the script.

## Tech stack

Python, Requests, BeautifulSoup, Pandas, NumPy, Matplotlib, Seaborn, Folium, scikit-learn, Plotly Dash, SQL / SQLite

## How to run

```bash
git clone https://github.com/mahmouduskudar/winning_space_race.git
cd winning_space_race
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install pandas numpy matplotlib seaborn requests beautifulsoup4 scikit-learn folium dash plotly jupyter
```

Recommended order:

1. Data collection & scraping scripts  
2. Wrangling / EDA / SQL notebooks  
3. Folium map analysis  
4. Landing prediction (P5)  
5. `python spacex_dash_app.py` for the dashboard  

**Note:** Several files were exported from Google Colab and may still contain Colab-only helpers (`piplite`, browser `fetch`, `/content/...` paths). Adjust those paths before running fully offline.
