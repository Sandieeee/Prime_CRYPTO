# Prime_CRYPTO
This code is designed to fetch the top 50 cryptocurrencies by market capitalization from CoinGecko's API, display their details, and then save this data to an Excel file. Let me walk you through the process, as I would in an interview:

Importing Libraries:

pycoingecko is used to interact with the CoinGecko API and fetch cryptocurrency data.
openpyxl is used to handle Excel files (reading, writing, and saving).
time is imported but isn't used in the code snippet (it might be meant for future use, like adding delays).
Fetching Data from CoinGecko:

The CoinGeckoAPI object (cg) is instantiated, which allows interaction with CoinGecko's public API.
The get_coins_markets() function is called to fetch the top 50 coins by market capitalization in USD, sorting them in descending order of their market cap. The function's parameters include:
vs_currency='usd': The prices are in USD.
order='market_cap_desc': This sorts the results by market capitalization in descending order.
per_page=50: Limits the results to 50 coins.
page=1: Specifies the first page of results.
The fetched data (top_coins) contains details such as coin name, symbol, price, and market capitalization.
Displaying Data:

The program then loops through the top_coins list and prints each coin's rank, name, symbol, price, and market capitalization.
Each cryptocurrency is printed in a formatted manner, showing its rank, name, symbol (uppercase), price (formatted with commas), and market cap.
Excel File Handling: The update_excel() function performs the task of updating or creating an Excel file (crypto.xlsx) with the fetched cryptocurrency data:

File Handling: The function attempts to load the crypto.xlsx file. If the file doesn’t exist (FileNotFoundError), it creates a new workbook.
Worksheet Setup: The Excel sheet is either opened (if it exists) or created with column headers: Coin_Name, Symbol, Price(usd), and Market_Cap.
Checking Existing Coins: The existing data is checked in column 'A' (Coin Names). This ensures that duplicate coins aren't added to the sheet.
Adding New Data: For each coin that’s not already in the existing list, the name, symbol, price, and market cap are added to the next available row in the sheet.
Saving the Workbook: After updating the Excel file with the new data, the workbook is saved and the function prints a success message. If any error occurs during saving, the error message is printed.
Closing the Workbook: The workbook is closed using workbook.close() to free up resources.
Execution Flow:

Initially, the top 50 coins are printed to the console.
The update_excel() function is meant to be called later (though it's not invoked in the current code snippet), which will update the Excel sheet with the data.
