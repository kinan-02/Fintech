# Fintech

This study explores the application of advanced Deep Learning models, specifically Long Short-Term Memory (LSTM) networks and Transformer models, to predict Bitcoin's Close prices on a minute-level basis. Leveraging the temporal dependencies captured by LSTMs and the attention mechanisms of Transformers, the research integrates data from various assets including crude oil, Ethereum (ETH), etc. To improve prediction accuracy. We present three different models, with our best model standing out by achieving an impressive MSE reaching 789.67 on the Test data. Our approach holds substantial promise for improving predictive modeling in bitcoin price prediction.

## Table of Contents

- [Installation](#installation)
- [Prerequisites](#Prerequisites)
- [How to Get The Data](#How-to-Get-The-Data)
- [How to deal with the missing data](#How-to-Deal-With-The-Missing-Data)
- [How to Join The Data](#How-to-Join-The-Data)
- [How to Run](#how-to-run)

## Installation

1. **Clone the Repository**:

   Clone this repository to your local machine using:

   ```sh
   git clone https://github.com/kinan-02/Fintech.git
   cd Fintech
   
## Prerequisites

make sure that you have jupyter or google colab (prefered google colab) 

## How to Get The Data
To get the required data for this project, follow the steps below:

1. **Install the Alpaca Library**:

   First, you need to install the Alpaca library. You can do this using `pip`:

   ```sh
   pip install alpaca-trade-api
   ```

2. **Get Your API Key**:

   - Go to the [Alpaca website](https://alpaca.markets/) and sign up for an account if you don't have one.
   - Once signed in, generate an API key, which will be needed to access the data.

3. **Get Cryptocurrency Data**:

   Use the `CryptoBarsRequest` class (provided by the Alpaca library) to retrieve cryptocurrency data. Make sure to use the relevant symbols. 

4. **Get Stock and Natural Resources Data**:

   Use the `StockBarsRequest` class to retrieve stock and natural resources data.

Notes : 
- all of the mentioned above (code) and also the data itself , is in the data folder
- you should download the data you already got (to use it after that again).
  
## How to Deal With The Missing Data
To handle missing data in the dataset, follow these steps:

1. **Install the Pandas Library**:

   You will need `pandas` to manage and process the data. Install it using:

   ```sh
   pip install pandas
   ```

2. **Upload the Downloaded Data**:

   Load the data that you have already downloaded using Pandas. You can do this in your script or Jupyter Notebook


3. **Run the Missing Data Script**:

   Open and run the Jupyter Notebook `filling_missing_values.ipynb` to handle the missing values
   
Note : check out the last cells, you should rename the files as you need (depends on the data you have)

## How to Join The Data

1. **Upload the Downloaded Data**:

   Load the data that you have already downloaded using Pandas. You can do this in your script or Jupyter Notebook
2. **Run the Missing Data Script**:

   Open and run the Jupyter Notebook `join_data.ipynb` to handle the missing values
   
Note : check out the last cells, you should rename the files as you need (depends on the data you have)

## How to Run
NOTE : the `final_data.parquet` in the `data/new_data/` is the train data and the `test_data.parquet` in the `data/test_data/` is the test data.

**You have two options to run the project:**

training the model from scratch and then evaluating it, or using the pre-trained model (`Trained_Models/`) directly for evaluation.

### Option 1: Train and Evaluate the Models
**Train and Evaluate the Model**:
   
Note that we have 5 different models that we used all the models are in `Models/` choose the model that you want to run and the code file that is relevant for example of you chose to run the baseline model run the `Models/LSTM_Model.ipynb` file.

This process will handle the training and evaluating the model with the hyperparameters that we chose.

Note : if you want to run the code in google colab platform you should upload the `final_data.parquet` in the `data/new_data/` and the `test_data.parquet` in the `data/test_data/`.


### Option 2: Evaluate Using a Pre-Trained Model

If you do not want to train the model and prefer to use the pre-trained models for evaluation upload all the files from `Trained_Models/` and run `eval_models.ipynb` file.

 
---
**This completes the instructions for running the notebooks and processing the data for our project. We encourage you to explore the final results, consider potential improvements, and possibly extend the project with your ideas.
Thank you for following through with our project workflow!**
