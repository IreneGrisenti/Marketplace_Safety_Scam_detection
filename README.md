This is an individual implementation of a group school project completed as part of a Machine Learning course. The project was originally developed in a team and this repository contains my personal version where I explored different and additional approaches other than experimented independently.  

The project was structured in two phases: an initial dataset (`historical_data`) was provided to build and evaluate the model, followed by a second release of new unlabelled data (`new_data`)to simulate a real production deployment on unseen listings.  

# Marketplace Safety - Prioritization of Suspicious Activity

This project builds a decision-support tool to help a Trust & Safety team prioritize the review of suspicious listings on a consumer marketplace app.  

Every week the platform is affected by a small but harmful number of scam listings, spam and suspicious accounts. The Trust & Safety team cannot review everything manually in time, which means real scams stay active longer than acceptable. This tool helps the team focus their time where it matters most.

## What the model does

The model scores every listing with a risk probability and ranks them from most to least suspicious. Each day the team reviews the top 100 highest-risk cases first, ensuring the most dangerous listings are always acted on within the team's daily capacity.  

## How it was built

I trained and compared five models on historical platform data, selecting Random Forest as the best performer based on F1 score and ROC AUC. The model was tuned to handle the natural imbalance in the data (roughly 90% legitimate listings and 10% suspicious ones) and validated on a held-out test set to ensure reliable performance on new data.

## Results

Reviewing the top 100 of daily listings the model catches approximately 3x more scams than random selection within the same workload. The daily capacity can be adjusted up or down based on team availability making the tool flexible and operationally practical.

The final model was applied to a new unlabelled dataset of 2000 listings, simulating a real production run. The top 100 highest-risk list contains the most suspicious listings ranked at the top.  

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