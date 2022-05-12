# Algorithmic Trading Using Python Course Notes
sources:
API Documentation: (https://iexcloud.io/docs/api/)
Video: (https://www.youtube.com/watch?v=xfzGZB4HhEE)
Jupyter Notebook: [[(FINISHED)001_equal_weight_S&P_500.pdf]]

## Part 1: Fundamentals and API Basics
- IEX Cloud API
	- Free service, provides randomly generated data
	- GET Request - get data from API
	- POST Request - add data to the API
	- PUT Request - adds and overwrites data in the API
	- DELETE request - deletes data in API

## Part 2: Building an Equally Weighted S&P500 Portfolio
- The following libraries are required
	- numpy
	- panda
	- requests
	- xlswriter
	- math

1. Must first import relevant stocks tickers from a .csv file
	- Can also be imported directly via an API (paid service)
	- Use Pandas command ``pd.read_csv()``.

2. Making API Calls
	- Create dynamic string for url that gets passed the stock ticker and the API token
	- Use ``requests.get`` to pull from exchange via API and import into a .json

3. Parsing API Calls
	- Using python library, assign to the variables (eg. price, volume) their respective values from the .json into an array using ``data['xyz']``.

4. Adding stock data to a Pandas DataFrame
	- First create array with necessary labels
	- Create pandas data frame and assign to columns the array
	- use ``.append`` to append the DataFrame using ``pd.Series`` which appends the DataFrame row by row
	
5. Looping through the tickers in our list of stocks (inefficient)
	- Using the method above, use API to pull stock information and append it to the DataFrame	

6. Better off, perform a batch call for the stock information
	- Batch call in this case would reduce number of API calls from 500 to 5

7. Export and format recommended trade into an .xlsx file using Pandas and .xlsx writer

Following is the output: 
![[recommended_trades.pdf]]



