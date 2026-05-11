# IBM Data Science Capstone - SpaceX Falcon 9 Landing Prediction

> IBM Data Science Capstone Project · Python · Data Analysis · Machine Learning · Dash · Folium

This repository contains my IBM Data Science Capstone project, focused on predicting whether the first stage of a SpaceX Falcon 9 rocket launch will land successfully.

The project follows a complete data science workflow, starting from data collection and cleaning, then moving into exploratory data analysis, SQL analysis, interactive visualisation, dashboard development, and machine learning model comparison.

The business context behind the project is simple: SpaceX can reduce launch costs because the Falcon 9 first stage can be reused after a successful landing. By predicting whether the first stage will land successfully, the analysis can help estimate launch risk and support cost-based decision-making for companies competing in the commercial space launch market.

---

## What This Project Does

* Collects historical SpaceX launch data through the SpaceX REST API
* Scrapes Falcon 9 and Falcon Heavy launch records from Wikipedia using BeautifulSoup
* Cleans and prepares launch data for analysis and modelling
* Performs exploratory data analysis using Pandas, Matplotlib, Seaborn, and SQL
* Analyses launch outcomes by site, orbit, payload mass, booster version, and flight number
* Builds an interactive Folium map to study launch site locations and geographical patterns
* Creates an interactive Plotly Dash dashboard for launch success analysis
* Trains and compares multiple machine learning models to predict first stage landing success
* Uses cross-validation and hyperparameter tuning to evaluate model performance

---

## Project Objective

The main objective of this capstone was to build a machine learning pipeline that predicts whether the Falcon 9 first stage will successfully land after launch.

This involved answering questions such as:

* Which launch sites have the highest success rates?
* Does payload mass affect landing success?
* Are certain orbit types more likely to result in successful landings?
* Does launch experience improve over time?
* Which machine learning model performs best for this classification problem?

---

## Repository Structure

| File                                                 | Purpose                                                                                                                                                    |
| ---------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `jupyter-labs-spacex-data-collection-api.ipynb`      | Collects SpaceX launch data from the SpaceX API and extracts key launch, booster, payload, orbit, and landing information.                                 |
| `jupyter-labs-webscraping.ipynb`                     | Scrapes Falcon 9 and Falcon Heavy launch records from Wikipedia using BeautifulSoup and converts the launch table into a structured dataset.               |
| `labs-jupyter-spacex-Data wrangling.ipynb`           | Cleans the dataset, handles missing values, prepares the landing outcome column, and creates the classification label.                                     |
| `jupyter-labs-eda-sql-coursera_sqllite.ipynb`        | Performs SQL-based exploratory analysis on the SpaceX dataset using SQLite queries.                                                                        |
| `edadataviz.ipynb`                                   | Performs visual exploratory data analysis and feature engineering using Pandas, Matplotlib, and Seaborn.                                                   |
| `lab_jupyter_launch_site_location.ipynb`             | Builds interactive Folium maps to analyse launch site locations, success and failure markers, and proximity to coastlines, highways, railways, and cities. |
| `spacex-dash-app.py`                                 | Contains the Plotly Dash app for interactive launch success analysis by site and payload range.                                                            |
| `SpaceX_Machine Learning Prediction_Part_5.ipynb`    | Trains and evaluates machine learning models for predicting Falcon 9 first stage landing success.                                                          |
| `plotlyfull.png`, `plotlygraph.png`, `plotlypie.png` | Screenshots of the interactive visualisations and dashboard outputs.                                                                                       |

---

## Data Collection

The project uses two main data sources.

First, launch data is collected from the SpaceX API. This includes details such as rocket version, launch site, payload mass, orbit, landing outcome, booster reuse, number of flights, grid fins, landing legs, and landing pad.

Second, historical Falcon 9 and Falcon Heavy launch records are scraped from Wikipedia. This adds another source of structured launch information and helps reinforce the analysis with a wider historical view of SpaceX launches.

The collected data is then converted into Pandas DataFrames and cleaned for later analysis.

---

## Data Wrangling and Feature Engineering

The raw launch data required several preparation steps before it could be used for analysis and machine learning.

Key preparation steps included:

* Selecting Falcon 9 launch records
* Extracting booster, payload, orbit, launch site, and core information
* Handling missing payload mass values
* Creating a binary landing outcome label
* Encoding launch outcomes into a target variable called `Class`
* Preparing feature columns for supervised machine learning
* Standardising the feature set before model training

This stage was important because the quality of the final prediction model depends heavily on how clearly the landing success label and input features are prepared.

---

## Exploratory Data Analysis

The EDA stage explored the relationship between launch success and several important variables.

The analysis looked at:

* Flight number and landing outcome
* Payload mass and landing outcome
* Launch site success rates
* Orbit type and mission outcome
* Booster version and launch performance
* Yearly launch success trends
* Relationship between payload mass, orbit, and booster reuse

A key pattern from the visual analysis was that launch success improved over time as SpaceX gained more flight experience. The project also showed that launch site, orbit type, and payload mass can all influence the likelihood of a successful first stage landing.

---

## SQL Analysis

The SQL notebook uses SQLite to query the SpaceX dataset and answer structured analysis questions.

This section includes queries for:

* Unique launch sites
* Launch records from specific sites
* Payload mass ranges
* Booster versions
* Successful and failed mission outcomes
* Launches by date and mission type

This part of the project demonstrates how SQL can be used alongside Python to explore data in a more structured and business-friendly way.

---

## Interactive Map Analysis

The Folium notebook builds an interactive map of SpaceX launch sites.

The map analysis includes:

* Marking all launch sites by latitude and longitude
* Adding success and failure markers for launch outcomes
* Using marker clusters to show launch density
* Measuring distance from launch sites to coastlines, railways, highways, and nearby cities

This analysis helped show that launch site geography matters. SpaceX launch sites are located close to coastlines, which supports safer launch trajectories and recovery operations.

---

## Interactive Dashboard

The repository includes a Plotly Dash app that allows users to explore SpaceX launch outcomes interactively.

The dashboard includes:

* A launch site dropdown filter
* A pie chart showing launch success distribution
* A payload range slider
* A scatter plot showing the relationship between payload mass and launch success
* Booster version category colouring for deeper comparison

The dashboard makes the analysis easier to explore without needing to run notebook cells manually.

---

## Machine Learning

The final part of the project builds and evaluates machine learning models to predict whether the Falcon 9 first stage will land successfully.

The machine learning workflow includes:

* Creating the target label
* Standardising the input features
* Splitting the data into training and test sets
* Training multiple classification models
* Using `GridSearchCV` for hyperparameter tuning
* Evaluating models using test accuracy and confusion matrices

The models tested include:

* Logistic Regression
* Support Vector Machine
* Decision Tree Classifier
* K-Nearest Neighbours

The Support Vector Machine model achieved strong performance after hyperparameter tuning, with a cross-validation accuracy of around 84.8% and a test accuracy of around 83.3% in the notebook.

---

## Tech Stack

**Languages and Core Tools:** Python, SQL, Jupyter Notebook

**Data Analysis:** Pandas, NumPy

**Visualisation:** Matplotlib, Seaborn, Plotly Express

**Interactive Dashboard:** Dash, Plotly

**Geospatial Analysis:** Folium

**Web Scraping:** BeautifulSoup, Requests

**Machine Learning:** scikit-learn, Logistic Regression, SVM, Decision Tree, KNN, GridSearchCV

**Database:** SQLite

---

## Key Skills Demonstrated

* End-to-end data science workflow
* API data collection
* Web scraping and HTML table parsing
* Data cleaning and feature engineering
* Exploratory data analysis
* SQL querying
* Interactive dashboard development
* Geospatial visual analytics
* Supervised machine learning classification
* Hyperparameter tuning and model comparison
* Communicating technical findings through visualisations

---

## Key Takeaways

This project shows how a real-world prediction problem can be approached using the full data science process.

Rather than only training a model, the project covers the full journey from raw data collection to interactive analysis and final machine learning evaluation. It also shows how different tools can work together in one workflow: APIs for data collection, BeautifulSoup for web scraping, SQL for structured querying, Folium for geospatial analysis, Dash for interactive dashboards, and scikit-learn for predictive modelling.

The final result is a portfolio-ready project that demonstrates practical data analysis, visualisation, and machine learning skills using a real business problem from the commercial space industry.

---

## Project Status

This project is complete as part of the IBM Data Science Capstone. The repository has been organised as a portfolio project to show the full data science workflow from collection to prediction.

---

## Author

**Ibrar Bhatti**
GitHub: [ibrawr](https://github.com/ibrawr)
