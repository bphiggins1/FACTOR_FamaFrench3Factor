# FamaFrenchFactorModel
The code in this repository downloads the data for the 3 Fama and French factors:
   1. Excess Return on the Market (Mkt-RF)
   2. Small Minus Big (SMB-accounts for publicly traded companies with small market caps that generate higher returns)
   3. High Minus Low (HML-accounts for value stocks with high book-to-market ratios that generate higher returns in
                     comparison to the market)
Then it regresses portfolio excess (fund return - RF) against market excess, SMB, and HML
      port_excess ~ mkt_excess + SMB + HML

DownloadCleanFamaFrenchData.py
   This Python code downloads and cleans Fama and French 3 factor model data.
   The data is downloaded into the file: F-F_Research_Data_Factors.csv
     (This code is based on that on the following website: https://www.codingfinance.com/post/2018-06-15-clean-ff-data-in-py/)
     
FactorBasedAnalysis.py
   This Python code extracts the Fama French factors data extracted from the previous program.
   It pulls price data for a fund (in this case Fidelity's FCNTX) from Yahoo and calculates that fund's returns.
   Fund returns are merged with Fama French data. Portfolio excess returns are calculated as returns minus risk free rate.
   An OLS regression is performed to fit the following equation: port_excess ~ mkt_excess + SMB + HML
   A second OLS regression is performed for fund GGRAX to fit the same equation: port_excess ~ mkt_excess + SMB + HML

This code is based on that in the following websites:

   Factor Based Analysis in Python
   
   https://www.codingfinance.com/post/2019-07-01-analyze-ff-factor-python
   
   https://github.com/codingfinance/misc/blob/master/get_fama_french.py
