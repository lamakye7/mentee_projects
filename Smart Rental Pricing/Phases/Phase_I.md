# Smart Rental Pricing: Data Gathering and Storage

## Project Overview

This mentorship project focuses on building a comprehensive, end-to-end data pipeline system to collect, process, and analyze real estate rental and sales listings from online sources.

The system will scrape property data from websites, clean and structure it, store it in a database, and serve it through a robust API that enables advanced pricing analysis and market insights.

By completing this project, the mentee will gain practical experience across web scraping, data engineering, backend development, DevOps, and software engineering best practices.

## Project Goal

To develop a data-driven system that automates the collection, cleaning, storage, and serving of real estate listings, enabling:

- Accurate market insights
- Fairer rental and sales pricing
- Better decision-making for renters, buyers, and landlords
- A foundation for future analytics like price prediction and geographic trends

## Why This Project Matters

- **Real-World Impact**: Builds a tool with meaningful social and economic benefits
- **Full-Stack Experience**: Combines scraping, backend, API, DevOps, and analytics
- **Career-Ready Skills**: Aligns with core competencies demanded in software, data, and ML engineering roles
- **Foundation for ML/AI** → Sets the stage for integrating machine learning price prediction models and dashboards

---
## Learning Objectives

Mentee will gain hands-on experience with:

### Web Scraping & Automation
- Dynamic website interaction with Selenium
- Handling pagination, retries, and error resilience

### Data Engineering
- Building robust ETL pipelines
- Data cleaning, normalization, and feature engineering

### API Development
- Designing RESTful APIs with FastAPI
- Database interactions using SQLAlchemy
- Versioning, authentication, and documentation

### DevOps Practices
- Containerization with Docker
- Environment management with Dynaconf
- Logging, monitoring, and deployments

### Software Engineering Best Practices
- Modular, scalable architecture
- Test-driven development with Pytest
- Version control with Git and CI/CD readiness

---
## Project Components

### Data Collection Module
- Web scraper to extract property listings
- Pagination and dynamic loading handling
- Error handling and retry mechanisms

### Data Cleaning Pipeline
- Normalizing location, price, and size fields
- Feature extraction (e.g., number of bedrooms, amenities)
- Outlier detection and correction

### Database Layer
- Schema design for storing listings
- Alembic migrations for schema evolution
- Optimized queries for filtering and analytics

### API Service
- REST endpoints to access listings
- Query parameters for filtering by price, location, date, etc.
- Rate limiting and optional authentication

### Deployment Configuration
- Docker + docker-compose setup for local/production environments
- Environment-specific configurations
- Logging and resource management

## Expected Deliverables

- Fully automated data pipeline to collect real estate listings
- Cleaned and structured dataset saved in a relational database
- RESTful API with filtering and analytics endpoints
- Docker setup for reproducible deployment
- Well-documented codebase, API docs, and deployment instructions

---
## Technologies & Tools

| Area | Tools |
|------|-------|
| Programming | Python |
| Scraping | Selenium |
| API Development | FastAPI |
| Database | SQLAlchemy, PostgreSQL / SQLite |
| Migrations | Alembic |
| Containerization | Docker, docker-compose |
| Logging | Loguru |
| Config Management | Dynaconf |
| Data Validation | Pydantic |
| Testing | Pytest |
| Exploration | Jupyter Notebooks |

---
## Proposed Timeline (Flexible)

| Phase | Duration |
|-------|----------|
| Requirements & Design | 1 week |
| Scraper Development | 2 weeks |
| Data Cleaning Pipeline | 1 week |
| Database + API Layer | 2 weeks |
| Dockerization + Docs | 1 week |