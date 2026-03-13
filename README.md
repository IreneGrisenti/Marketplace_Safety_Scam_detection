# Marketplace Safety - Prioritization of Suspicious Activity

This project builds a decision-support tool to help a Trust & Safety team prioritize the review of suspicious listings on a consumer marketplace app.  

Every week the platform is affected by a small but harmful number of scam listings, spam and suspicious accounts. The Trust & Safety team cannot review everything manually in time, which means real scams stay active longer than acceptable. This tool helps the team focus their time where it matters most.

## What the model does

The model scores every listing with a risk probability and ranks them from most to least suspicious. Each day the team reviews the top 10% highest-risk cases first, ensuring the most dangerous listings are always acted on within the team's daily capacity.

## How it was built

I trained and compared five models on historical platform data, selecting Random Forest as the best performer based on F1 score and ROC AUC. The model was tuned to handle the natural imbalance in the data (roughly 90% legitimate listings and 10% suspicious ones) and validated on a held-out test set to ensure reliable performance on new data.

## Results

Reviewing the top 10% of daily listings the model catches approximately 3x more scams than random selection within the same workload. The daily capacity can be adjusted up or down based on team availability making the tool flexible and operationally practical.

## Installation

Clone the repo and install dependencies:  
`git clone https://github.com/IreneGrisenti/Marketplace_Safety_Scam_detection.git`

Create and activate virtual environment:  
`python -m venv .venv`

Windows PowerShell:  
`.venv\Scripts\Activate`

macOS/Linux:  
`source .venv/bin/activate`

Install dependencies:  
`cd Marketplace_Safety_Scam_detection python -m pip install -r requirements.txt`

## Environment

Python: 3.12.3  
Packages: Numpy, Pandas, Matplotlib, Jupyter, Scikit-learn (see requirements.txt)