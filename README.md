# Watch_it_movie_revenue_prediction
Machine learning project for predicting movie revenue categories
WATCH-IT: MOVIE REVENUE CATEGORY PREDICTION

## Project Overview
This project focuses on developing a machine learning classification model to predict the revenue category of movies for Watch-It, a subscription-based streaming service.
The project uses historical movie information and performance-related features to classify movies into two revenue categories: High Revenue and Low Revenue.
The analysis and modelling process involves data exploration, data cleaning, feature engineering, data visualization, model development, evaluation and prediction.
The ultimate goal is to develop a reliable predictive model that can help Watch-It make better-informed decisions when selecting movies for licensing and content acquisition.

## Problem Statement
Watch-It operates in a competitive streaming industry where selecting the right movies is important for business performance and revenue generation.
However, deciding which movies are likely to generate high revenue can be challenging when decisions are based only on assumptions or historical observations.
Licensing movies that generate low revenue may lead to inefficient use of financial resources, while failing to identify potentially successful movies may result in missed business opportunities.
Therefore, Watch-It needs a data-driven approach that can use available movie information to predict whether a movie is likely to fall into the High Revenue or Low Revenue category.
This project addresses that challenge by applying machine learning classification techniques to historical movie data.

## Project Objectives
The main objective is to develop a machine learning model that predicts movie revenue categories.
The specific objectives are to:
1. Explore and understand the available movie dataset.
2. Identify and handle missing values, inconsistent data and other data quality issues.
3. Perform exploratory data analysis to identify patterns, distributions and relationships among movie features.
4. Transform and prepare the data for machine learning.
5. Develop and compare different classification models.
6. Evaluate model performance using appropriate classification metrics.
7. Select the best-performing model for making predictions on the test dataset.
8. Generate a final submission file containing movie titles and their predicted revenue categories.

## Dataset Description
The project uses three main files:
train.csv: Contains historical movie records and the target variable, "revenue_category".
test.csv: Contains movie records for which revenue categories must be predicted.
sample_submission.csv: Provides the required structure for the final prediction file.

The dataset contains movie-related information, including:
- Movie titles
- Countries and languages
- Genres
- Release dates and running time
- User votes and comments
- Likes, dislikes and overall views
- IMDb, Rotten Tomatoes and Metacritic ratings
- Awards and nominations
- Title adaptation information
The target variable is "revenue_category", which has two possible classes:
- High
- Low

## Project Methodology and Workflow
The project followed a systematic machine learning workflow.

Step 1: Data Loading and Initial Inspection
The training dataset, testing dataset and sample submission file were loaded into the Jupyter Notebook using Python and Pandas.
The datasets were inspected to understand their dimensions, column names, data types and general structure.

Step 2: Data Cleaning and Preprocessing
The datasets were examined for missing values, duplicate records and inconsistencies.
The following preprocessing activities were performed:

- Missing categorical values were handled using the mode.
- Missing numerical values were handled using the median.
- Missing movie titles were replaced with "Unknown".
- Duplicate records were checked.
- Numerical columns were converted into appropriate numeric formats.
- Date columns were converted into datetime format.

These activities helped improve data quality and prepare the datasets for analysis.

Step 3: Exploratory Data Analysis (EDA)

Exploratory Data Analysis was conducted to understand the characteristics and relationships within the dataset.

The analysis included:

- Histograms to examine numerical distributions.
- Box plots to identify potential outliers.
- Correlation heat maps to examine relationships between numerical variables.
- Comparisons of movie performance indicators such as likes and overall views.
- Analysis of the distribution of High and Low revenue categories.

The target variable was reasonably balanced, with:

- High Revenue: 1,221 records (50.9%).
- Low Revenue: 1,179 records (49.1%).

The findings helped establish a better understanding of the data before modelling.

Step 4: Feature Engineering

Feature engineering was performed to convert the available movie information into useful machine learning features.

The process included:

- Cleaning and encoding country information.
- Splitting and encoding movie genres.
- Processing and encoding language information.
- Converting censor ratings into dummy variables.
- Converting Boolean title adaptation values into numerical values.
- Extracting release years from movie release dates.
- Extracting DVD release years.
- Removing original date columns after extracting useful information.

The movie title was retained separately for the final submission and excluded from the model features.

Step 5: Feature Selection and Dataset Preparation

The prepared datasets were examined to identify features that would not contribute useful information to the model.

The following activities were performed:

- Checking for remaining object data types.
- Checking for missing and infinite values.
- Removing constant features.
- Identifying and removing duplicate features.
- Ensuring that training and testing datasets had matching feature columns.

After feature preparation, the final datasets contained 234 features.

Step 6: Splitting the Training Data

The training dataset was divided into training and validation sets using an 80:20 split.

The split was performed using "train_test_split", with a random state of 42 and stratification based on the target variable.

The resulting datasets were:

- Training set: 1,920 records.
- Validation set: 480 records.
- Test set: 600 records.

Feature scaling using StandardScaler was applied for Logistic Regression, while the tree-based models used the prepared unscaled features.

Step 7: Model Development

Three classification algorithms were developed and trained:

1. Logistic Regression

This model was used as a classification approach to establish a baseline and examine how well a linear classification method could predict movie revenue categories.

2. Decision Tree Classifier

A Decision Tree model was developed to identify patterns and decision rules within the movie features.

3. Random Forest Classifier

A Random Forest model was trained using multiple decision trees to improve predictive performance and provide a more robust classification approach.

Step 8: Model Evaluation and Comparison

The models were evaluated using validation accuracy and other classification metrics, including precision, recall and F1-score.

The validation accuracy results were:

Model| Validation Accuracy
Logistic Regression| 87.29%
Decision Tree| 82.50%
Random Forest| 87.50%

The Random Forest model achieved the highest validation accuracy of 87.50%.

It was therefore selected as the best-performing model among the three evaluated models.

Step 9: Final Model Selection

Random Forest was selected for final prediction because it achieved the highest validation accuracy.

Its classification report showed balanced performance across the two revenue categories.

The confusion matrix and classification report were also examined to understand the model's classification performance.

Step 10: Prediction on the Test Dataset

After selecting the best-performing model, the Random Forest classifier was used to predict revenue categories for all 600 records in the test dataset.

The predictions were converted into their corresponding category labels:

- High
- Low

The original movie titles were restored and combined with the predicted revenue categories.

Step 11: Final Submission File Generation

A final submission DataFrame was created containing exactly two columns:

1. "title"
2. "revenue_category"

The resulting file was saved as:

"submissions.csv"

The final file contains 600 movie records and is structured according to the required submission format.

## Tools and Technologies Used
The following tools and Python libraries were used throughout the project:
- Python: Main programming language.
- Jupyter Notebook: Development and documentation environment.
- Pandas: Data loading, manipulation and cleaning.
- NumPy: Numerical operations.
- Matplotlib: Data visualization.
- Seaborn: Statistical data visualization.
- Scikit-learn: Data preprocessing, model training, validation and evaluation.

## Business Value of the Project
The developed model provides a data-driven approach that can support Watch-It's content acquisition and licensing decisions.
By predicting movie revenue categories, the model can help management:
- Identify movies with potentially high revenue performance.
- Support informed movie licensing decisions.
- Reduce reliance on subjective assumptions.
- Improve the use of available movie data.
- Support strategic content selection and planning.
However, the predictions are estimates based on historical data and should be considered alongside other business factors when making actual licensing decisions.

## Conclusion
This project demonstrates the application of machine learning in solving a business classification problem within the streaming entertainment industry.
Through systematic data cleaning, exploratory data analysis, feature engineering, model development and evaluation, a Random Forest classifier was identified as the best-performing model among the three models tested.
The selected model achieved a validation accuracy of 87.50% and was used to predict the revenue categories of 600 movies in the test dataset.
The project provided practical experience in the complete machine learning workflow, from understanding a business problem to developing a predictive solution and generating a final submission file.

Project Outcome: A completed movie revenue category prediction workflow with a trained classification model and a final CSV file containing 600 predictions.
