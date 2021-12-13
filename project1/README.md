# Project 1: Effects of family income on test scores in California

### Problem Statement

There is an increasing education gap between the rich and poor [(source)](https://www.forbes.com/sites/nickmorrison/2019/12/17/higher-education-gap-between-rich-and-poor-reaches-10-year-high/?sh=2cc772f9749a) . The primary aim of this project is to help educational institutes and governments with resource and policy planning, to make education more accessible and equitable. It will analyze if the income gap has an effect on standardized testing, by examining the state of California as it is one of the more populous states. 

-----
### Contents:
- [Background](#Background)
- [Data Import & Cleaning](#Data-Import-and-Cleaning)
- [Exploratory Data Analysis](#Exploratory-Data-Analysis)
- [Data Visualization](#Visualize-the-Data)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations)
-----

### Background
The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). They have different score ranges, which you can read more about on their websites or additional outside sources (a quick Google search will help you understand the scores for each test):
* [SAT](https://collegereadiness.collegeboard.org/sat)
* [ACT](https://www.act.org/content/act/en.html)

Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from sudents' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude ([*source*](https://www.minotdailynews.com/news/local-news/2017/04/a-brief-history-of-the-sat-and-act/)). Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry. Lately, more and more schools are opting to drop the SAT/ACT requirement for their Fall 2021 applications ([*read more about this here*](https://www.cnn.com/2020/04/14/us/coronavirus-colleges-sat-act-test-trnd/index.html)).


### Datasets
The datasets chosen are 
* [`act_2019_ca.csv`](./data/act_2019_ca.csv): 2019 ACT Scores in California by School
* [`sat_2019_ca.csv`](./data/sat_2019_ca.csv): 2019 SAT Scores in California by School
* [California Census](https://en.wikipedia.org/wiki/List_of_California_locations_by_income) : 2014 Income and population information by county

#### Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|-----------|
|county|Object|All|Names of the counties in California state|
|sat_cohort|Integer|SAT (2018-2019)|Total number of students in grade 11 and 12|
|sat_testees|Integer|SAT (2018-2019)|Total number of students who took the SATs in grade 11 and 12|
|sat_participationrate|Float|SAT (2018-2019)|Percentage of students who took the SATs in grade 11 and 12|
|sat_erwmet|Integer|SAT (2018-2019)|Total number of students who met the ERW component benchmark|
|sat_mathmet|Integer|SAT (2018-2019)|Total number of students who met the Math component benchmark|
|sat_bothmet|Integer|SAT (2018-2019)|Total number of students who met both benchmarks|
|sat_bothpct|Float|SAT (2018-2019)|Percentage of students who met both benchmarks|
|act_cohort|Integer|ACT (2018-2019)|Total number of students in grade 12|
|act_testees|Integer|ACT (2018-2019)|Total number of students who took the ACTs in grade 12|
|act_participationrate|Float|ACT (2018-2019)|Percentage of students who took the ACTs in grade 12|
|act_avgtotal|Float|ACT (2018-2019)|Average score of the 4 components: English, Math, Reading and Science|
|act_above21|Integer|ACT (2018-2019)|Total number of students who scored above the benchmark of 21|
|act_pctabove21|Float|ACT (2018-2019)|Percentage of students who scored above the benchmark of 21|
|popt|Integer|[Wikipedia](https://en.wikipedia.org/wiki/List_of_California_locations_by_income)|Population of county|
|popt_dens|Integer|[Wikipedia](https://en.wikipedia.org/wiki/List_of_California_locations_by_income)|Population density (per square mile) of each county|
|income_percap|Integer|[Wikipedia](https://en.wikipedia.org/wiki/List_of_California_locations_by_income)|Income per capita in each county|
|income_median_hh|Integer|[Wikipedia](https://en.wikipedia.org/wiki/List_of_California_locations_by_income)|Median household income in each county|
|income_median_fam|Integer|[Wikipedia](https://en.wikipedia.org/wiki/List_of_California_locations_by_income)|Median family income in each county|


### Conclusion and Recommendations
<b>Conclusion: </b>
In this study, we have looked at 3 different data sets across the state of California. These data sets looked at ACT and SAT test scores, and family incomes per county. 

From the various analysis, there is a positive correlation between income per capita and test performances. Students in lower income families tend to perform worse compared to their higher income peers. This has also been supported by various research papers, which even states that public/private schools are not the determining factor of success. [(source)](https://www.wbur.org/hereandnow/2018/08/27/public-private-school-family-income-study)

We have also identified certain counties that have poor test performance and are in the lower income bracket. Should resources need to be allocated, these counties should get priority in order to improve education levels.


<b>Recommendations: </b>
There are a few counties that have consistently scored the lowest for both tests - Modoc, San Bernardino, Merced, Madera, Colusa, and Glenn. Of which, Merced and Madera are the counties with the lowest income per capita. The relevant authorities could look into these 2 counties first. 

For starters, it could be possible to look into specific schools or districts in these counties, and identify specific help required. Some immediate remedies could include subsidy for test fees to improve accessibility of education for the lower income. 

In addition, improvements to accessibility of education could also play a big part in improving educational levels during the time of COVID-19 and online learning. The digital divide has widened the educational gap between low and high income families [(source)](https://www.ppic.org/publication/who-is-losing-ground-with-distance-learning-in-california/) and resources to help to even out the playing field.

*Assumptions:* 
- Assume that income per capita does not change drastically over 5 years
- Assume that the effects of  family income is something that affects a student from young, and not only when a student takes their ACT/SAT