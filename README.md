# Sigma Internship Coding Challenge Solution
    This repository contains my solution to the Sigma Internship Coding Challenge, designed to demonstrate proficiency with the Quantrocket platform, coding abilities, and understanding of basic trading algorithms.

Goal: Constructing a simple model to make buy order decisions for Apple Inc. (AAPL) stock based on daily close prices for the year 2023.

Getting Started
    
    Installation: It is instructed to install Quantrocket either locally or on a cloud platform.
    
    Data Retrieval: Pulling the daily close price data for AAPL for the year 2023, leveraging Quantrocket's freely available US stock price data.
    
    The Trading Model
    Objective: The core objective is to build a model that decides whether to place a buy order trade for the next day (d+1), aiming to maximize the portfolio's value based on daily returns (r(d)).

The model involves:
Logic

    Calculating daily returns: r(d) = (p(d) - p(d-1))/p(d-1).
    
    Classifying states based on returns:
    Bull (+1) if r(d) >= 0.01.
    Flat (0) if -0.01 < r(d) < 0.01.
    Bear (-1) if r(d) <= -0.01.
    
    Applying a value function where the portfolio value (V(d+1)) is adjusted based on the state transitions from day d to d+1.
    Increase the portfolio value by 1 if Flat on (d) to Bull state on (d+1)
    Decrease the portfolio value by 1 if Flat on (d) to Bear state on (d+1) 
    Stays unchanged for all other scenarios

Implementation

    This repository includes a Jupyter Notebook (Final.ipynb) containing the complete code implementation of the trading model described above. The notebook walks through the data retrieval process, calculation of daily returns, state classification, application of the value function, and decision-making to identify optimal buy points.

Results
The notebook concludes with:

    The final portfolio value V(N) after executing the trading strategy throughout 2023.
    A list of optimal buy indices, indicating the days on which buy orders were placed.

Output

    Portfolio Value =  17
    Buy Indices:  [6, 8, 12, 16, 21, 28, 30, 41, 50, 52, 59, 61, 69, 79, 85, 88, 94, 100, 103, 108, 110, 113, 117, 120, 123, 133, 142, 160, 164, 177, 187, 191, 207, 209, 212, 216, 218, 232, 234, 238]

Further Steps
