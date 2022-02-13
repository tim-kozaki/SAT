# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Test Analysis

## Problem Statement
As part of JustHangOn Consulting Group, we have been tasked by the United States Education Department to provide recommendations to increase participation rate and score to maintain competitiveness and relevants world wide. 

This study will analyze the trends and provide key insights on:
- State
- Race
- College Major
- Household Income
- State Income
- Fee Waiver / Grant


## Contents:
- 1.0	Import Libraries
- 2.0	Data Import and Cleaning
- 2.1	Dataframe Overview
- 2.1.1	SAT Scores for 2017
- 2.1.2	SAT Scores for 2018
- 2.1.3	SAT Scores for 2019
- 2.1.4	SAT Scores by Parent’s Highest Qualifications
- 2.1.5	SAT Scores by Nationality/Race for 2019
- 2.1.6	Number of High School Graduates Projections by Knocking at the College Door
- 2.2	Checking for Missing (null) Values & Data Errors
- 2.3	Fixing Errors
- 2.4	Rename Columns
- 2.5	Export DataFrames to CSV
- 3.0	Data Dictionary
- 4.0	Exploratory Data Analysis
- 5.0	Visualize the Data
- 6.0	Conclusions and Recommendations


## Background
The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). They have different score ranges, which you can read more about on their websites or additional outside sources (a quick Google search will help you understand the scores for each test):
* [SAT](https://collegereadiness.collegeboard.org/sat)
* [ACT](https://www.act.org/content/act/en.html)

Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from sudents' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude ([*source*](https://www.minotdailynews.com/news/local-news/2017/04/a-brief-history-of-the-sat-and-act/)). Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry. Lately, more and more schools are opting to drop the SAT/ACT requirement for their Fall 2021 applications ([*read more about this here*](https://www.cnn.com/2020/04/14/us/coronavirus-colleges-sat-act-test-trnd/index.html)).


The below datasets were used in this project:

* [sat_2017.csv](./data/sat_2017.csv): 2017 SAT Scores by State ([*source*](https://reports.collegeboard.org/archive/sat-suite-program-results/2017/detailed-2017-reports))
* [sat_2018.csv](./data/sat_2018.csv): 2018 SAT Scores by State ([*source*](https://reports.collegeboard.org/archive/sat-suite-program-results/2018/class-2018-results#:~:text=2.1%20million%20SAT%20test%20takers,weekend%20administration%20of%20the%20SAT))
* [sat_2019.csv](./data/sat_2019.csv): 2019 SAT Scores by State ([*source*](https://reports.collegeboard.org/archive/sat-suite-program-results/2019/state-results))
* [sat_2019_parents.xlsx](./data/sat_2019_parents.xlsx): 2019 SAT Scores by Parent's Highest Qualifications ([*source*](https://reports.collegeboard.org/archive/sat-suite-program-results/2019/state-results))
* [sat_2019_race.xlsx](./data/sat_2019_race.xlsx): 2019 SAT Scores by Nationality/Race ([*source*](https://reports.collegeboard.org/archive/sat-suite-program-results/2019/state-results))
* [high_school_graduates_projection.xlsx](./data/high_school_graduates_projection.xlsx): Knocking At the College Door ([*source*](https://knocking.wiche.edu/))


## Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*object*|sat_2017 / sat_2018/ sat_2019 / parents_2019 / race_2019|State in the United States of America|  
|**participation**|*object*|sat_2017 / sat_2018/ sat_2019|State participation rate|
|**ebrw**|*integer*|sat_2017 / sat_2018/ sat_2019|State's average score for Evidence-Based Reading & Writing of SAT|
|**math**|*integer*|sat_2017 / sat_2018/ sat_2019|State's average score for Math section of SAT|
|**total**|*integer*|sat_2017 / sat_2018/ sat_2019|State's average score for SAT|
|**qualification**|*object*|parents_2019|Test taker's parents highest qualification|
|**rate**|*integer*|parents_2019|Number value quantify the parent's qualification level|
|**test_takers_no**|*integer*|parents_2019 / race_2019|Number of tester takers for SAT|
|**total_score**|*float*|parents_2019 / race_2019|SAT score|
|**erw_score**|*float*|parents_2019 / race_2019|Evidence-based Reading & Writing Score of the SAT|
|**math_score**|*float*|parents_2019 / race_2019|Math Score of the SAT|
|**benchmarks_both**|*float*|parents_2019 / race_2019|Test Taker achieved benchmarks for both Evidence-based Reading & Writing and Math|
|**benchmarks_erw**|*float*|parents_2019 / race_2019|Test Taker achieved benchmark for Evidence-based Reading & Writing|
|**benchmarks_math**|*float*|parents_2019 / race_2019|Test Taker achieved benchmark for Math|
|**benchmarks_none**|*float*|parents_2019 / race_2019|Test Taker failed to achieve any benchmarks|
|**t_1400**|*float*|race_2019|Number of test taker's that achieved SAT score between 1400 to 1600|
|**t_1200**|*float*|race_2019|Number of test taker's that achieved SAT score between 1200 to 1390|
|**t_1000**|*float*|race_2019|Number of test taker's that achieved SAT score between 1000 to 1190|
|**t_800**|*float*|race_2019|Number of test taker's that achieved SAT score between 800 to 990|
|**t_600**|*float*|race_2019|Number of test taker's that achieved SAT score between 600 to 790|
|**t_400**|*float*|race_2019|Number of test taker's that achieved SAT score between 400 to 590|
|**erw_700**|*float*|race_2019|Number of test taker's that achieved Evidence-based Reading & Writing score between 700 to 800|
|**erw_600**|*float*|race_2019|Number of test taker's that achieved Evidence-based Reading & Writing score between 600 to 690|
|**erw_500**|*float*|race_2019|Number of test taker's that achieved Evidence-based Reading & Writing score between 500 to 590|
|**erw_400**|*float*|race_2019|Number of test taker's that achieved Evidence-based Reading & Writing score between 400 to 490|
|**erw_300**|*float*|race_2019|Number of test taker's that achieved Evidence-based Reading & Writing score between 300 to 390|
|**erw_200**|*float*|race_2019|Number of test taker's that achieved Evidence-based Reading & Writing score between 200 to 290|
|**math_700**|*float*|race_2019|Number of test taker's that achieved Math score between 700 to 800|
|**math_600**|*float*|race_2019|Number of test taker's that achieved Math score between 600 to 690|
|**math_500**|*float*|race_2019|Number of test taker's that achieved Math score between 500 to 590|
|**math_400**|*float*|race_2019|Number of test taker's that achieved Math score between 400 to 490|
|**math_300**|*float*|race_2019|Number of test taker's that achieved Math score between 300 to 390|
|**math_200**|*float*|race_2019|Number of test taker's that achieved Math score between 200 to 290|
|**read_35**|*float*|race_2019|Number of test taker's that achieved Reading score between 35 to 40|
|**read_30**|*float*|race_2019|Number of test taker's that achieved Reading score between 30 to 34|
|**read_25**|*float*|race_2019|Number of test taker's that achieved Reading score between 25 to 29|
|**read_20**|*float*|race_2019|Number of test taker's that achieved Reading score between 20 to 24|
|**read_15**|*float*|race_2019|Number of test taker's that achieved Reading score between 15 to 19|
|**read_10**|*float*|race_2019|Number of test taker's that achieved Reading score between 10 to 14|
|**wl_35**|*float*|race_2019|Number of test taker's that achieved Writing & Language score between 35 to 40|
|**wl_30**|*float*|race_2019|Number of test taker's that achieved Writing & Language score between 30 to 34|
|**wl_25**|*float*|race_2019|Number of test taker's that achieved Writing & Language score between 25 to 29|
|**wl_20**|*float*|race_2019|Number of test taker's that achieved Writing & Language score between 20 to 24|
|**wl_15**|*float*|race_2019|Number of test taker's that achieved Writing & Language score between 15 to 19|
|**wl_10**|*float*|race_2019|Number of test taker's that achieved Writing & Language score between 10 to 14|


## Conclusions and Recommendations

Based on the analysis, SAT scores show a strong correlation to the education/qualifications of graduate's parents. 
Possible reasons could be better financial support for tutoring, college applications and tuition. Further investigation is required to understand this trend better. 

Although Asians make up a small portion of the overal test takers, they have the highest average SAT score, Evidence-based Reading and Writing scores, and Math scores. Their average scores is in an increasing trend each year from 2017 to 2019. 

White population make up the majority of test takers with SAT scores that are comparable to Asians. 

Hispanics/Latinos, Black/African Americans, Native American Indians require assistance to boost their average SAT scores. 

### Recommendation from other domains
My other teammates had covered the impact and corresponding recommendation from their study on race demographic , finanicial aid , states and college major. These will be summarised in the PDF / PPT slide decks in another document.

