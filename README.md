# SOLAR_irradiance


Solar Irradiance Prediction Using Meteorological Data

This project focuses on predicting solar irradiance using meteorological data from the HI-SEAS weather station. Solar irradiance is a key measure of how much energy from the sun reaches the Earth's surface, and is essential for applications like optimizing the use of solar panels. The project utilizes various feature extraction, selection, and machine learning techniques to predict solar radiation.

Dataset Overview

The dataset contains meteorological data collected between September and December 2016 from the HI-SEAS weather station. The data includes the following fields:

Solar radiation (watts per meter²)
Temperature (degrees Fahrenheit)
Humidity (percent)
Barometric pressure (Hg)
Wind direction (degrees)
Wind speed (miles per hour)
Sunrise/Sunset (Hawaii time)
Date and Time in UNIX time and yyyy-mm-dd format
The dataset captures conditions relevant to predicting solar radiation, which is the target variable in this project.

Key Project Steps


1. Data Wrangling
   
We began by processing the raw meteorological data:

Splitting Date & Time: Extracted day, month, year, seconds, and minutes to generate additional time-related features.
Feature Extraction: Extracted key features like rise hour and set minute for enhanced time-based analysis.
Dropping Irrelevant Features: Removed parent features after extraction to reduce dataset complexity and redundancy.
Target Creation: Isolated the solar radiation column as the target variable for predictions.

2. Feature Selection

To reduce dimensionality and improve model performance, we applied various feature selection techniques:

Correlation Matrix: Identified highly correlated features with solar radiation.
SelectKBest Method: Used statistical tests to select the top features relevant to the target variable.
Extra Tree Classifier: Applied a tree-based feature selection method to assess feature importance.

3. Feature Engineering

Feature engineering was carried out to transform the data and improve the model's predictive performance. The transformations included:

BoxCox Transformation: Applied to normalize skewed data.
Log Transformation: Used for reducing variance in the dataset.
MinMax Scaling: Scaled features to a specific range.
Standardization: Standardized the dataset to have a mean of 0 and a standard deviation of 1.

4. Data Preparation

After feature engineering, we prepared the data for modeling:

Train-Test Split: Divided the dataset into training and test sets to evaluate model performance.

5. Modeling

We applied machine learning models to predict solar irradiance:

XGBoost: The first model used for prediction, known for its robustness in handling tabular data.
Multilayer Perceptron (MLP): A neural network model was also trained to capture more complex patterns in the data.

6. Model Evaluation

We evaluated the performance of the models using common metrics like:

Mean Absolute Error (MAE)
Root Mean Square Error (RMSE)
R² Score
These metrics helped in assessing how well the models predicted solar irradiance on unseen test data.

Technologies Used

Programming Language: Python
Libraries:
Pandas, NumPy for data manipulation
Scikit-learn for machine learning models and feature selection
Seaborn, Matplotlib for data visualization
XGBoost for gradient boosting
TensorFlow/Keras for neural network implementation
