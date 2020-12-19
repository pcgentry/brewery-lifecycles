# Life Cycle of a Beer.


## Possible Hypothesis: 

- There is an optimal lifecycle of a specialty brew based on the sales characteristics of past specialty brews
- There are indicators that show that some recipes are more optimal than others
- There is an optimal number of specialty brews to have at a given time based on sales
- There is an ideal mix of specialty brews in terms of variety
- Customers fit a profile based on tastes
- Customers of specific profile like a particular amount of variation

## Initial challenges
- obtaining data
- choosing what data to focus on
- Working with the brewery to get insight into what data would be most useful to them
- Sanitizing data such that personal data was not being compromised
- Addressing other privacy concerns around sensitive data being publicly available

## Motivation
- The part of data science that I am most passionate about is solving real world problems. I know that this brewery has been adversly affected by covid and it is a place that I personally care about. I wanted to help, and the thing that I can bring to the table there in particular that nobody else was equipped to do, is Data Science.
- Ultimately, the reason I chose to work on this is that the study of specialty brews was both interesting to me and it seemed like a great place to make an impact for this business.

## Data Collection
The data was collected directly from a real world point of sale software. It contained sensitive and personally identifiable information, so before I could publish the data I needed to replace names with computer generated names, as well as remove things like credit card info before even being able to consider exploring the data much or putting anything up on github that might be publicly visible.

I also spent some time cleaning the data. Concatenating seperate files of the same type, joining data sets that I knew I wanted relationships for, and removing extraneous data that would get in the way later.

## Purchases 
Purchases were categorized by line item and I wanted to look specifically at something that could have a positive impact on the business, so I chose to focus on what the pos

## Categorization
I split the brews into two categories.
- "Major" sets that were more or less on tap all the time or already have a place in rotation.
- "Minor" sets that were single runs or short runs. 

I split that data where I saw the first patterns of short term recipes showing up. That was at 710 beers sold. In the "Minor" group there was also the need to filter out beverages that were sourced from other companies and would not be expected to fit the same pattern as a specialty brew from this brewery.

## Exploration of approaches
In an attempt to narrow down a way to find indicators that a particular beer was a great success, I tried a lot of approaches.

Each beer was graphed on it's own and the graphs were compared in several ways:
- the eyeball method
- linear regression
- poisson distributions
- A/B splitting with Poisson distribution

## I looked at the timeline
![test](images/sales_timeline.jpg)

## The lifecycle. How many days on tap?
This is a histogram of the lifecycle of a beer from release to end of life. From this we can see most beers falling between 20-50 days on tap, and some run all the way up to 100.
![test](images/eol_hist.jpg)

## The sales characteristics for each
I plotted each individual beers sales onto a chart to see what they were generally shaped like.
![test](images/sales_series.jpg)

## Stacked into ordinal days (starting at 0)
Since the data was sparse, it seemed worthwhile to create a stacked graph containing all the series to more directly compare them, along with the larger trend of beers from day 0.

What I saw was that there appears to be an overall trend downwards, and other than that the comparison looks to be fairly chaotic.

![test](images/sales_stacked.jpg)

## Can we look for improvement?
So in the next step I simplified the previous chart to only two points. An accumulation of the first part of a beers life, with the second part. I just wanted to see if there was a trend.

![test](images/a_b_trend.jpg)

## Poisson Distributions
This sales data was by nature a good fit for Poisson. So I graphed the Poisson distribution for each sale series. 

I graphed each day where sales were made with an alpha of .1. This creates a shadow of a graph that changes and moves over time. I wanted a visual of what happens over time with each data set.

The final Poisson distribution is in darker blue.

![test](images/poisson_shadow.jpg)

## Is it even significant?
Finally I split the beers into an A/B test where the first half of the lifecycle represented "A" and the second half of the life represented "B"

I calculated critical values and means for the hypothesis and there was very little reason to believe that there were any significant upward trends to be found whatesoever.

![test](images/poisson_crits.jpg)

## Conclusion
In the end I found a lot of chaos in the data. My ending thoughts are that answering a question such as this is either not possible with the data I have or with the skills I have.


