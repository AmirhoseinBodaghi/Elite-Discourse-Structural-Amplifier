# Elite-Discourse-Structural-Amplifier
Elite Project: Crisis as a Structural Amplifier This repository contains the analytical pipeline for the Elite Project, a large-scale study of Twitter (X) discourse patterns among 102 global elites (Politicians, Business Leaders, and Celebrities). The project specifically analyzes how the COVID-19 pandemic (post-March 11, 2020) reshaped behavioral patterns and semantic network structures.
📊 Project Overview The pipeline processes 1.26 million tweets spanning from 2010 to 2021. It transitions from raw data unification to causal time-series modeling and semantic network analysis, culminating in a structural mediation model that explains how crisis amplifies pre-existing discourse architectures.
🛠 Repository Structure & Workflow The analysis is divided into five integrated steps. Each notebook builds upon the output of the previous one.
Step 1: Raw Tweet Data Consolidation Goal: Unify fragmented Excel files into a single, clean dataset for each elite individual.
Input: Multiple .xlsx files organized by subfolders.
Key Tasks: Recursive directory traversal, chronological sorting, field extraction, and duplicate tweet ID verification.
Output: Consolidated .xlsx files (one per individual) containing cleaned text and metadata.
Step 2: Preprocessing & Behavioral Aggregation Goal: Clean text data and aggregate behavioral metrics into weekly time-series.
Input: Consolidated files from Step 1.
Key Tasks: URL/Emoji removal, multilingual sentiment analysis (XLM-RoBERTa), and weekly aggregation of tweet volume, length, and interaction types (retweets, replies, quotes).
Output: {Person}_Weekly_Behavioral_Summary.xlsx files.
Step 3: Interrupted Time Series (ITS) Modeling Goal: Quantify the immediate behavioral impact of the COVID-19 announcement.
Input: Weekly summaries from Step 2.
Key Tasks: Construction of a balanced panel (2010–2021), Poisson GLM for tweet counts, OLS for sentiment/length, and category-level meta-regressions.
Output: Regression summaries and significance heatmaps showing level and trend shifts post-intervention.
Step 4: COVID-Centric Ego Network Analysis Goal: Map the semantic structure of COVID-related discourse.
Input: Raw consolidated files from Step 1.
Key Tasks: Named Entity Extraction (spaCy en_core_web_lg), fuzzy entity resolution, and the construction of "COVID-ego" networks (co-occurrence). It performs a 1,000-iteration permutation test to compare COVID discourse against random baseline topics.
Output: High-res network visualizations (.png), GML graph files, and permutation statistics.
Step 5: Structural Mediation & Global Reporting Goal: Test the "Structural Amplification" hypothesis across the full cohort of 102 elites.
Input: Network metrics and permutation results from Step 4.
Key Tasks: OLS regression with HC3 robust standard errors, ANOVA/Tukey HSD category comparisons, and causal mediation modeling.
Output: MASTER_REPORT.xlsx, detailed regression summaries, and heatmaps visualizing how baseline network structures (density, modularity) predicted pandemic-era reorganization.
🚀 Getting Started Prerequisites Python 3.10+
Libraries: pandas, numpy, spacy, networkx, statsmodels, rapidfuzz, matplotlib, seaborn.
spaCy Model: python -m spacy download en_core_web_lg
Usage Data Setup: Place your raw Excel files in the directory structure expected by Step1.ipynb.
Sequential Execution: Run the notebooks in order (1 through 5).
Outputs: Each step will create a dedicated output folder (e.g., /Step4/, /Step5/) to store intermediate datasets, statistical summaries, and visualizations.
📈 Key Findings Summary The project demonstrates that while elites reacted differently in behavior (volume and sentiment), their discourse structure was largely dictated by their pre-pandemic network properties. This suggests that crises serve as "amplifiers" of existing communicative architectures rather than equalizers.
