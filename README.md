# Behaviour of residential construction and real estate markets in W.A. during Covid-19 Crisis

## Team members
- Lauren Prins
- Daniel Sobral
- Warren Villarosa
- Sylvia Broadbent

## Table of Contents
- [Summery](#Summery)
- [Stock Market - Daniel Sobral](#Stock_Market)
- [Real estate - Warren Villarosa](#Real_estate)
- [Permits & construction value - Sylvia Broadbent](#Permits_construction)
- [First home owners grant - Lauren Prins](#First_home)
- [Conclusion](#Conclusion)
- [Limitations of the study/ Difficulties experienced](#Limitations)
- [If we had more time](#more_time)

# Summary <a name = "Summery"></a>
## Hypothesis
Considering the information we keep receiving from the government and media, it seems that the whole world has been affected by COVID-19. We are looking at various factors of the residential real estate and construction market in WA to see if it has really been affected.

## Questions
We asked ourselves what areas we can look into to get a diversified look at the residential real estate market as that is an area of shared interest in our team. We have narrowed it down to property sales, building permits issued and their value and the first home owner grant in relation to dwellings, townhouses and apartments.
We then looked further into the behaviour of the stock value of the 10 largest property groups in WA.

## Available timeframe
We based our timeframe for the research on the dataset with the most limited data. This turned out to be the real estate information as most of that information requires payment. We started from the last quarter of the year in 2018 to the second quarter this year.

## Covid-19 period
In WA the regional travel ban started on 31 March so we have used the second quarter of 2020 as the ‘COVID-19’ quarter to compare against. 

# Stock Market - Daniel Sobral <a name = "Stock_Market"></a>

## Question: How was the Share Market impacted from Q4 2018 to Q2 2020?
How does the behavior of the market relates to other macro economic factors in the Real Estate Sector?
To do so we will look at the top 10 companies with highest market capitalization in the property sector.

## Data: Extracted share prices and traded volume data from the last 5 years using Bloomberg API available on RapidAPI.
National Real Estate Sales Data - extracted from Kaggle 

Cleanup & exploration: 
Libaries and modules used: 

    requests
    pandas
    numpy
    datetime
    json
    matplotlib.pyplot
    matplotlib.dates
    scipy.stats
    csv

Save extracted Data into json format

Use Pandas module to treat our data creating tables to analyse changes in volume traded and share price change. Individual tables per share were created, holding the price value and traded volume value.

Convert our tables into quarterly % changes to analyse possible sudden changes as Australia dealt with the Covid-19 Crisis.

Convert Share Market Price change into monthly % changes, increasing our number of data points in order to look for correlation with changes in national changes.

Table 1 - Share Price % change
![](https://paper-attachments.dropbox.com/s_EF93BDB6B62B70FB08902DFADDC9F89B49DC49956990D5BF17FBD2E1EE63378F_1603706661387_Share+Price+Change.PNG)


Table 2 - Trade Volume % Change
![](https://paper-attachments.dropbox.com/s_EF93BDB6B62B70FB08902DFADDC9F89B49DC49956990D5BF17FBD2E1EE63378F_1603706727211_Trade+Volume+Change.PNG)

## Analysis:
To visualise our data we decided to plot line charts as they express strong changes during the Covid-19 Outbreak. The analysis is split into 2 approaches, outlook on share valuation (Figure 1) and market liquidity (Figure 2)

Figure 1 - % Change in Share Value
![](https://paper-attachments.dropbox.com/s_EF93BDB6B62B70FB08902DFADDC9F89B49DC49956990D5BF17FBD2E1EE63378F_1603706935385_top+10.png)

### Share Price Analysis
- From start of 2020 the Top 10 Property stocks display closer price movements, 
- Leading to end of Q2 2020 (covid outbreak and subsequent lockdown) measures all shares dropped.
- Followed by a V-shape recovery until end of Q3 of 2020.
- GMG stands has the biggest realestate company with 3 times the market cap of the second largest.
-  The Average Price Movement will allow us to compare the stock market behaviour with other macroeconomic variables.

Figure 2 - % change in Traded Value
![](https://paper-attachments.dropbox.com/s_EF93BDB6B62B70FB08902DFADDC9F89B49DC49956990D5BF17FBD2E1EE63378F_1603706946742_top+10vol.png)

### Volume as a Liquidity indicator: 
- GMG displays a more independent behaviour with and individual spike of liquidity leading to 2020 Q3. 
- Spike in volume traded in the beginning of 2020(pre-covid) - Followed of a massive drop heading to end of Q2 2020(post-covid).

### Overall Share Market Conclusion Conclusion:
-  Shares Value and Volume traded dropped after March.
-  Although the % change in prices saw a V-shape recovery, the % change in traded volume kept negative.
- Despite the recovery in the value these stocks, they now offer significantly less liquidity than they did pre-covid.

## Correlation:
After analysing the Share Market behaviour in regards to real estate, we set out to find if the market behaviour has any correlation with changes in National Real Estate Sales.

Due to limitations on National Sales Data we limit our table to begining of April 2020.
Using pandas module I transformed absolute sales value into monthly percentage change and compare it with the share market percentage change. This change allowed me to increase the number of data points to 18 (Table 3) and create a scatter (Figure 3) plot to compare the 2 variables.

Table 3 - Change in Property Sales Vs Share Value Change
![](https://paper-attachments.dropbox.com/s_EF93BDB6B62B70FB08902DFADDC9F89B49DC49956990D5BF17FBD2E1EE63378F_1603704236523_image.png)

Figure 3 - Change in Property Sales vs Share Value Change
![](https://paper-attachments.dropbox.com/s_EF93BDB6B62B70FB08902DFADDC9F89B49DC49956990D5BF17FBD2E1EE63378F_1603702717601_Scatter.png)

Figure 3 shows that share price value variation presented some stability when compared
with the variation in Property Sales.

We can notice a clear exception when both variables revealed a record drop.
As we've seen previously on Figure 1 this drop relates to the beginning of Q2 202, when the covid-19 outbreak gave origin to lockdown measures Australia wide. 

Normal Distribution Hypothesis:
Using - scipy.stats module 
Both Variables exceeded the necessary p-value to be considered normal distribution so we cannot run a linear regression and evaluate a degree of correlation.

# Real estate - Warren Villarosa <a name = "Real_estate"></a>

## Introduction:
The following data was sourced from Kaggle as a CSV file and included real estate sales nation wide. The dataset did not include commercial real estate sales. Each row was a confirmed sale and included date, price, suburb, property type and the coordinates for the suburb

## Methodology:
The Market of interest for the analysis was Western Australia so I cleaned the dataset and limited it to sales within Western Australia. I wanted to make sure that I used as much of the information available. Some time was spent changing the strings in the date column into Datetime format and breaking the dates into year, month and quarter columns to make grouping a little simpler.

The main libraries and modules used for the processing of this data were:

- Pandas
- Matplotlib
- Scipy
- Numpy
- Datetime

Figure 1 - The Share of total real estate sales over the time frame examined.

![Share of total volume by Property Type.](https://paper-attachments.dropbox.com/s_7E2DABFC1BDBAC38C0C2816ADBC56CEB5E5B8459AE1D27059D21C777E0A08794_1603511933169_share_by_property_total_sales_2018_to_2020.jpeg)

The figure above is simply here to illustrate that the Western Australian market is heavily weighted towards dwellings (houses) with only 13% of the market being shared between units and townhouses. This means that the sales of the latter two categories will only have a minor influence on the data following. 

After grouping the data by year, month, date sold and adding a count of entries, I was able to produce the plot below by plotting the months against the counts which corresponded to sales volume. On the above figure and the ones following, I marked some key dates to see if they coincided with any major trends in the data. The dates are as follows:

- Dec 31st 2019 - WHO announces a “mysterious pneumonia”
- Late February (Around the 23rd) 2020 - Scott Morrison Declares Covid 19 a pandemic
- March 11 2020 - WHO Declares Covid19 a global pandemic
- March 31 2020 - Regional borders and schools closed within Western Australia
- June 6 2020 - Regional travel ban lifted

The dates were sourced from various news articles from the ABC.

Figure 2 - Total volume of real estate sales from Oct 2018 to June 2020
![Total volume of real estate sales over the period examined](https://paper-attachments.dropbox.com/s_7E2DABFC1BDBAC38C0C2816ADBC56CEB5E5B8459AE1D27059D21C777E0A08794_1603507663698_line_re_sales_bymn_102018_to_072020.jpeg)

This particular figure illustrates the trend followed by the total volume of sales during the period being examined. I chose this graph because I thought it would be interesting to explore the effect that Covid19 had on the overall volume of sales.  The sharpest drop in volume appears to follow shortly after Scott Morrison declared Covid 19 a pandemic (Indicated by the purple intermittent vertical line) in late February 2020 (ABC News). While the correlation between the two can only be suggested as a best guess with the limited data on hand, the market does show a strong reaction not long after the announcement.

Figure 3 - Volume of realestate sales from Oct 2018 to June 2020 by housing category 
![Total volume of realestate sales by category Oct 2018 to Jun 2020](https://paper-attachments.dropbox.com/s_7E2DABFC1BDBAC38C0C2816ADBC56CEB5E5B8459AE1D27059D21C777E0A08794_1603507684295_line_re_sales_cat_bymn_102018_to_072020.jpeg)

After breaking the dataset up into property type I was able to plot individual trend lines for each property type against the monthly periods. The above figure provides an insight into the influence the various housing categories had on the overall volume of sales.

When compared to the previous line graph an almost identical trend can be noticed in dwellings (green); this is likely because they make up the lions share of the total volume of sales. The market’s reaction had a less severe but noticeable effect on the sale of units (yellow), while the low volume of town house (purple) sales was barely affected at all.

Figure 4 - mean and median house price by month 
![Monthly key housing price indicators from Oct 2018 to Jun 2020](https://paper-attachments.dropbox.com/s_7E2DABFC1BDBAC38C0C2816ADBC56CEB5E5B8459AE1D27059D21C777E0A08794_1603507707123_line_re_sales_medmean_bymn_102018_to_072020.jpeg)

Another avenue that I wanted to explore was the effect that Covid 19 had on house prices. To obtain this dataset I grouped by year, month and used my favourite function, .agg to determine the mean and median prices for each period of interest.

I had initially planned to create box plots of the resulting data for some variety. However, I decided against this as plotting just the median and mean house prices was clearer and told the same story. Housing prices had appeared to follow a downward trend since the initial announcement from the WHO acknowledging a “mysterious pneumonia” . However, what is interesting is that the mean price trended upward for two months not long after Scott Morrison’s announcement, while the median house price continued to fall. One can speculate that investors or owners with higher value assets were prompted to liquidate in preparation for what would inevitably become a recession. Once borders finally shut then the mean house price started falling sharply following the median house price trend. 

Table 1 - Top Ten Suburbs by Sales Volume across quarters during the period examined

| Q4 2018      | Q1 2019      | Q2 2019        | Q3 2019      | Q4 2019      | Q1 2020      | Q2 2020      |
| ------------ | ------------ | -------------- | ------------ | ------------ | ------------ | ------------ |
| Baldivis     | Baldivis     | Baldivis       | Baldivis     | Baldivis     | Baldivis     | Baldivis     |
| Canning Vale | Morley       | Thornlie       | Canning Vale | Canning Vale | Scarborough  | Ellenbrook   |
| Morley       | Scarborough  | Canning Vale   | Scarborough  | Scarborough  | Canning Vale | Canning Vale |
| Dianella     | Canning Vale | Ellenbrook     | Dianella     | Thornlie     | Dianella     | Dianella     |
| East Perth   | Dianella     | Scarborough    | East Perth   | Ellenbrook   | Morley       | Butler       |
| Gosnells     | Como         | Dianella       | Elllenbrook  | Rockingham   | Rockingham   | Scarborough  |
| Perth        | Gosnells     | Maylands       | Morley       | Perth        | Como         | Duncraig     |
| Thornlie     | Maylands     | East Perth     | Como         | South Perth  | Maylands     | Thornlie     |
| Clarkson     | Bayswater    | Morley         | Byford       | Dianella     | Duncraig     | Wanneroo     |
| Scarborough  | South Perth  | Secret Harbour | South Perth  | Morley       | Ellenbrook   | Claremont    |

I also wanted to explore the effect that Covid might have had on the best performing suburbs by volume. I had wanted to plot these in bar charts but didn’t feel those bar plots added any value to the big picture. Not even a pandemic could shake Baldivis from its top spot; while Canning Vale, Scarborough and Dianella rarely fell out of the top 10 if ever. I started to wonder why anyone would willingly buy in Baldivis but thought better of it. After all, I myself made the mistake of buying in the same postcode as Armadale. 

Figure 5 - Scatter Plot Showing Correlation between number of permits issued and number of real estate sales for W.A.
![](https://paper-attachments.dropbox.com/s_12B7CFFAE8325C91D43F3E8963105294986F43FBE278F71DB68227B779BEA2DE_1603516124242_Screen+Shot+2020-10-24+at+1.08.10+pm.png)

Figure 6 - Scatter Plot Showing Correlation between number of permits issued and number of real estate sales.
![Number of Permits in Australia vs Total Real Estate Sales](https://paper-attachments.dropbox.com/s_12B7CFFAE8325C91D43F3E8963105294986F43FBE278F71DB68227B779BEA2DE_1603432314983_realestate_permits.png)

# Permits & construction value - Sylvia Broadbent <a name = "Permits_construction"></a>

Through my career as a building surveyor I know that councils are required to submit their statistical data monthly. I started with the Building Commission which is where they have to provide the data to.  Apparently, they just forward it to the ABS (Australian Bureau of Statistics). On the ABS website they have a collection of data of all states and surprisingly the data from WA starts at 1970! 
After finding the right files I could export them as excel files. Then it was just a matter of changing them to a csv format and extracting the relevant information by creating a Pandas DataFrame in Jupyter. 
Some of the columns required changing the type from object to integer and from string to Datetime. Then sorting the information into quarters for comparison and plotting. I didn’t use any average or median values as there is not enough information to make an accurate representation. The dataset needs to be larger for that. 

![](https://paper-attachments.dropbox.com/s_12B7CFFAE8325C91D43F3E8963105294986F43FBE278F71DB68227B779BEA2DE_1603509440694_Screen+Shot+2020-10-24+at+11.16.55+am.png)
![](https://paper-attachments.dropbox.com/s_12B7CFFAE8325C91D43F3E8963105294986F43FBE278F71DB68227B779BEA2DE_1603509448543_Screen+Shot+2020-10-24+at+11.17.03+am.png)

All information presented below shows the number of permits on the left and the value of permits in $’000 on the right.
First I checked out if there was any major differences between the permits issued Australia wide compared to WA per quarter. Australia wide the best quarter is 2018 Q4 (46,181) with not many variation between the other quarters, while in WA  the best quarter is 2019 Q1 (3,935) sloping down to the lowest number in 2020 Q1 (3,231 = 82% of 2019 Q1) with a significant increase in 2019 Q2 (3,750). 

![](https://paper-attachments.dropbox.com/s_12B7CFFAE8325C91D43F3E8963105294986F43FBE278F71DB68227B779BEA2DE_1603432697772_permits_AUvsWA_bar.png)

The following is a pie chart showing just the information for WA of each quarter. The quarters are going clockwise. You can see that there is little variation in the size of the slices with the smallest slice being Q1 this year with 12.6% vs the largest slice being 15.3%.

![](https://paper-attachments.dropbox.com/s_12B7CFFAE8325C91D43F3E8963105294986F43FBE278F71DB68227B779BEA2DE_1603339791219_permits_WA_pie.png)

This line graph is showing just the information for WA of each quarter separated by type of residential construction. Dwellings are the largest parts of residential permits followed by apartments and then townhouses.  When the demand for dwellings go up the demand for apartments go down and vice versa.  This can be explained that the total number of dwellings remains stable whether that is the demand for dwellings or apartments.

![](https://paper-attachments.dropbox.com/s_12B7CFFAE8325C91D43F3E8963105294986F43FBE278F71DB68227B779BEA2DE_1603286166435_Screen+Shot+2020-10-21+at+9.15.08+pm.png)

You can also see that there is not much difference between the amount of permits issued versus the value it represents. We can conclude that the average value per permit does not vary much, which means that the distribution of high spec homes versus low spec homes is fairly equal.

## First home owners grant vs Building permits

We expected the applications for construction grants to directly affect the number of building permits issued.  As shown by the Linear regression model the value shows a moderate negative correlation. 

![](https://paper-attachments.dropbox.com/s_12B7CFFAE8325C91D43F3E8963105294986F43FBE278F71DB68227B779BEA2DE_1603432306265_fhog_permits.png)

# First home owners grant - Lauren Prins <a name = "First_home"></a>

On the 15th of every month, Revenue WA collects data on First Home Owner Grants and publishes it on www.wa.gov.au for public online use.  The data is broken down by month and backdates to July 2000. The downloadable excel file displays the total amount of applications made for the grant, and the number of grants that have been paid.  It’s further broken down into ‘Established Homes’ and ‘New Dwellings’. 
To begin analysis on the data I was able to save the excel tabs as csv files and upload them to Jupyter. I used Pandas to merge the two csv’s together and changed the months listed into the quarters that we needed as an index. From there I could begin presenting the data through various graphs.
I used Matplotlib to create the 2 pie charts below which are displaying the ‘Total applications made’ and ‘total applications paid’ by the Commonwealth for Western Australia. I chose these graphs to see if there was a significant increase or decrease in any of the 7 quarters for either topic but after looking at the charts you can see it is evenly spread.

![](https://paper-attachments.dropbox.com/s_8E5287F91CDD5F5EC83C7EF35473A09757B42788986FDAB9EC9D2A4B9D506DDF_1603351794266_image.png)

![](https://paper-attachments.dropbox.com/s_8E5287F91CDD5F5EC83C7EF35473A09757B42788986FDAB9EC9D2A4B9D506DDF_1603352059636_image.png)

I then chose to combine that data to create a line and bar graph which showed the difference per quarter, between applications made and applications paid. As you can see in this graph, there is a lot of variance both within and between both variables. 

![](https://paper-attachments.dropbox.com/s_8E5287F91CDD5F5EC83C7EF35473A09757B42788986FDAB9EC9D2A4B9D506DDF_1603370360069_image.png)

![](https://paper-attachments.dropbox.com/s_8E5287F91CDD5F5EC83C7EF35473A09757B42788986FDAB9EC9D2A4B9D506DDF_1603370331610_image.png)

I found it interesting that the excel document informs the viewer that the grant guidelines changed in 2019 and the FHOG would only be available for New Dwellings. I displayed this information in the first graph below where you can see a sudden decline and a flat line from 2019 in applications and paid grants to established homes.  The second graph shows a steady amount of paid grants for new dwellings. 

![](https://paper-attachments.dropbox.com/s_8E5287F91CDD5F5EC83C7EF35473A09757B42788986FDAB9EC9D2A4B9D506DDF_1603354797684_image.png)

![](https://paper-attachments.dropbox.com/s_8E5287F91CDD5F5EC83C7EF35473A09757B42788986FDAB9EC9D2A4B9D506DDF_1603354726897_image.png)

# Conclusion <a name = "Conclusion"></a>

Did we find what we expected to find? 
- As a group, we were all hoping to find a significant downturn across all data sets for Q1 and Q2 of 2020. For Sylvia and Lauren, there was no significant change on construction permits or first home owner grants, and between both data sets there was a moderate positive linear relationship of 0.59.
- The total volume of sales, average house price and median house price decreased since the announcement of the pandemic. There was no shown correlation with this and the number of permits, as the r squared value is 0.08. 
- Share value and volume dropped after March 2020. Although prices saw a recovery, the % change in traded volume kept negative.

# Limitations of the study/ Difficulties experienced <a name = "Limitations"></a>
- A lot of real estate information is paid which limited the amount and type of data that is accessible to us. 
- Several construction grants were announced late May, starting in June. There was no information available yet so that is a factor that will have had an impact on the residential construction market.
- Accessibility to the most recent data which would better provide information to the effects of Covid. 
- It would be good to have more access to grant data sets, for WA and AU.
- The Normal test was not possible as it needs a minimum of 8 samples and our dataset has 7 samples (7 quarters).  We also didn’t remove any outliers as there are not enough points left. The linear regression model is limited that it is not provided to predict values but to see if a correlation exist between our several investigations. The outcome will be more reliable with more data.

# If we had more time <a name = "more_time"></a>
- Extend our data time to include more previous years to compare to, and expand with Q3 and Q4 of 2020 so see if there is a recovery.
- Compare WA’s performance against other states and possibly the world.
- Add commercial as well as residential development.
- Include the rest of 2020 to see data trends past the apparent recovery of WA.
- Explore trends by suburb in more detail.
