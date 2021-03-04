# Investigating how teen birth rate contributes to poverty rate 

## Background
Contraceptive measures have several health [benefits](https://www.healthline.com/health/birth-control-benefits) including regulation of menstrual cycle, reducing cancer rate, and reducing frequency of ovarian cysts, with minimal side effects. A recent [suggests](https://www.elle.com/culture/career-politics/news/a44005/women-cant-pay-more-than-10-for-birth-control/) that at least 33% of women are unable to pay for contraceptives, depending on the method chosen. While the Affordable Care Act has [routes](https://www.healthcare.gov/coverage/birth-control-benefits/) for individuals to obtain contraception, the Supreme Court recently upheld an [appeal](https://khn.org/news/high-court-allows-employers-to-opt-out-of-acas-mandate-on-birth-control-coverage/) that employers may deny contraceptive provisions to employees due to conflict with the religious beliefs of the employer. Further, despite the increased control and benefits given to women, [political feuds](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5678404/) continue to exist regarding government-funded contraception in addition to other healthcare provisions. The primary focus for opposition is [excessive spending](https://www.forbes.com/sites/jeffreydorfman/2014/01/23/why-some-people-oppose-expanding-government-aid-to-the-poor/?sh=6887b9442b85).

This analysis seeks to investigate the connection between teenage birth rate and poverty rate by comparing Baltimore, MD and Sussex County, DE. The population of Baltimore is approximately [593,000](https://www.census.gov/quickfacts/fact/table/baltimorecitymarylandcounty/AGE295219) and primarily politically [Democratic](https://www.bestplaces.net/voting/city/maryland/baltimore). The population of Sussex County is approximately [234,000](https://www.census.gov/quickfacts/sussexcountydelaware) and leans more [Republican](https://www.bestplaces.net/voting/city/delaware/lewes). As noted above, Republican voters tend to be against government-funded contraceptives and certain degrees of financial support with respect to food stamps, welfare, and Medicaid. Another goal of this analysis is to speculate on whether government spending could be reduced long-term if contraceptive provisions are provided.

## Business Question
__Can increasing access to affordable or government-funded contraception reduce the rate of poverty in Baltimore, MD?__

## Data Question - Open Data
All data from this analysis comes from the [Opportunity Atlas Project](https://www.opportunityatlas.org/) organized by tract. Files were downloaded for each location and combined into the files here:

- [Household Income](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/shown_tract_kfr_rP_gP_pall.csv)
- [Median Rent](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/shown_tract_median_rent2016.csv)
- [Fraction of Population in Poverty](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/shown_tract_poor_share2016.csv)
- [Fraction of Single Parents](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/shown_tract_singleparent_share2016.csv)
- [Frequency of Teen Births](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/shown_tract_teenbirth_rP_gF_pall.csv)
- [Percent married](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/shown_tract_married_rP_gF_pall.csv)

For detailed workflow, please see [data analysis](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/data-analysis-workflow.md)

## Data Question - Analysis
Microsoft Excel was used to answer the following:
1. __What factors are correlated with poverty rate in Baltimore, MD and Sussex County, DE?__ Key community metrics including median rent, teen birth rate, frequency of single parents, and percent married were compared between the municipalities using single and multiple linear regression analysis.
2. __Are teen mothers more likely to be single parents?__ Teen birth rate was compared to single parent frequency using simple linear regression.
3. __Are single parents more likely to be impoverished?__ Single parent frequency was compared to poverty rate using simple linear regression.

## Data Answer
__What factors are correlated with poverty rate in Baltimore, MD and Sussex County, DE?__
![error](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/Balt_poverty_mult_linear.png)

Multiple linear regression on Baltimore data shows that teen birth rate, single parent frequency and median income are significant predictors of poverty rate. Median income is logical, as the rent one can afford is dependent on income. Teen birth rate and single parent frequency are correlated (see below), so it is unsurprising that both are significant. 

![error](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/Sussex_poverty_mult_linear.png)

Contrary to Baltimore, the only variable which was significant in predicting poverty rate in Sussex County was median rent. As discussed above, the reason is probably entirely due to the fact that one's income determines what rent can be sustained. The only other value which was significant was the intercept, which suggests that there may be other variables that are significant predictors of poverty rate in Sussex County. For the remainder of the analyses, the expected chronology of events was taken into account (one must give birth in order to be a single parent). Correlations were therefore investigated between teen birth rate and single parent frequency as well as between single parent frequency and poverty rate.

__Are teen mothers more likely to be single parents?__
![error](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/teenbirth_singleparent.png)
![error](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/Balt_Sussex_plot_linear_regression_values.png)

In comparing teen birth rate to single parent frequency, the correlation is positive for both locations. For Baltimore, both the slope of the line of best fit is 2x that for Sussex County, indicating that for every 1% increase in teen birth rate, single parenthood frequency is expected to increase 2x what is observed for Sussex County. Further, the R-squared values for these data are 0.53 for Baltimore and 0.11 for Sussex County. 0.53 is a moderate relationship while 0.11 is quite weak. This indicates that in addition to the reduced slope for Sussex County, the correlation between teen births and single parenthood frequency is very poor.

__Are single parents more likely to be impoverished?__
![error](https://github.com/mehurlock94/comparing-baltimore-sussex-county-teen-birth-economic-outcomes/blob/main/singleparent_povertyrate.png)

In comparing single parent frequency to poverty rate, the correlation is positive for both locations, though the slope for Baltimore is 4x higher in magnitude than the slope for Sussex County. Strikingly, the R-squared value for Baltimore (0.44) is over 5x that of Sussex County (0.08). At face value, these indicate that single parent frequency is moderately correlated to poverty rate for Baltimore and very poorly correlated for Sussex County. In total, the data shown here suggest that teen birth rate and, subsequently, single parenthood are reasonably correlated for Baltimore, but not for Sussex County.

## Data Interpretation

This data highlights several striking differences between Baltimore and Sussex County. The multiple linear regression analysis showed that both teen birth rate and single parent frequency are significantly predictive of poverty rate, where these metrics are not significant in predicting poverty rate for Sussex County. Looking at pairwise relationships revealed that teen birth rate is moderately correlated with single parenthood in Baltimore but not so for Sussex County. Similarly, single parenthood is associated with poverty in Baltimore but not in Sussex County. One possible explanation is that teens who give birth in Sussex County are more likely to stay with their partner than in Baltimore. 











