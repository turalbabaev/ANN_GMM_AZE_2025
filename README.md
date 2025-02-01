# ANN_GMM_AZE_2025
This repository contains ANN-based ground motion model developed for Azerbaijan.

ANN-based Ground Motion Model (GMM) for Predicting PGA
This repository contains a machine learning-based ground motion model for Azerbaijan (Artificial Neural Network, ANN) developed for predicting Peak Ground Acceleration (PGA) from earthquake magnitude (M) and hypocentral distance (R). The model is trained using real seismic data and can be used by users to predict the PGA values for any given earthquake parameters.

Contents:
ann_model.h5 - The trained ANN model file.
scaler.pkl - The scaler used to normalize inputs before prediction.
ANN_single_prediction.ipynb - A Jupyter notebook that loads the model and scaler, takes user input, and predicts PGA for a single earthquake record.
ANN_multiple_prediction.ipynb - A Jupyter notebook that processes a batch of data from a CSV file, calculates hypocentral distance, and predicts PGA for multiple earthquake records.
LICENSE - The license file for the repository.
.gitignore - File to ignore unnecessary files during version control.
Requirements:
To use this repository, you need Python installed, along with the following libraries:

tensorflow
numpy
pandas
joblib
To install the required packages, you can run the following command:

bash
Copy
Edit
pip install -r requirements.txt
Usage:
1. Predicting PGA for a Single Earthquake:
To use the ANN_single_prediction.ipynb notebook for predicting the PGA value for a single set of earthquake parameters (magnitude and distance), follow these steps:

Download or Clone the Repository:

Clone or download this repository to your local machine.
Prepare the Environment:

Make sure you have Python installed and the required libraries listed above.
Open the Jupyter Notebook: Run the ANN_single_prediction.ipynb

Enter User Inputs:

When prompted, enter the following details:
Earthquake magnitude (M): Local magnitude of the earthquake.
Depth (h): Depth of the earthquake (in km).
Distance (d): Distance from the earthquake epicenter to the site (in km).

Output: The notebook will output the predicted PGA (in cm/s²) based on the provided inputs.

2. Predicting PGA for Multiple Earthquakes (Batch Processing)
To use the ANN_multiple_prediction.ipynb notebook for predicting PGAs for multiple earthquake records stored in a CSV file, follow these steps:

Prepare the Input CSV File:

Your CSV file should have the following columns:
M: Local magnitude (e.g., 5.5, 6.0, etc.).
h: Depth of the earthquake (in km).
d: Distance from the earthquake epicenter to the site (in km).

Example:

M	h	d
5.5	10	50
6.0	15	40
4.8	20	30

Open the Jupyter Notebook: ANN_multiple_prediction.ipynb

Provide the Input File Name:

When prompted, enter the whole name of your CSV file (with .csv extension). 

For example: earthquake_data.csv

Output: The script will generate a new CSV file with the suffix _pga.csv containing the same data as the input, but with two new columns:
R: The calculated hypocentral distance (in km).
PGA: The predicted Peak Ground Acceleration (in cm/s²).

For example, if your input file is earthquake_data.csv, the output will be earthquake_data_pga.csv.

Note that, the Jupyter Notebooks, ann model (.h5) and scaler (.pkl) and the input .csv files are all must be in the same folder.

How the Model Works:
Input Features: The model uses two input features for predicting PGA:

Earthquake magnitude (M)
Hypocentral distance (R), which is calculated as R = sqrt (h^2+d^2),
​
where h is the depth (in km) and d is the distance from the earthquake to the site (in km).

ANN Model: The ANN model was trained on real seismic data to predict the log of PGA, which is then transformed back to obtain the final PGA value in cm/s².

License:
This repository is licensed under the Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License (CC BY-NC-ND 4.0). You may freely download and share the files, but you cannot modify, redistribute, or use them for commercial purposes.

Acknowledgements:
The model is built on real seismic data and utilizes TensorFlow and other Python libraries.
Special thanks to the open-source community for their contributions to seismic data analysis and machine learning.
