TOTAL POWER GENERATION PREDICTION MODEL:

This project is a machine learning model designed to predict total power generation based on a time series dataset. The model uses a Long Short-Term Memory (LSTM) neural network to predict power generation and identify outliers through residual analysis. Developed in Google Colab, this project leverages Python's deep learning and data analysis libraries.

DATASET:

The dataset includes features:
1. Plant Day Gen (KWh): Daily power generation by the plant
2. Inverter Day Gen (KWh): Daily power generation by the inverter
3. Diff (Plant-Inverter) Day Gen (KWh): Difference in daily generation between the plant and inverter
4. Total Gen (KWh): Total daily power generation
5. Controlled PR (%) and Uncontrolled PR (%): Performance ratios under different controls
The dataset should be in CSV format, with a 'Date' column that will be converted to a datetime format and set as the index.

PROJECT STRUCTURE:

1. Data Processing:

* Missing values are forward-filled to handle gaps.
* Data normalization is performed using MinMaxScaler.

2. Modeling:

* The time-series data is split into sequences using a window size (time_steps).
* The LSTM model has two LSTM layers and one Dense layer with 6 outputs (one for each feature).

3. Training:

* The model is compiled with the Adam optimizer and a mean squared error loss function.
* Training is conducted over 100 epochs with an 80-20 validation split.

4. Evaluation and Prediction:
 
* Predictions are made on test data, scaled back to original values.
* The results for the Total Gen (KWh) column are compared with actual values to evaluate model accuracy.

5. Residual Analysis and Outlier Detection:

* Residuals (difference between actual and predicted values) are calculated.
* Z-scores of residuals are used to identify outliers beyond a specified threshold (3 standard deviations from the mean).
* The results include visualization of residuals and outliers.

VISUALIZATIONS:

1. Actual vs. Predicted Power Generation: Shows the predicted values against actual total power generation across the dataset.
2. Residuals Plot: Displays residuals with thresholds indicating significant deviations.
3. Outliers Plot: Highlights data points identified as outliers in the residual analysis.

REQUIREMENTS:

The project requires the following Python libraries:
1. numpy
2. pandas
3. sklearn
4. keras
5. matplotlib
6. google.colab
These libraries can be installed using pip install -r requirements.txt.

HOW TO USE:

1. Upload Dataset: Use Google Colab’s file upload functionality to upload dataset.csv.
2. Run the Notebook: Execute the code cells in sequence to preprocess data, train the model, and visualize results.
3. View Results: Evaluate model performance through the plots generated in the notebook.

COLAB VIEW LINK:

https://colab.research.google.com/drive/1eHnsSkOqrz6ans1-YnitOwqYsAXo8a3q?usp=sharing


