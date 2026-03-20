This is an individual implementation of a group school project completed as part of a Machine Learning course. The project was originally developed in a team and this repository contains my personal version where I explored different and additional approaches other than experimented independently.  

The project was structured in three phases: an initial dataset (`historical_data`) was provided to build and evaluate the model, followed by a second release of new unlabelled data on Tuesday 17/03/2026 (`new_data`) to simulate a real production deployment on unseen listings. Finally, on Thursday 19/03/2026, the true labels for the new data were released (`new_data_target 1`), allowing a full evaluation of the model's performance.  

# Marketplace Safety - Prioritization of Suspicious Activity

This project builds a decision-support tool to help a Trust & Safety team prioritize the review of suspicious listings on a consumer marketplace app.  

Every week the platform is affected by a small but harmful number of scam listings, spam and suspicious accounts. The Trust & Safety team cannot review everything manually in time, which means real scams stay active longer than acceptable. This tool helps the team focus their time where it matters most.

## What the model does

The model scores every listing with a risk score and ranks them from most to least suspicious. Each day the team reviews the top 100 highest-risk cases first, ensuring the most dangerous listings are always acted on within the team's daily capacity.  

## How it was built

I trained and compared five models on historical platform data, selecting Random Forest as the best performer based on F1 score and ROC AUC. The model was tuned to handle the natural imbalance in the data (roughly 90% legitimate listings and 10% suspicious ones) and validated on a held-out test set to ensure reliable performance on new data.

## Results

Across training, test and new data the model delivers consistent performance with an F1 score of ~0.31 and a recall of ~0.70, confirming it generalizes well to unseen listings without overfitting.

At a daily review capacity of 100 cases the model identifies real scams at up to 4.5x the rate of random selection. Nearly 1 in 2 flagged cases is a real scam, ensuring the Trust & Safety team spends their time efficiently on the highest-risk listings.

The model was validated on a new unlabelled dataset of 2000 listings simulating a real production run. When the true labels were subsequently released, the results confirmed that the model performs reliably on real unseen data, catching 48 out of 212 scams in the top 100 flagged cases, consistent with all previous evaluations.

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