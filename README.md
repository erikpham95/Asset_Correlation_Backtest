# Asset Correlation Backtest
Verifying common “market wisdom” regarding asset correlations

## I.  Project Descriptions

### 1.  Overview

#### a.  Objectives

-   Various "market wisdom" regarding asset correlations will be tested with 10-year data

-   Python will be used to find the (Pearson) correlation coefficient of asset returns (not "raw" price)

#### b.  Implementation Highlights

-   Programming details

    -   Required Python packages: yfinance, pandas matplotlib

    -   For currency index, raw value (instead of "return") will be used

    -   10-year data will be used (you can change the start & end date to find the correlation between different time period)

-   Execution Guidelines (for Linux & VS code)

    -   S1: Go to your project folder that you store the script (assuming located at **/folder\_locations**) using **cd /folder\_locations**

    -   S2: Create & activate virtual environment

        -   **\> virtualenv -p python3.9 backtest\_correlations**

        -   **\> source /folder\_locations/backtest\_correlations/bin/activate**

    -   S3: Install libraries & provide permissions

        -   **\> pip install yfinance pandas matplotlib**

        -   **\> sudo chmod -R 777 DXY\_vs\_SPY.py**

    -   S4: Run the script with the "Run Python file"
        button in VS Code

### 2.  List of correlations

#### a.  Dollar vs Gold / Silver vs US Market

-   DXY vs SPY / QQQ

    -   US Market is expected to perform well when the USD is weak (low interest rate)

    -   QQQ, which consist of more long-duration asset, is expected to be more sensitive to rates

    -   Gold is expected to perform well when interest rate is low (USD is weak)

    -   Gold is also expected to perform well when uncertainty is high (USD is strong)

-   GLD vs SLV / GDX / SPY

    -   Gold and Silver are expected to be correlated (Gold/Silver ratio is expected to "revert to the mean")

    -   Gold & Gold Miners are expected to be highly correlated

    -   Gold are also "expected" to not correlate with equities (to provide "diversification")

-   US Market Segments

    -   Stocks vs Bonds: QQQ vs TLT

    -   Overall Market vs Mid Cap vs Small Cap: SPY vs IWR vs IWM

#### b.  Oil & Nat Gas

-   CL=F vs NG=F vs XLE / XOP / XES

    -   Oil & Natural gas price are expected to be correlated

    -   Increasing oil price is expected to benefit "Energy Sector ETFs"

-   CL=F vs CAD.USD (EWC) vs AUD.USD (EWA)

    -   Increasing oil price is expected to benefit Canada & Australia (oil exporter)

    -   Their currency is also expected to gain strength

## II. Testing Results

### 1.  Dollar vs Gold / Silver vs US Market

#### a.  DXY vs SPY / QQQ / GLD

-   DXY vs SPY / QQQ

    ![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic1_%20DXY_vs_SPY.png)

    ![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic2_DXY_vs_QQQ.png)

    -   The 10-year correlation is 0.48 (for SPY) and 0.42 (for QQQ),
    against initial believe (rising USD cause stock to fall)

    -   The correlation between different time period is vastly different
    from each other (The negative correlation are much stronger in 2022
    onwards


-   DXY vs GLD

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic3_GLD_vs_DXY.png)

    -   The 10-year correlation is 0.28, against initial believe (rising USD
    cause gold to fall)

    -   The correlation between different time period is vastly different
    from each other (The negative correlation are much stronger in 2022
    onwards

#### b.  GLD vs SLV / GDX / SPY

-   GLD vs SLV

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic4_GLD_vs_SLV.png)

    -   The 10-year correlation is 0.78, very consistent in the 10-yr
    period, follow initial believe (gold and silver are highly
    correlated)

    -   Silver offer lower return with more volatility


-   GLD vs GDX

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic5_GLD_vs_GDX.png)

    -   The 10-year correlation is 0.92, very consistent in the 10-yr
    period, follow initial believe (gold and gold miner are highly
    correlated)

    -   Gold miner offer slightly lower return (dividend not yet accounted)
    with more volatility

-   GLD vs SPY

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic6_GLD_vs_SPY.png)

    -   The 10-year correlation is 0.92, very consistent in the 10-yr
    period, against initial believe (gold offer diversification to
    stock)

    -   Gold provide much lower return than SPY

#### c.  US Market Segments

-   TLT vs SPY

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic7_%20TLT_vs_SPY.png)

    -   The 10-year correlation is 0.52, but the correlation changed greatly
    over time.

    -   It's worth noticing that bond performance in the last 10 years are
    very "abnormal" because of FED's QE and low interest rate.

    -   TLT provide much lower return than SPY, without diversification
    effect.


-   SPY vs IWR vs IWM

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic8_IWR_vs_SPY.png)

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic9_IWM_vs_SPY.png)

    -   The correlation between SPY and IWR (0.99) and IWM (0.95) are very
    high & consistent

    -   SPY outperform due to the contribution of "megacap" stocks like the
    FAANG

### 2.  Oil & Nat Gas

#### a.  CL=F vs XLE / XOP / XES / NG=F

-   CL=F vs XLE / XOP / XES

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic10_Oil_vs_XLE.png)

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic11_Oil_vs_XOP.png)

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic12_Oil_vs_XES.png)

    -   The correlation between Oil price and XLE (0.71), XOP (0.65) and XES
    (0.41) are significant, as expected

    -   XLE and XOP are more correlated to Oil Price than XES, as expected

    -   XES perform very badly for the period from 2014-2021, due to
    underinvestment in energy sector

-   CL=F vs NG=F

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic13_Oil_vs_NatGas.png)

    -   The correlation between oil and natural gas price are significant
    (0.7), as expected

    -   Recently, natural gas price are much more volatile (Ukraine --
    Russia war)

#### b.  CL=F vs CAD.USD (EWC) vs AUD.USD (EWA)

-   CL=F vs CAD.USD / EWC

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic14_Oil_vs_CAD.USD.png)

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic15_Oil_vs_EWC.png)

    -   The correlation between Oil price and CAD.USD (0.64) and EWC (0.51)
    are significant, as expected

    -   It's crucial to monitor the USD and US economy when analyzing Canada
    currency / economy / stock market

-   CL=F vs AUD.USD / EWA

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic16_Oil_vs_AUD.USD.png)

![Use this template](https://github.com/erikpham95/Asset_Correlation_Backtest/blob/main/Pic/Pic17_Oil_vs_EWA.png)

    -   The correlation between Oil price and AUD.USD (0.47) and EWA (0.45)
    are significant, as expected

    -   It's crucial to monitor the China economy when analyzing Australia
    currency / economy / stock market
