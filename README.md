# Project
Comparison of various Machine Learning Models used in the research paper for stock prediction [1].

## About
In the research paper that I picked, the authors surveyed and compared the predictive power of five neural network models, namely, back propagation (BP) neural network, radial basis function (RBF) neural network, general regression neural network (GRNN), support vector machine regression (SVMR), least squares support vector machine regresssion (LS-SVMR) for stock price prediction. They applied the five models to make price prediction of three individual stocks, namely, Bank of China, Vanke A and Kweichou Moutai. They found that BP neural network consistently and robustly outperformed the other four models [1]. In this project I test the conclusions of the neural networks for stock price prediction research paper.

## Introduction
Due to the extremely volatile nature of financial markets, it is commonly accepted that stock price prediction is a task full of challenge. However, in order to make profits or understand the essence of equity market, numerous market participants or researchers try to forecast stock price using various statistical, econometric, or even neural network models [1].

One of the most prominent techniques involved in ML for stock prediction is the use of Artificial Neural Networks (ANN). ANNs can be thought of as mathematical function approximators. The most common form of ANN in use for stock market prediction is the feed forward network utilizing the backward propagation of errors algorithm to update the network weights. These networks are commonly referred to as Back Propagation Neural Networks . Also in recent year there is a significant improvement in SVM (Support Vector Machine) implementation for stock prediction. After various Another form of ANN that is more appropriate for stock prediction is the time recurrent neural network (RNN). One of the modified version of RNN is Long Short Term Memory (LSTM), which memorize history data for prediction [2].

Keeping these details in mind for this project, I tested the accuracy of BPNN, SVM, and LSTM models in stock price prediction. I picked the BPNN and SVM models from the research paper [1] and the LSTM from the princeton paper [2]. The reason I picked the BPNN and SVM from the five models used is due to the implementation difficulty of the other models and time constraints. The reason I included the LSTM  model is because it is currently widely used in stock prediction because they are able to store past information. This is important because the previous price of a stock is crucial in predicting its future price.

## Description
The objective is to predict the increase or decrease in stock price for the next day using the BPNN, SVM, and LSTM algorithms and comparing their performance.

## Approach
Our approach to this project consist of major steps:

1. Dataset collection and creation
2. Implementation of algorithms
3. Comparison of results and analysis

## 1.	Dataset Creation:
For the data collection, I used the pandas data reader package to import stock information from Yahoo Finance. Most of the companies I chose were in the technology sector. I chose Apple, Amazon, Google, IBM, and Microsoft. I collected data from January 2014 to December 2018.

The stock data obtained from yahoo contains the following parameters:

*   Date
*   Open
*   High
*   Low
*   Close
*   Adj Close
*   Volume

Basic assumption in stock market is that the stock momentum increasing or decreasing will depend on the given stock's past performance. Also, the stock price for a given company will also depend on how market is doing and how given sector is doing, which is why I calculated the attributes below.

*   Index Momentum
*   Index Volatility
*   Sector Momentum
*   Stock Momentum
*   Stock Price Volatility
*   Output

**Momentum:** If the price of a stock is higher than yesterday then the momentum for the given day is +1 otherwise the momentum is -1.

**Volatility:** Represents the change in a stock closing value. Volatility is calculated using difference between yesterday's closing value and today’s closing value divided by yesterday’s closing value.

**Index Momentum:** Calculated based on market performance for last five days. It's the five day average volatility for all technology comapnies used in this project.

**Sector Momentum:** Calculated based on market performance for the last five days. It’s the five day average stock value for all the technology companies used in this project.

**Stock Momentum:** Calculated as average for last 5 days momentum for given company momentum

**Stock Price_Volatility:** Calculated as average of last 5 days for given stock.

**Output:** If the closing stock price for a given stock is higher than yesterday’s closing stock price, then the output is 1, otherwise the output is 0.

## 2.	Comparison of Results and Analysis:

I ran the algorithm for each model 30 times and taking the average of the 30 runs at the end. I ran each model multiple times to make sure that the algorithm performs consistently.

**Backpropagation Result:**
I got 66.42 for mean accuracy with a standard deviation of 2.05. An image of the results is in the Back Propagation Neural Network folder.

**SVM Result:**
I got 63.02 for mean accuracy with a standard deviation of 0.32.  An image of the results is in the Support Vector Machine Regression folder.

**LSTM Result:**
I got 62.35 for mean accuracy with a standard deviation of 0.40.  An image of the results is in the Long Short Term Memory folder.

## Conclusion

In this project, I have shown that BPNN outperforms SVM and LSTM. However, we can not fully claim that BPNN outperforms RBF, GRNN, or LS-SVM because I have not implemented these models, but based on houw BPNN outperforms both the SVM and LSTM models, I will stand behind the conclusions of the research paper [1] that BPNN outperforms the others models tested. 

## Reference
**1.**
[Research Paper](https://arxiv.org/pdf/1805.11317v1.pdf)

**2.**
[Reference Paper 1](https://www.cs.princeton.edu/sites/default/files/uploads/saahil_madge.pdf)

**3.**
[Reference Paper 2](https://link.springer.com/article/10.1007%2FBF00126626)

**4.**
[Reference Paper 3](https://ieeexplore-ieee-org.ezproxy.lib.vt.edu/document/859420?arnumber=859420&SID=EBSCO:edseee)

**5.**
[BPNN Reference](https://machinelearningmastery.com/implement-backpropagation-algorithm-scratch-python/)

**6.**
[SVM Reference](https://scikit-learn.org/stable/modules/svm.html)

**7.**
[LSTM Reference](https://machinelearningmastery.com/time-series-prediction-lstm-recurrent-neural-networks-python-keras/)
