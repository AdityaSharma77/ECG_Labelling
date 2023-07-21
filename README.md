ECG Data Analysis using Deep Learning LSTM Model
This repository contains code for detecting peaks from ECG data of rice/mice. The code incorporates a deep learning LSTM model using labelled peaks information to train the model. It aims to analyze ECG data and provide valuable insights for better decision-making.

#Requirements
To run the code, ensure you have the following libraries installed:

pandas
keras
scikit-learn
numpy
tensorflow

#Usage
1. Make sure to have the required libraries installed in your Python environment.

2. Place your ECG data in a CSV file, and ensure that the file contains the following columns: 'Raw/Voltage' and 'Time'.

3. Modify the code to specify the correct file name for your ECG data:
   
Replace "ecgfmob_044_3320pkcorrected.csv" with the name of your ECG data file
dataframe = read_csv("ecgfmob_044_3320pkcorrected.csv")[10000:]

Run the code to train the LSTM model on the provided ECG data:
model_output = ECG("ecgfmob_044_3320pkcorrected.csv")

The trained model will be saved to disk as 'model_output.json' and 'model_output.h5'.
To use the trained model for prediction on unlabelled data, replace "AA.csv" with the name of your unlabelled data file:
inputfile = read_csv("AA.csv")
The predictions on the unlabelled data will be appended to the 'Label' column of the CSV file.

#Additional Information
1. The 'Label' column in the CSV file will indicate the presence of peaks (1) or non-peaks (0) in the ECG data.

2.The code uses the LSTM model for its ability to capture long-term dependencies and patterns in sequential data.

3.The model is trained using softmax activation for the final layer to ensure the output ranges between 0 and 1.

4.The data is normalized using the Normalizer class to handle data with different scales effectively.

5.The code provides visualizations through Power BI to present data insights clearly and concisely.

Note
This code is intended for educational and demonstrational purposes and may require further optimization for specific use cases. It is essential to ensure the accuracy and appropriateness of the data before applying the model to real-world scenarios.
