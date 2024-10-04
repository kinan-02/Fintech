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
NOTE : the `final_data.parquet` in the `data/new_data/` is the train data and the `test_data.parquet` in the `data/test_data/` is the test data
You have two options to run the project: training the model from scratch and then evaluating it, or using the pre-trained model directly for evaluation.

### Option 1: Train and Evaluate the Models

1. **Train the Models**:
 - **Run the Missing Data Script**:

   Open and run the Jupyter Notebook `join_data.ipynb` to handle the missing values

   - `--train`: This flag indicates that you want to train the model.
   - `--config config/train_config.json`: This specifies the configuration file that contains the training parameters (e.g., learning rate, epochs, dataset path).

2. **Evaluate the Model**:

   After training, you can evaluate the trained model using:

   ```sh
   python main.py --eval --config config/eval_config.json
   ```

   - `--eval`: This flag indicates that you want to evaluate the model.
   - `--config config/eval_config.json`: This specifies the evaluation parameters (e.g., validation dataset path, model checkpoint).

### Option 2: Evaluate Using a Pre-Trained Model

If you do not want to train the model and prefer to use the pre-trained model for evaluation, use the following command:

```sh
python main.py --eval --pretrained_model_path path/to/pretrained_model.pth --config config/eval_config.json
```

- `--eval`: This flag indicates that you want to evaluate the model.
- `--pretrained_model_path path/to/pretrained_model.pth`: Provide the path to the pre-trained model file (e.g., `transformer_model.pth`).
- `--config config/eval_config.json`: This specifies the configuration for evaluation.

### Example Commands

1. **Training from Scratch**:

   ```sh
   python main.py --train --config config/train_config.json
   ```

2. **Evaluating the Trained Model**:

   ```sh
   python main.py --eval --config config/eval_config.json
   ```

3. **Evaluating Using a Pre-Trained Model**:

   ```sh
   python main.py --eval --pretrained_model_path pretrained_models/transformer_model.pth --config config/eval_config.json
   ```

---

This "How to Run" section provides users with clear instructions for both training and evaluating the model, as well as the option to only evaluate a pre-trained model. Replace paths like `path/to/pretrained_model.pth` and `config/train_config.json` with the appropriate file paths in your project.
   

