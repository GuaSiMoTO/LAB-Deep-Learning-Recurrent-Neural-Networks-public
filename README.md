# LAB: Deep Learning - Recurrent Neural Networks (RNNs)

![RNN](https://user-images.githubusercontent.com/970858/63474771-d6734700-c469-11e9-83bb-9429da563909.png)

## Introduction

In this LAB, you will go through the steps of building two types of Recurrent Neural Networks (RNNs) to predict stock prices. You will compare a simple RNN model with an **LSTM** (Long Short-Term Memory) model, understand the differences, and evaluate their performance. Finally, you will perform hyperparameter tuning using **GridSearch** to optimize your model.

---

## Setup Instructions

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

## Iteration 1: Data Load

We will start by loading the historical stock price data for **Apple (AAPL)** from Yahoo Finance using the `yfinance` library. The data will cover the period from **January 2010** to **January 2022**.

- Download the data and load it into a pandas DataFrame.
- Focus on the **'Close'** column, as we are interested in predicting the closing price of the stock.
- Display the first few rows to understand the data structure.

#### Tasks:
1. Use the `yfinance` library to download the data.
2. Load it into a pandas DataFrame and inspect the first few rows.

---

## Iteration 2: Explore Data

Before jumping into model building, it's important to explore and visualize the data. This helps to understand trends and patterns over time.

- Plot the closing prices over time to observe the stock price fluctuations.
- Optionally, compute basic statistics such as the mean and standard deviation of the stock prices.

#### Tasks:
1. Create a line plot of the **'Close'** prices to visualize the trend.
2. (Optional) Calculate basic statistics such as the mean and standard deviation of the closing prices.

---

## Iteration 3: Feature Selection and Preprocessing

### 3.0 Feature Selection

For this task, we will use the **'Close'** column as our feature for time-series prediction.

### 3.1 Create Time Sequences

Since RNN models require sequential data, we need to transform the dataset into sequences. Each sequence will consist of a **window of 60 days** of stock prices, and the target variable will be the stock price on the **61st day**.

- Create a function that takes the closing prices and generates sequences of a given length.

#### Tasks:
1. Write a function that takes the dataset and creates sequences of past stock prices.
2. Make sure that each sequence has a target value, which will be the stock price of the day following the sequence.

### 3.2 Feature Normalization

Neural networks perform better when input data is normalized. We will normalize the stock prices using **Min-Max Scaling**, scaling values between 0 and 1.

#### Tasks:
1. Apply Min-Max Scaling to normalize the data.
2. Ensure the scaling is applied after creating the sequences.

---

## Iteration 4: Build Recurrent Neural Network Models

Now that we have preprocessed the data, we will build two different models: a basic RNN and a more advanced LSTM model. The goal is to compare the performance of these two approaches.

### 4.1 Build a Simple RNN

You will first create a basic **RNN** model using the **Keras** library. This model will contain:
- One SimpleRNN layer, followed by a Dense layer to output the predicted stock price.

#### Tasks:
1. Define a simple RNN model.
2. Compile the model using **Adam** optimizer and **mean squared error (MSE)** loss function.

### 4.2 Build an LSTM Model

Next, you will create an **LSTM** model, which is a more advanced type of RNN designed to handle long-term dependencies.

#### Tasks:
1. Define an LSTM model.
2. Compile the model using the same optimizer and loss function as the RNN.

---

## Iteration 5: Train Both Recurrent Neural Networks

You will now train both models using the same training data and parameters to keep the comparison fair.

- Use a **batch size** of 32 and train for **10 epochs**.

#### Tasks:
1. Train the RNN model.
2. Train the LSTM model.
3. Observe the training loss for both models to understand their learning behavior.

---

## Iteration 6: Evaluate Both Models

After training, it's important to evaluate the models on a test set to understand their performance.

- Calculate key metrics like **Mean Squared Error (MSE)** and **Mean Absolute Error (MAE)** to compare the prediction accuracy of both models.

#### Tasks:
1. Use the trained models to predict on the test data.
2. Calculate the **MSE** and **MAE** for both models.
3. Compare the evaluation metrics to determine which model performs better.

---

## Iteration 7: Visualize Training History

Visualizing the training process can help you see how well each model learned from the data. You will plot the loss curves for both models to understand their convergence behavior.

#### Tasks:
1. Plot the loss curves for both the RNN and LSTM models.
2. Compare the loss curves to see how quickly or slowly each model converged during training.

---

## Iteration 8: Hyperparameter Tuning with GridSearch

At this point, you will perform **hyperparameter tuning** to find the optimal set of parameters for your models. GridSearch is a systematic way to search for the best combination of hyperparameters.

#### GridSearch Parameters to Tune:
- Number of RNN/LSTM units (e.g., 50, 100)
- Batch size (e.g., 32, 64)
- Number of epochs (e.g., 10, 20)
- Learning rate (e.g., 0.001, 0.0001)

You will use **GridSearch** to evaluate different combinations of these parameters to find the best performing model.

#### Tasks:
1. Set up a GridSearch to try different combinations of hyperparameters.
2. Run GridSearch for both the RNN and LSTM models.
3. Identify the best set of hyperparameters and retrain the models with them.

---

## Iteration 9: Final Model Evaluation

After hyperparameter tuning, evaluate the models again with the test data using the optimal hyperparameters you found. Compare the results with the previous models to see if tuning improved performance.

#### Tasks:
1. Retrain both models using the optimal hyperparameters.
2. Evaluate the models again and compare the performance improvements after tuning.

---

## Bonus

### Compare Results with Other Models

To extend your analysis, you can compare the results of your RNN/LSTM models with traditional statistical methods like **ARIMA** or **Prophet**. This comparison will help you understand how machine learning models differ from classical time-series forecasting methods.

---

## Submission
Once you have completed your analysis and visualizations, push your Jupyter notebook to your forked GitHub repository. Ensure that your final submission includes narratives explaining your visualizations and insights.


```bash
$ git add .
$ git commit -m "done"
$ git push origin main
```

Then create a Pull Request!!

## Additional Resources

- [ ]()
- [ ](/)
- [ ]()
- [ ]().
- [ ]().

![happy_coding](https://user-images.githubusercontent.com/970858/63899010-c23fc480-c9ea-11e9-84a2-542907e42362.png)
