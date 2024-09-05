# LAB: Deep Learning - Recurrent Neural Networks (RNNs)

![RNN](https://user-images.githubusercontent.com/970858/63474771-d6734700-c469-11e9-83bb-9429da563909.png)

## Introduction

In this LAB, we will work through a comprehensive Deep Learning workflow using a Recurrent Neural Network (RNN) to predict time series data. We will use a real dataset from Kaggle, the **"Air Quality Prediction Dataset,"** which contains hourly air quality records. Our goal is to predict the future concentration of a specific pollutant based on historical values using an RNN.

In this LAB, we will cover everything from data collection and preprocessing, to feature engineering, model training, evaluation, and comparison of different recurrent neural network techniques, including **LSTM** (Long Short-Term Memory) and **GRU** (Gated Recurrent Unit).

## Setup Instructions

To run the notebook and reproduce the results, follow these steps:

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

### Iteration 1: Data Load

We will load the **"Air Quality Prediction Dataset"** into a pandas DataFrame. This dataset contains hourly air quality records, with various features such as temperature, humidity, pressure, and concentrations of different gases.

- Import the necessary libraries: `pandas`, `zipfile`, `io`, and `requests`.
- Download and unzip the dataset.
- Load the `air_quality.csv` file into a pandas DataFrame.
- Display the first few rows to understand its structure.

### Iteration 2: Explore Data

Visualize the dataset to understand the distribution of pollutant concentrations and their relationship with other features.

- Import visualization libraries: `seaborn` and `matplotlib.pyplot`.
- Visualize the distribution of pollutant concentrations and scatter plots of features against concentrations.

### Iteration 3: Feature Selection and Preprocessing

#### 3.0 Feature Selection

Select the most relevant features that will be used as inputs for the RNN. This may include variables like previous hour gas concentrations, temperature, pressure, etc.

#### 3.1 Create Time Sequences

Convert the dataset into time sequences. Each RNN input should be a sequence of historical data, for example, a window of the last 24 hours.

- Create a function that generates sequences of length `T` (e.g., 24 hours) and their corresponding target value.

#### 3.2 Feature Normalization

Normalize the feature set to ensure that each feature contributes equally during the training process.

### Iteration 4: Build Recurrent Neural Network Models

In this iteration, you will create and compare **two recurrent neural network models** to predict the future concentration of a pollutant. One model will be a simple RNN, and the other will include more advanced techniques like LSTM or GRU.

#### 4.1: Build a Simple RNN

1. **Define the model architecture**:
   - **Input layer**: Specify the input shape based on the sequence length.
   - **Recurrent layer**: Add a simple RNN layer with an activation function like `tanh`.
   - **Output layer**: Use a linear activation function to predict the concentration.

2. **Compile the model**:
   - Use an appropriate optimizer (e.g., Adam).
   - Set the loss function to Mean Squared Error (MSE).
   - Include Mean Absolute Error (MAE) as a metric.

#### 4.2: Build an RNN with LSTM or GRU

1. **Define the model architecture**:
   - **Input layer**: Specify the input shape based on the sequence length.
   - **Recurrent layer**: Add an LSTM or GRU layer.
   - **Output layer**: Use a linear activation function to predict the concentration.

2. **Compile the model**:
   - Use an appropriate optimizer (e.g., Adam).
   - Set the loss function to Mean Squared Error (MSE).
   - Include Mean Absolute Error (MAE) as a metric.

---

### Iteration 5: Train Both Recurrent Neural Networks

Train **both recurrent neural network models** on the training data:

1. Train the simple RNN model using the following parameters:
   - Number of epochs: 100
   - Batch size: 32

2. Train the LSTM or GRU model using the same parameters:
   - Number of epochs: 100
   - Batch size: 32

---

### Iteration 6: Evaluate Both Models

Evaluate the performance of each model on the test data:

1. For the simple RNN model, calculate:
   - Mean Squared Error (MSE)
   - Mean Absolute Error (MAE)

2. For the LSTM or GRU model, calculate:
   - Mean Squared Error (MSE)
   - Mean Absolute Error (MAE)

Compare the results to see how the advanced techniques affect performance.

---

### Iteration 7: Visualize Training History

Plot and compare the training and validation loss for both models over epochs:

1. Create a plot for the simple RNN model showing:
   - Training loss
   - Validation loss

2. Create a plot for the LSTM or GRU model showing:
   - Training loss
   - Validation loss

Analyze the plots to diagnose the training process and observe differences.

---

### Iteration 8: Hyperparameter Tuning

Optimize both recurrent models by experimenting with different hyperparameters:

1. Tune the number of layers, units per layer, and dropout rates.
2. Use techniques such as **GridSearchCV** from `sklearn`, or perform manual tuning.

---

### Iteration 9: Final Model Evaluation

After hyperparameter tuning, evaluate the final models:

1. Print and compare the final Mean Squared Error (MSE) and Mean Absolute Error (MAE) for both models.
2. Plot and compare the training and validation loss over epochs for both final models.

---

## Bonus

### Compare Results with Other Models

Compare the performance of the recurrent neural network with other models such as ARIMA, Prophet, and SARIMA.

- Compare metrics such as MSE and R² to determine which model performs best.

## Submission

Once you have completed your analysis and visualizations, push your Jupyter notebook to your GitHub repository. Ensure that your final submission includes narratives explaining your visualizations and insights.

```bash
$ git add .
$ git commit -m "done"
$ git push origin main
```
