---
layout: default
---

# Motivation

Wine is often seen as an important segment of the culinary arts. Wine has existed for centuries, and the way that it has been produced, sourced, and bottled is constantly changing with the adoption of technology in farming. Wine consumption has steadily increased over the past twenty or so years, with the advent of major commercialization and the ‘new world’ joining the ranks of pre-existing major wine producers. Wine has also become a store of value, sometimes with returns even greater than the stock and bond markets. 

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/1.png)

The motivation of this analysis is straightforward - we both love red wine and want to spread our love of red wine to our fellow peers. Wine is often seen as an expensive alcohol that requires capital for quality, and we want to prove that this is not the case. Some of the best wines that we have had cost $20, yet, when we conducted some preliminary research for this project, our peers thought that the average price of wine cost around $30. This common misconception prevents college students from consuming wine and enjoying a beverage rich in history. 

Wine plays an important role in many countries, and is becoming increasingly important in American culture. The United States is now the 4th biggest producer of wine, after France, Italy, and Spain. Interestingly, the United States is the biggest consumer of wine, with an increasing number of individuals falling in love with this form of alcohol. We choose to specifically study wine from the US because of its growing demand and appreciation, alongside the fact that we both originally study in the US. We used Vivino, a powerful marketplace to analyze wine and extract our data. Vivino uses crowd-sourced data to personalize wine recommendations to its users, making it the premier platform to search for and buy the right wine. 

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/2.png)

# Justification

In popular culture, wine is seen as an alcoholic beverage purchased and consumed for special occasions, at restaurants with family, friends, and business colleagues. Wine can be classified into three major categories - red, white, and rose. Red wine is produced from the grapes and skin of red grapes, white wine is produced with the pulp of white grapes, and rose is produced with a mixture of red and white grapes. Through fermentation and the addition of sugar, raw grapes are processed into a drink that is enjoyed worldwide. 

Since the data set would be too large to take into account all the different styles and types of wine, we decided to focus on red wine production in the US. Red wine is the most popular style of wine, with prices ranging from as little as $2 to over $15,000. This not only makes it exciting to analyze but also provides depth to the data we can extract. Additionally, the different characteristics of wine, along with the sheer variety of styles and grapes within red wine production, make it a topic worth exploring. 

# Aim

To provide an accurate analysis of which ones truly represent value for money from the US region, we needed to probe and ask a specific set of questions. Amongst many of the questions we aimed to answer, a few key thoughts were:

1.  What year of production yields the highest rating of red wine (California and its regions)?
2.  How does price impact red wine ratings in California?
3.  What are the most and least popular red wine grapes grown in California?
4.  What are the best food pairings (vegetarian cuisine, steak) that go well with red wine?

From these main questions, we were able to dive deeper into the data and create sub-questions that really helped us focus on the quality of red wine in California. 

# Understanding the Data
To gain an accurate representation of our data, we had to adjust filters on Vivino to suit the needs of our exploration. We changed the original settings to

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/3.png)

As we can see here, we chose to 
1.  **Ship to:** United States
2.  **Region of production:** United States
3.  **State of production:** California
4.  **Price range:** $0 - $500
5.  **Rating:** Any (above one star)

This gave us approximately 12,401 bottles of red wine to extract and analyze. It is important to note that this figure kept on changing as some wines were delisted while others might have been added. The number is different from the screenshot above as new red wines would have been added since we began scraping for this project. 

As a team, we decided to use a mix of selenium and web API to scrape our data from Vivino. After placing the aforementioned conditions, we were able to retrieve 12,401 bottles of wine to analyze. After we extracted the wine, we used different features to retrieve the different characteristics of the wine. The description for these features can be seen below:

|       Characteristics       |       Description       |
|:-------------|:------------------|
| Wine         | This section contains the name of the wine (label printed on bottle)  |
| Winery       | The winery is where the grapes are grown.  |
| The rating   | The average rating of the wine. It ranges between 1.0 to 5.0. It is very rare to have a wine rated at 5.0.  |
| review_count | The review count is the number of times a wine has been reviewed.  |
| Country      | The country where the wine has been produced. In this, all the wines have been produced in the US. |
| Subregion    | The subregion is the region in California where the wine has been produced (eg. napa valley). |
| Price        | The price of the wine. In Vivino, most of the wines are given two prices. The main one is the discounted price and the one below that displayed price is the original price (basic e-commerce sales technique)  |
| Year         | The year when the wine has been produced. Typically, the older the wine, the better it is. However, data shows something far more interesting. |

The starting point of the data was the location of the wine. We used California as a main region because this is where the majority of wine is produced in the us. Within California, there are sub-regions that contribute to the overall wine production of the state. A few examples of this are napa valley, Sonoma county, and Russian River Valley to name a few. We created a heatmap (as seen below) to better portray this data. 

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/4.png)

The heatmap connotes that most of the wine production happens around napa valley, with the heat signature going green and red. In terms of the libraries, we used folium to plot heatmap and nominatim to fight longitude and latitude.  Most of the concentration of wine production in California is in the napa region, and this makes sense due to the spillover of highly skilled labor, fertile land, and capital to invest in and maintain vineyards. There are a few outliers such as Monterey, Sequoia, and the mountainous region of Sacramento. These areas most likely produce smaller quantities, but a higher quality of wine. 

After we finalized our geographical location, we started looking at the best years of production in California. This would answer the very first question we asked ourselves - what years of production yield the highest rating? This would be an important metric to factor in value for money, as the best wines could potentially have come from a great harvesting year. We looked at the top 10 years to give us a greater range of data. The top 10 years of wine production in California can be seen below:

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/5.png)

From the data, we can see that the top 10 years of wine production include 1993, 1998, 1999, 2001, 2003, 2004, 2005, 2007, 2008, and 2011. The top year of wine production was 2003, with an average of 4.65. This marked an exceptional year for California, and specifically napa valley. We were initially shocked at the result of the average and conducted some qualitative research to verify that this was in fact true. 2003 was a stellar year for napa valley and California as seen below in the newspaper clipping:

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/6.png)

2007 had the lowest of the maximum averages, with an average rating of 4.43. The golden years of California wine production seemed to all be at the very end of the 20th century and at the beginning of the 21st century, between 1998 and 2011. 

After analyzing the important years in California wine production, we then explored arguably the most important aspect to value for money wine - price. The next step in our exploration was to scrape the different price points of red wine in California and start to make connections between the labels, the grapes, the wineries, the years of production, and the price. An example of the dataset we used can be seen below:

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/7.png)

With over 12,000 wines to analyze, we decide to group our wines into different price ranges and categories. The best way to do this was using intervals of $50 and plotting a bar graph to see which price points the majority of wines fell under. This distribution can be seen below:

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/s1.png)

As we can see, the majority of wine in California fell under the $0-50 price range. This makes a lot of sense, as most producers in the region would be focused on producing wine at scale to sell to the mass market. The average buyer of wine would not spend more than $50 on a bottle, either because they want something to consume quickly (and not store), or because they do not have the desire or understanding of wine to spend more than $50 on it. The wines over $100 would be purchased by those with a higher disposable income, for celebrations, and for consumers who fall under the “collector” category. For a value-for-money wine, the price would need to fit into the first “$0-50” category as most college students would not have a budget to spend more than that. 

After looking at the best years of wine production along with the price distribution, we dove into analyzing the ratings. Price, production year, and ratings would be the basis of our analysis before we explored further aspects such as pairings. 

It is important to note that all ratings are not verified. This will be explained further in our limitations of data, but for the sake of our analysis, we included all ratings made by Vivino users and produced this density graph:

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/8.png)

The key takeaway from this data is that most reviews for Californian red wine fall under the 3.8-4.0 category, which can be categorized as a high overall average. This range is considered “very good”, which means that any of the bottles falling under this range would result in an enjoyable drinking experience. 

The distributions of ratings were positive reaffirmation that red wine in California is greatly appreciated, which means that recommendations from this region for our peers would result in positive reactions. However, price is also an important factor when it comes to the appreciation of wine. We analyzed the correlation between price and rating, giving us the following data:

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/9.png)

To plot the correlation between the price and rating, we used a grid of 100 price points using the Poisson regression model to predict the corresponding ratings. The predicted ratings are then plotted as a line, and the actual data points are plotted as a scatter plot. The two plots are then displayed on the same graph, with a legend and axis labels added. We notice that there is no correlation between the price and ratings as the Poisson regression line doesn't fit in most of the points. 

Before we started looking at the pairings, we broke down the variety of grapes in California to provide an accurate representation of popularity. California is extremely well known for its Cabernet Sauvignon, Pinot Noir, and Merlot. The entire distribution, along with the “frequency” (number of wines containing these grapes) can be seen below:

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/10.png)

When looking at the distribution of the frequency of the grape varieties, we notice that both the Nebbiolo and the Sangiovese have very limited data when looking at our main datasets. In fact, there are only 2 wines that are produced with Nebbiolo while there is only 1 wine that is produced with Sangiovese. However, the Cabernet Sauvignon and the Pinot Noir have the highest frequencies, and both 4.1 and 4.2 in ratings respectively. Therefore, we can conclude that both of these grape varieties are the most popular in California (produced and sold to).

We also looked at the average rating for each grape and noticed some interesting observations:

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/11.png)

By looking at this graph, we notice that the highest ratings go to the grapes Nebbiolo, Cabernet Sauvignon, and Sangiovese respectively. Cabernet Sauvignon, the most popular red wine grape, is among the highest-rated in Vivino. However, we might think that the favorable climate for growing this grape variety, the increasing demand for premium wine, the recognition of its unique characteristics, and the growing popularity of Italian cuisine in the United States, the Nebbiolo might be the most sought-after red wine in the future. Similarly, the Sangiovese is shown to be as highly popular and it might be because of its unique ability to be correctly blended with other varieties of grape. Pinot Noir and Merlot are also highly rated, proving that mature grape varieties and vineyards do consistently well in California. 

To provide a thorough analysis of red wines in California, we also needed to scrape and see which wines provided the best options for vegetarian and steak pairing. Wine pairings are incredibly important because they act as a catalyst for amylase breakdown in the mouth. Essentially, food appears to taste better when consumed with wine because wine helps to break down fats in the mouth, producing more saliva. Red wine goes well with a variety of foods, but the secret of good pairings depends on the grape variety. Bolder wine styles such as Cabernet Sauvignon pair well with proteins such as steak, lamb, and pork, while vegetables and vegetarian food work better with grenache. 

We broke down the top 10 wines that go well with both vegetarian food and meat (in this instance, steak). We used the rating as a variable to define whether a wine worked well with vegetarian food, describes as “pasta, legumes, vegetables, fruit, and seeds”. The top 10 wine pairings were:

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/12.png)

As we can see, all of these wines are either a Grenache or Tempranillo. Both these grapes originate in Spain, and thrive in warm climates with elevation. California provides these traits - with 300+ days of sunshine and close proximity to the sea, these two grapes are fairly easy to grow on the west coast of the US. The lack of tannins in both of these grapes makes it extremely easy to pair with cheese, vegetable bakes, and legume-based dishes. 

For steak, the outcome was entirely different. Cabernet Sauvignon is a bold wine style that helps cut through fats found in meats. Its high tannic nature allows it to break down fats in the mouth, making steak “juicer” in the mouth. Additionally, Tannins soften the meat, allowing it to create more flavor in the mouth. 

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/13.png)

Cabernet Sauvignon almost dominates the chart, with the exception of a Syrah which is a similar style to Cabernet Sauvignon and high in tannic nature. 

Overall, we have managed to use different metrics to analyze red wine produced in California. Our dataset was robust, with over 12,000 wines scraped. Using price, ratings, year of production, regions, grape variety, and pairings, we were able to narrow down our “value for money” recommendations to 6 wines for every price category and occasion.


# Methodology

The dataset that we took was a scraped dataset from vivino.com. Today, Vivino is the largest wine marketplace in the world. When scraping the dataset, we made sure to add pre-set conditions (filters) to be able to have a specific dataset for wines produced in California. 

In our main dataset, we scraped all the results from the preset conditions (see above) and then divided the dataset into different columns to be able to conduct a better analysis. When looking into each specific wine in Vivino, we see 8 main characteristics that differentiate one wine from the other. We started by analyzing the years of production to be able to get the top years of production based on rating. This part was straightforward as we used selenium to scrape all the data. We also imported the time library in order to wait for the page to load. For each new page that loads, we get new data formed of 25 wines. However, we needed to calculate the height of the first page and write a function to compare it to the next page that loads. If the heights are the same, the web driver keeps scrolling and scraping data. However, when the height is not the same anymore, the web driver stops because we have reached the last page. We also furthered our analysis by getting into which wines pair the best with which type of food and which grapes are the most popular in California. For the grapes, we have also used selenium to be able to click on every single wine and extract the name of the grape. This part was a bit challenging because it required an extra step by clicking on every single wine and waiting for the data to be fetched. We needed to create a different dataset that only had the grapes of all the wines, with their ratings and their review counts. In that way, we were able to analyze and provide different graphs that currently portray the different grapes that are cultivated in the region and how popular they are. 

When coming to food pairings, we decided to switch to the API because we wanted to explore a new way of data scraping. The use of the API took a bit of time as it required the right configuration of the parameters. We used many resources on the internet to be able to overcome the errors that the API was giving while trying to play with it. For example, we faced a problem with the number of requests. In fact, we had to put in the number of requests that we need the API to perform, and to find that we had to divide the results of wine after putting our filters by 25 (maximum number of results for each page). The advantage of using the API is that it is also smart enough to deal with the last page because even if it is less than 25, it just produces the data that is out there without an error. Similar to the analysis of the grape, we created two different datasets, one for vegetarian and another one for beef steak. 

In terms of data cleaning, we were fortunate enough to get correct data and no missing values. The variables are consistent across the whole dataset as they follow the same format. In order to analyze and plot our data, we used python : pandas, seaborn, numpy, matplotlib. 

# Limitations

Although our model is robust, there are some clear limitations to it. First of all, we could not extract every characteristic of red wine. This is because scraping certain characteristics such as oakiness, the presence of red fruit, the presence of tobacco, etc would require us to go to every individual page of wine and scrape this information. Because we had over 12,000 wines in our data set, scraping each individual page would be extremely time-consuming and counterproductive. But, because we didn't scrape every characteristic, it does mean that our model and results have room for improvement. If we had looked at each individual page, there is a chance that our results would have differed slightly. Additionally, our filters only allowed the price of wine to range from $0-$500. Although this would not affect our model to a large extent (as we were looking specifically for value-for-money wine), it would have increased the number of wines in our dataset, allowing for more complex analysis. Furthermore, since Vivino is an active site, the number of wines uploaded and reviewed changes frequently. This means that over the course of our project, it is possible that the number of reviews could have increased for a wine that was close to being the best wine, as the review count was an important asset to the algorithm. Lastly, there is an inherent bias in the data set because reviews in Vivino are not verified. 

# Conclusion & Results: 

The aim of this project was to provide wines that our college peers could afford and enjoy without breaking the bank. The three wines that came out on top are commercially sold in supermarkets worldwide, have a great reputation amongst the wine community, and are cabinet staples that always deliver, no matter the vintage. These wines can be seen below:

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/14.png)

**Meiomi Pinot Noir -**

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/15.png)

|       Name       |       Price       |       Reviews       |       Review count       |       Grape         |
|:-------------|:------------------|
| Meiomi Pinot Noir         | $17.99  | 2005  | 16347  | Pinot Noir  |

**Bonanza Cabarnet Sauvignon Lot N.V**

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/16.png)

|       Name       |       Price       |       Reviews       |       Review count       |       Grape         |
|:-------------|:------------------|
| Bonanza Cabernet Sauvignon       |  $16.98  | N.V  | 26546  | Cabernet Sauvignon   |

**1000 Stories Zinfandel 2017**
![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/17.png)

|       Name       |       Price       |       Reviews       |       Review count       |       Grape         |
|:-------------|:------------------|
| 1000 stories Zinfandel     |  $19.99  | 2017  | 9521  | Zinfandel   |

We used three characteristics to derive our top three “value for money” wines - price, review count, and overall rating. The conditions we used were as follows:

|       Price       |       Review Count       |       Rating       |
|:-------------|:------------------|
| >$15 & <$25     |  Ascending Order  | > 4  |

We chose a rating of 4 because, for the price point, any wine rated above 4 is rare. We also chose our $15 - $25 price range because any wine below 15 would have not made the 4+ rating. We needed our review count to be in ascending order because the higher the review count, the more likely it would be enjoyed by anyone purchasing the bottle. A screenshot of our code can be seen below:

![Octocat](https://raw.githubusercontent.com/hamzads105/test/main/images/18.png)

When we were studying in the US, we managed to try all three of these wines (as they are commercially sold in supermarkets) and were extremely surprised to see the same wines on our list. Meoimi is an extremely popular wine, and our personal favorite out of the three. It is easy to drink, affordable, and provides the best value for money from the Californian market.

Appendix:
https://econlife.com/2020/01/wine-consumption-changes/
\https://en.wikipedia.org/wiki/Vivino
https://napavintners.com/press/press_release_detail.asp?ID_News=28
https://www.vivino.com/GB/en/meiomi-pinot-noir/w/1136137
https://www.vivino.com/GB/en/bonanza-california-cabernet-sauvignon-lot/w/6886895
https://www.vivino.com/GB/en/ten-zero-zero-stories-zinfandel/w/2918277




