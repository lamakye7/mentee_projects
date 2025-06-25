> **Project Title:** Smart Rental Pricing and Recommendation System for Ghana

> **Project Owner:** Louis Amakye
> 
> **Project Supervisor:** David Adarkwah  
> **Github Profile:** [Github](https://github.com/lamakye7)  
> **LinkedIn Profile:** [Linkedin](https://www.linkedin.com/in/louis-amakye-34358816b/)

## Table of Contents

- [Table of Contents](#table-of-contents)
- [Problem Statement](#problem-statement)
- [Supporting Statistics \& Evidence](#supporting-statistics--evidence)
- [Why This Is a Problem](#why-this-is-a-problem)
- [Project Goal](#project-goal)
- [Use Cases \& Stakeholders](#use-cases--stakeholders)
- [Core Features](#core-features)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Technology Stack](#technology-stack)
- [KPIs \& Evaluation Metrics](#kpis--evaluation-metrics)

## Problem Statement

Ghana's rental housing market is highly fragmented, informal, and lacks pricing transparency. With no standardized pricing mechanisms or centralized listings platform, most tenants and landlords rely on guesswork, agent recommendations, or informal networks such as WhatsApp groups and roadside signboards to determine rental prices.

This lack of structure has led to:

- Widespread pricing inconsistencies
- Overpricing in prime locations
- Undervaluation in less visible areas
- Longer listing times and tenant frustrations
- Missed investment opportunities due to poor data visibility

## Supporting Statistics & Evidence

| Key Insight                  | Data Point / Source                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------|
| Rising Urban Demand          | Ghana's urban population rose from 50% in 2010 to over 58% in 2022 — driven by migration & job search   |
| Housing Deficit              | Ghana faces a housing deficit of over **1.8 million units** *(Ministry of Works & Housing)*             |
| Rent as % of Income          | Rent in urban areas consumes up to **40–60%** of monthly income for lower-middle class tenants *(GSS)*  |
| Price Inconsistency          | Rent for similar 2-bed apartments in Accra can vary by over **400%** depending on listing source        |
| Informal Market Dependence   | Over **65% of rentals** are advertised informally *(WhatsApp, signs, agents)*                           |
| Agent-Driven Pricing         | Most landlords set prices based on agent intuition, with no data benchmark                              |

**Sources:** Ghana Statistical Service (GSS), Ministry of Works & Housing, World Bank Urbanization Review, Jiji Ghana, MeQasa, Tonaton

## Why This Is a Problem

- There is no pricing transparency. As such, tenants can't determine if a listing is overpriced, and landlords often price arbitrarily.
- No platform to analyze trends, recommend better alternatives, or visualize market dynamics.
- Also, informal listings and lack of data make it difficult for policymakers to understand supply-demand dynamics.
- Agents dominate pricing decisions, introducing bias and inefficiency.

## Project Goal

The main goal of this project is to build a data-driven rental intelligence system to help:

- Tenants find fairly priced homes
- Landlords/Agents set competitive prices
- Investors identify high-growth neighborhoods
- Policy Makers understand housing gaps

## Use Cases & Stakeholders

| Use Case                  | Stakeholder          | Value                                                       |
|---------------------------|----------------------|-------------------------------------------------------------|
| Get rent estimate         | Tenants              | Avoid overpaying, compare listings easily                   |
| Smart pricing assistant   | Landlords/Agents     | Set optimal rental prices, faster property turnover         |
| Explore rental trends     | Investors            | Identify hotspots for high ROI                             |
| Personalized search       | Renters              | Discover suitable listings efficiently                      |
| Supply-demand dashboard   | Policy Makers / NGOs | Gain insights into affordability and availability trends    |

## Core Features

| Feature                  | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| Price Prediction API     | Predicts rental prices based on features like location, size, and amenities |
| Property Recommender     | Suggests similar or better-value listings                                   |
| Trend Dashboard          | Interactive heatmaps and trend lines for pricing across neighborhoods       |
| NLP Listing Insights     | (Optional) Auto-summarize or evaluate listing quality                       |

## Dataset

| Component         | Description                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| Source            | Scraped from [Tonaton Ghana - Houses & Apartments for Rent](https://tonaton.com/c_houses-apartments-for-rent) |
| Format            | JSON/CSV records with fields: title, price, location, bedrooms, bathrooms, amenities, date posted, URL |
| Frequency         | Scraped weekly via Airflow/Cron                                    |
| Storage           | Raw data stored with timestamps in AWS S3 bucket |
| Enrichment        | Geocoded neighborhoods using GeoPy, normalized amenities, converted prices  |
| Volume (Estimate) | ~500–1000+ listings per scrape, depending on frequency and filtering        |

## Methodology

| Step                       | Description                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| 1. Scraping                | Use Selenium to scrape property listings from Jiji Ghana                     |
| 2. Raw Storage             | Save listings as JSON/CSV in local/S3-bucket             |
| 3. Cleaning & Normalization| Standardize text, fill missing values, deduplicate, parse locations         |
| 4. Feature Engineering     | Create new variables: price per m², amenity count, neighborhood zones       |
| 5. Model Training          | Use machine learning to predict rental prices       |
| 6. Recommendations         | Use content-based filtering or similarity scoring to suggest properties     |
| 7. API Deployment          | Serve predictions and recommendations via FastAPI                           |
| 8. Dashboarding            | Build Streamlit app for trend visualization and user insights                |
| 9. Monitoring              | Track drift, prediction errors, API usage via Evidently AI, MLflow & Airflow               |

## Technology Stack

| Layer               | Tools                                                                 |
|---------------------|-----------------------------------------------------------------------|
| Web & Data Scraping | Selenium, Beautifulsoup                                               |
| Data Storage        | PostgreSQL, AWS S3                                                    |
| ORM & Migrations    | SQLAlchemy, Alembic                                                   |
| Configuration       | Dynaconf, .env, yaml                                                  |
| Automation          | Makefile, Shell scripts                                               |
| Code Quality        | Ruff (linting), Black (formatting)                                    |
| Logging             | Loguru                                                                |
| Orchestration       | Airflow                                                               |
| Modeling            | XGBoost, CatBoost, SHAP, scikit-learn                                 |
| Model Tracking      | MLflow                                                                |
| API Layer           | FastAPI                                                               |
| Dashboards          | Streamlit, Plotly, GeoPandas                                          |
| Deployment          | Docker, AWS ECS                                                       |
| CI/CD               | GitHub Actions                                                        |
| Monitoring          | MLflow, Evidently AI, ZenML                                           |

## KPIs & Evaluation Metrics

| Component             | Metric                                                              |
|-----------------------|---------------------------------------------------------------------|
| Price Prediction      | MAE, RMSE                                                           |
| Recommendation Engine | Precision@K, Recall@K, Listing Diversity                            |
| Data Freshness        | % of listings updated weekly                                        |
| Model Drift           | Distribution shift, prediction deviation                            |
| System Health         | API latency, uptime, error rate                                     |
