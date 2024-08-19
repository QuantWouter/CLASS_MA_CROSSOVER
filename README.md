Moving Average Strategy (maCrossover Class)

This project implements a simple Moving Average strategy using Python, encapsulated within a class called maCrossover. The class allows you to instantiate an object that performs the strategy on a given stock, specified by the ticker, start date, end date, and moving average length.

Project Overview

The maCrossover class calculates a moving average for a specified stock and generates trading signals based on its relationship with the stock’s closing price. Specifically, when the moving average is higher than the closing price, a long trade signal (1) is generated. Otherwise, a signal of 0 is recorded. The signals are stored in a signal column, and the column is shifted by one position for proper backtesting.

This strategy uses vectorized backtesting to efficiently process the data.

Features

	•	Object-oriented design with the maCrossover class
	•	Fetch historical stock data using yfinance
	•	Calculate a single moving average of user-defined length
	•	Generate trading signals: 1 (long) when the moving average is above the close price, 0 otherwise
	•	Shift the signal column by one for backtesting
	•	Visualize the stock data and signals using matplotlib

Installation

To run this project, you’ll need to have Python installed along with the following libraries:

pip install yfinance numpy pandas matplotlib

Usage

Class Initialization

To use the maCrossover class, you first need to import the necessary libraries and create an instance of the class with the required parameters:

import yfinance as yf
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from maCrossover import maCrossover  # Adjust the import according to your file structure

# Initialize the class
crossover = maCrossover(ticker='AAPL', start='2020-01-01', end='2023-01-01', ma_length=50)

Running the Strategy

Once the class is initialized, you can run the strategy and generate the graph:

crossover.run()

This will output a graph showing the stock’s closing price alongside the moving average and plot the generated trading signals.

Example

Here is an example of how to use the class:

# Import the class and libraries
import yfinance as yf
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from maCrossover import maCrossover  # Adjust the import according to your file structure

# Initialize the class with desired parameters
crossover = maCrossover(ticker='TSLA', start='2021-01-01', end='2023-01-01', ma_length=50)

# Run the strategy and plot the results
crossover.run()

How the Strategy Works

	1.	Moving Average Calculation: The class calculates the moving average for the specified ma_length.
	2.	Signal Generation:
	•	A signal of 1 is placed in the signal column when the moving average is higher than the close price.
	•	A signal of 0 is placed when the moving average is not higher than the close price.
	3.	Signal Shift: The signal column is then shifted by one position to account for backtesting.
	4.	Visualization: The class then plots the stock’s closing price and moving average on a graph, along with the signals.

Libraries Used

	•	yfinance: For fetching stock data
	•	numpy: For numerical computations
	•	pandas: For data manipulation
	•	matplotlib: For plotting the results

License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

Contributing

Contributions are welcome! If you find a bug or have a feature request, please open an issue. If you’d like to contribute code, feel free to submit a pull request.

Contact

If you have any questions or feedback, feel free to reach out via my GitHub profile: QuantWouter
