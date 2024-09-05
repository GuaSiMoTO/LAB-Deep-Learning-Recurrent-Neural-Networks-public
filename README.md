# LAB: Deep Learning - Recurrent Neural Networks (RNNs)

![RNN](https://user-images.githubusercontent.com/970858/63474771-d6734700-c469-11e9-83bb-9429da563909.png)

## Introduction

In this LAB, we will work through a comprehensive deep learning workflow using a Recurrent Neural Network (RNN) to predict stock prices. We will use historical stock price data from **Apple (AAPL)**, downloaded from Yahoo Finance using the `yfinance` library. Our goal is to predict future stock prices based on past data, comparing different types of recurrent neural networks, including **LSTM** (Long Short-Term Memory).

---

### Setup Instructions

1. **Clone the repository**:
    ```bash
    git clone https://github.com/your-username/LAB-Deep-Learning-RNN.git
    cd LAB-Deep-Learning-RNN
    ```

2. **Create a virtual environment and install the required packages**:
    ```bash
    pip install -r requirements.txt
    ```

3. **Start Jupyter Notebook**:
    ```bash
    jupyter notebook
    ```

---

### Iteration 1: Data Load

In this iteration, we will load **Apple's historical stock price data** using the `yfinance` library and store it in a pandas DataFrame.

- Download the stock price data from Yahoo Finance for Apple (AAPL) from January 2010 to January 2022.
- Load the data into a pandas DataFrame and display the first few rows to understand its structure.
- Use the 'Close' column (closing price) for the analysis.

---

### Iteration 2: Explore Data

Visualize the dataset to understand the price trends over time.

- Plot the stock prices over time to get a sense of the trend.
- Optionally, compute basic statistics such as mean and standard deviation of the stock prices.

---

### Iteration 3: Feature Selection and Preprocessing

#### 3.0 Feature Selection

Use the stock closing prices as the main feature for time-series prediction.

#### 3.1 Create Time Sequences

Convert the dataset into sequences of past data. For this lab, we will use the previous 60 days of prices to predict the next day's price.

- Create a function to generate sequences of length `T` (e.g., 60 days) and their corresponding target value.

#### 3.2 Feature Normalization

Normalize the feature set to ensure that each feature contributes equally during the training process.

---

### Iteration 4: Build Recurrent Neural Network Models

#### 4.1: Build a Simple RNN

Define and compile a simple RNN model to predict future stock prices.

#### 4.2: Build an LSTM Model

Define and compile a more advanced LSTM model.

---

### Iteration 5: Train Both Recurrent Neural Networks

Train both models using the same parameters and dataset.

---

### Iteration 6: Evaluate Both Models

Evaluate both models using the test dataset and calculate metrics like Mean Squared Error (MSE) and Mean Absolute Error (MAE).

---

### Iteration 7: Visualize Training History

Plot and compare the training history of both models.

---

### Iteration 8: Hyperparameter Tuning

Try different hyperparameters such as the number of layers, units per layer, and dropout rates to optimize both models.

---

### Iteration 9: Final Model Evaluation

Evaluate the final models and compare their performance after tuning.

---

## Bonus

### Compare Results with Other Models

Compare the performance of the RNN/LSTM models with traditional methods like ARIMA or Prophet.

---

### Submission

Once you have completed your analysis and visualizations, push your Jupyter notebook to your GitHub repository.

```bash
$ git add .
$ git commit -m "done"
$ git push origin main
```
