# Stock Analysis with VBA
## Overview of Project 
A Finance degree holder, Steve, who wanted to assist his parents make the right decision regarding which  green energy stock to invest in, decided to use VBA for his analysis. His parents without much research, had decided to invest all their money in DAQO New Energy Corp stock. An Excel file that contained a handful of green energy stock data including that of DAQO New Energy Corp was analyzed by steve. He used the extension to excel, VBA, for his analysis so that the analysis could be automated and reused with any stock data. After his analysis, the result was that DAQO New Energy Corp had a return of approximately 200% in 2017 but in 2018 its return dropped to -63%.

### Purpose

In this project, the existing VBA code that was created by steve to help determine which green energy stock his parents should invest in will be refactored. Refactoring the code will allow the VBA Macro to run more efficiently. That is, it will be able to run thousands of stocks while using just a short time to execute. The goal here is to make it possible to expand the dataset to include the entire stock market over the last few years while running in a short amount of time.  


## Results

In performing this analysis, three new output arrays "tickerVolumes", "tickerStartingPrices", and "tickerEndingPrices" were created. A variable "tickerIndex" was also created and set to zero before iterating over all the rows.The tickerIndex was used to get access to the correct index of the new three arrays created as well as the "tickers" array.

A loop was created to initialize tickersVolume to 0. Another loop was created to loop over all the rows in the spreadsheet. Within this second loop, using the tickerIndex as index, a script was created that increased the current "tickerVolumes" and added the ticker volume for the current stock ticker.

An if-then statement was created to check whether the current row is the first row with the selected tickerIndex.If it is, the current starting price is assigned to the tickerStartingPrices variable. Another if-then statement was created to check whhether the current row is the last row with the selected tickerIndex.If it is, the current closinging price is assigned to the tickerEndingPrices variable.

A new script was created that increases the tickerIndex if the next row's ticker does not match the previous row's ticker. A for loop was used to loop through the four arrays to obtain "Ticker", "Total Daily Volume', and "Return" columns in the worksheet. The code was run and the stock analysis outputs were the same as it was before being refactored. 

From the analysis of the results obtained, the overall stock performance of the year 2017 was far better than the performance for 2018. 

![2017_analysis](https://user-images.githubusercontent.com/102351522/168691875-0eb19e26-3d7b-4626-8f1e-7d6990c71240.png)


![2018_analysis](https://user-images.githubusercontent.com/102351522/168691955-5f90f1b0-847b-4eb9-a941-61db255c16c7.png)

As it can be seen from the above images, the year 2017 had just one stock (TERP) having a negative return while the year 2018 had just two stocks (ENPH and RUN) having a positive return. 

When it comes to run time, the original code Steve created took about 0.96 seconds to run for the year 2017 and about 0.89 seconds to run for the year 2018. After refactoring, the code runtime reduced to 0.1875 seconds for 2017 and 0.15625 seconds for 2018 as shown in the images below.

![2017image](https://github.com/GerlechJen/stock-analysis/blob/main/RESOURCES/VBA_Challenge_2017.png)

![2018image](https://github.com/GerlechJen/stock-analysis/blob/main/RESOURCES/VBA_Challenge_2018.png)

## Summary 
Refactoring code has a lot of advantages. Some of the advantages include:
- It improves the logic of the code and makes the code easier to read and understand.
- It makes the code use less memory hence the code runs faster .
- It makes the code reusable.
- It makes debugging a little more smoother 
- It helps to improve the functionality of the code without adding any new functionality.
- It makes the code more organized and reliable.

When it comes to disadvantages, if not carefully executed, refactoring could introduce new bugs or errors into the existing code which can affect the functionality of the code. Also, refactoring can be time-consuming.

The pros and cons mentioned above apply to the refactoring performed on the original code for this project. The refactored code is easier to read and understand. Also, when the code had not been refactored, the runtime for the 2017 analysis was about 0.96 seconds and that of 2018 was about 0.89 seconds. However, after refactoring, the code runtime reduced to about 0.19 seconds for 2017 and 0.16 seconds for 2018.

Furthermore, after refactoring the code, if thousands of stock data for other years are to be included in the Excel file, the code will still run efficiently. Although the initial code worked for the analysis of the two years and will work even if we had a dozen years' stock data, it might not run as well. Should we try to analyze thousands of stock data using the old code, even if it will run it would take a very long time to execute the code.

Another thing that was observed was that, for the initial starting code when a year is run, the formatting applied to colour the cells based on whether the return was positive or negative does not work automatically on the next year analysed. For the next year analysed to have a correct colour formatting, the formatAllStocksAnalysisTable() Macro has to be run again for the correct colours to be applied. When it comes to the refactored code, the functionality was greatly improved. When different years are analyzed using the refactored code, the colour formatting works perfectly for any year analyzed without having to re-run the formatAllStocksAnalysisTable() Macro.

To address the disadvantages of refactoring mentioned earlier, while refactoring the existing code, I took time and also tested the code often to make sure it was working as expected before moving on to the next step and this resulted in an accurate refactored code.
