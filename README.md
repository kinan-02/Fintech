# Fintech

This study explores the application of advanced Deep Learning models, specifically Long Short-Term Memory (LSTM) networks and Transformer models, to predict Bitcoin's Close prices on a minute-level basis. Leveraging the temporal dependencies captured by LSTMs and the attention mechanisms of Transformers, the research integrates data from various assets including crude oil, Ethereum (ETH), etc. To improve prediction accuracy. We present three different models, with our best model standing out by achieving an impressive MSE reaching 789.67 on the Test data. Our approach holds substantial promise for improving predictive modeling in bitcoin price prediction.

## Table of Contents

- [Installation](#installation)
- [Prerequisites](#Prerequisites)
- [How to Get The Data](#How-to-Get-The-Data)
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

   Use the `CryptoBarsRequest` class (provided by the Alpaca library) to retrieve cryptocurrency data. Make sure to use the relevant symbols. Here is an example:

   ```python
   from alpaca.data.requests import CryptoBarsRequest
   from alpaca.data.historical import CryptoHistoricalDataClient

   api_key = "YOUR_API_KEY"
   secret_key = "YOUR_SECRET_KEY"
   client = CryptoHistoricalDataClient(api_key, secret_key)

   crypto_request_params = CryptoBarsRequest(
       symbol_or_symbols=["BTC/USD", "ETH/USD"],  # Replace with the relevant symbols
       timeframe="1D"  # Daily data
   )

   crypto_data = client.get_crypto_bars(crypto_request_params)
   ```

4. **Get Stock and Natural Resources Data**:

   Use the `StockBarsRequest` class to retrieve stock and natural resources data. Again, specify the relevant symbols:

   ```python
   from alpaca.data.requests import StockBarsRequest
   from alpaca.data.historical import StockHistoricalDataClient

   client = StockHistoricalDataClient(api_key, secret_key)

   stock_request_params = StockBarsRequest(
       symbol_or_symbols=["AAPL", "MSFT", "XOM"],  # Replace with the relevant symbols
       timeframe="1D"  # Daily data
   )

   stock_data = client.get_stock_bars(stock_request_params)
   ```

Make sure to replace `"YOUR_API_KEY"` and `"YOUR_SECRET_KEY"` with your actual Alpaca API credentials, and specify the correct symbols for the assets you want to retrieve.

You can further modify the timeframe and other parameters according to your needs.

---

This section provides clear instructions on how users can install the Alpaca library, obtain their API key, and then use the provided classes to retrieve both cryptocurrency and stock/natural resources data. Feel free to customize the examples as needed for your specific project.
