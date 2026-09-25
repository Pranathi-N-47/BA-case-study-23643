# User Preferences for YouTube Recommendation Systems: A Business Analytics Case Study

A data-driven study analysing how user habits, satisfaction, and friction points influence viewing reliance on YouTube recommendations.

**Author:** Pranathi Nibhanipudi  
**Register Number:** CB.SC.U4CSE23643  
**Section:** CSE-G  
**Domain:** Digital Media Analytics / Recommendation Systems  

---

## Overview

Recommendation algorithms drive a large portion of digital media consumption, yet platforms often struggle to balance user engagement with content repetition and clickbait fatigue. This case study explores user interactions with YouTube's recommendation system, evaluating how viewing time, platform satisfaction, content repetition, and skip behaviours impact how much users rely on recommendations.

The study scales an initial 115-response survey to a 10,000-record dataset using an Empirical Gaussian Copula to preserve distributions and correlations, followed by exploratory analysis and predictive regression modelling.

---

## Project Structure

```text
├── README.md
├── data/
│   ├── seed_dataset.csv                  # Raw survey responses (N = 115)
│   ├── seed_dataset_cleaned.csv          # Cleaned and standardised survey responses
│   └── synthetic_youtube_dataset_10k.csv # Scaled dataset via Gaussian Copula (N = 10,000)
├── analysis.ipynb                        # Main Jupyter notebook containing the full analysis (Sections 1–5)
├── Case_Study_Report.pdf                 # Final case study report document
└── LICENSE                               # MIT License
```

---

## Key Analysis Sections

1. **Environment Setup & Data Loading (Section 1):** Configuration of data manipulation, statistical, and plotting libraries (`pandas`, `numpy`, `scipy`, `scikit-learn`, `matplotlib`, `seaborn`, `plotly`).
2. **Data Cleaning & Feature Engineering (Section 2):** Repairing spreadsheet date conversions, handling missing responses, and encoding multi-select survey questions into compact archetypes.
3. **Dataset Scaling via Gaussian Copula (Section 3):** Expanding the empirical survey sample to 10,000 records while preserving exact statistical distributions and correlations (verified using two-sample Kolmogorov-Smirnov tests).
4. **Exploratory Data Analysis (Section 4):** Target-focused visualisations examining how satisfaction, repetition fatigue, skip counts, and surface choices relate to `recommendation_watch_pct`.
5. **Predictive Modelling & Evaluation (Section 5):** Training and evaluating regression models to predict `recommendation_watch_pct` (0–100%):
   - **Ridge Regression (Baseline):** Linear model providing standardised coefficients ($\beta$) for feature interpretability ($R^2 = 0.5263$, $\text{RMSE} = 20.73$).
   - **Random Forest Regressor (Ensemble):** Non-linear model capturing complex user interaction patterns ($R^2 = 0.9659$, $\text{RMSE} = 5.56$).

---

## Key Findings

- **Primary Predictive Drivers:** The strongest features determining recommendation watch percentage are `watch_more_likelihood`, `repetition_frequency`, `surface_home_flag`, and `weekly_hours`.
- **Repetition Fatigue:** Daily users experiencing content repetition "Very Often" see a 10-point drop in median recommendation watch percentage compared to those who experience it "Rarely".
- **Friction & Abandonment:** Skipping more than 20 videos pushes over 88% of users to either manually search for videos or leave the platform entirely.
- **Surface Adoption:** Users who browse across multiple surfaces (Home Feed, Shorts Feed, Subscriptions) report the highest recommendation reliance (median 60.0%), while search-reliant users report the lowest (median 10.0%).

---

## Setup & Execution

### Prerequisites
- Python 3.10 or higher
- PowerShell or standard terminal

### Setup Virtual Environment

```powershell
# Create and activate virtual environment
python -m venv venv
.\venv\Scripts\Activate.ps1

# Install required dependencies
pip install numpy pandas scipy matplotlib seaborn plotly scikit-learn nbconvert ipykernel
```

### Running the Notebook

You can open and run `analysis.ipynb` directly in VS Code / Jupyter Lab, or execute the full notebook from the command line:

```powershell
.\venv\Scripts\python.exe -m nbconvert --to notebook --execute analysis.ipynb --output analysis.ipynb
```

---

## License

This project is licensed under the [MIT License](LICENSE).
"# BA-case-study-23643" 
