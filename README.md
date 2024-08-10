# Stock Price Prediction Using RNN, LSTM, and GRU

This project aims to predict Google's stock prices using three different types of recurrent neural networks: Simple RNN, LSTM, and GRU. The dataset includes Google's historical stock prices from January 1, 2018, to December 31, 2023.

## Table of Contents

- [Installation](#installation)
- [Data](#data)
- [Model Architecture](#model-architecture)
  - [Simple RNN](#simple-rnn)
  - [LSTM](#lstm)
  - [GRU](#gru)
- [Training](#training)
- [Evaluation](#evaluation)
- [Results](#results)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)

# Stock Price Prediction Using RNN, LSTM, and GRU

This project aims to predict Google's stock prices using three different types of recurrent neural networks: Simple RNN, LSTM, and GRU. The dataset includes Google's historical stock prices from January 1, 2018, to December 31, 2023.

## Data

The dataset consists of Google's historical stock prices downloaded using the `yfinance` API. The dataset includes the following columns:

- **Date**
- **Open**
- **High**
- **Low**
- **Close**
- **Adj Close**
- **Volume**

### Data Preparation

1. **Date Range**: The data ranges from January 1, 2018, to December 31, 2023.
2. **Training/Testing Split**: The dataset is split into 80% training data and 20% testing data.
3. **Feature Selection**: We use the `Open` price as the primary feature for training the models.
4. **Normalization**: The data is normalized using `MinMaxScaler` from `sklearn` to scale the prices between 0 and 1.

## Model Architecture

### Simple RNN

- **Layers**: 4 SimpleRNN layers with 50 units each.
- **Activation Function**: `relu`
- **Optimizer**: SGD with a learning rate of 0.01.
- **Loss Function**: Mean Squared Error (MSE)
- **Dropout**: 0.2 to prevent overfitting.

### LSTM

- **Layers**: 2 LSTM layers with 50 units each, followed by a Dense layer with 25 units.
- **Activation Function**: `tanh`
- **Optimizer**: Adam
- **Loss Function**: Mean Squared Error (MSE)

### GRU

- **Layers**: 4 GRU layers with 50 units each.
- **Activation Function**: `tanh`
- **Optimizer**: SGD with a learning rate of 0.01.
- **Loss Function**: Mean Squared Error (MSE)
- **Dropout**: 0.2 to prevent overfitting.

## Training

The models were trained on the training set with the following configurations:

- **Epochs**:
  - Simple RNN: 20
  - LSTM: 12
  - GRU: 20
- **Batch Size**:
  - Simple RNN: 2
  - LSTM: 1
  - GRU: 1

## Evaluation

The models were evaluated using the Mean Squared Error (MSE) and R-squared metrics on the test set. The results are as follows:

- **Simple RNN**:
  - MSE: 9.9552
  - R-squared: 0.9627
- **LSTM**:
  - MSE: 4.5034
  - R-squared: 0.9831
- **GRU**:
  - MSE: 18.5283
  - R-squared: 0.9305

## Results

- **RNN**: The Simple RNN performed decently but was outperformed by the LSTM.
- **LSTM**: The LSTM model achieved the best results with the lowest MSE and the highest R-squared.
- **GRU**: The GRU model performed the worst in terms of MSE and R-squared, but it is still a strong performer.

## Future Work

### Additional Features

To improve model performance, consider adding the following features:

1. **Date and Time Features**:
   - Day of the Week
   - Month of the Year
2. **Lagged Variables**:
   - Previous Days' Prices
   - Moving Averages
3. **External Factors**:
   - Economic Indicators
   - Events and Holidays
4. **Technical Indicators**:
   - Trading Volume
   - Volatility
   - RSI, MACD, Bollinger Bands
5. **Sentiment Analysis**:
   - News Sentiment
   - Social Media Trends

## Contributing

If you would like to contribute to this project, please fork the repository and submit a pull request.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.


## Installation

To run this project, you'll need Python 3.x and the following libraries:

- pandas
- numpy
- yfinance
- scikit-learn
- keras
- tensorflow
- matplotlib

You can install the required libraries using pip:

```bash
pip install pandas numpy yfinance scikit-learn keras tensorflow matplotlib

