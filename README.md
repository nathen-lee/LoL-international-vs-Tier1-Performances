**By: Nathen Lee & Siddharth Vyasabattu**
# Introduction
Our project will investigate the differences between the performances of League of Legends professional teams in 2022 on regional stages and international stages. Our research gives insight on how the performance of teams are influenced by the type of stage they are on. The dataset being used is a cleaned version of the data provided by https://oracleselixir.com/tools/downloads with rows and columns corresponding to our research focus. This dataset has 6548 total rows and 15 total columns. Each row in our dataset corresponds to a team's statistics in a certain game.  
The columns correspond to those statistics:
- <mark>gametype</mark> states whether the game was played on a regional stage or international stage. 
- <mark>gameid</mark> corresponds to identification number of the game played.
- <mark>league</mark> corresponds to the league/tournament the game was from.
- <mark>datacompleteness</mark> states whether or not the data collection process was completely successful for that particular game.
- <mark>teamname</mark> corresponds to the name of the team
- <mark>result</mark> declares whether or not a team won(1) or a team lost(0).
- <mark>kills</mark> corresponds to the total sum of the kills of each player of the team. 
- <mark>dragons</mark> corresponds to the total number of dragons the team killed over the course of the game.
- <mark>elders</mark> corresponds to the total number of elder dragons the team killed over the course of the game.
- <mark>heralds</mark> corresponds to the total number of rift heralds the team killed over the course of the game.
- <mark>barons</mark> corresponds to the total number of baron nashors the team killed over the course of the game.
- <mark>towers</mark> corresponds to the total number of towers the team destroyed over the course of the game.
- <mark>visionscore</mark> corresponds to the total sum of the vision granted or denied by the players on the team. 
- <mark>creepscore</mark> corresponds to the total sum of the minions and monsters killed by the players on the team.

The question at hand: **Do teams perform differently depending on whether they are playing on a regional stage or on an international stage?**

# Cleaning and EDA (Exploratory Data Analysis)
## Data Cleaning 
As part of our project, we took several steps to clean and refine the data to make it more useful and accessible. Our process involved the following steps:

- We created a new column called 'creepscore' by combining the 'minionkills' and 'monsterkills' columns. This helped us to represent these measures more accurately and effectively.
- We streamlined the dataset by removing all irrelevant columns, and keeping only the most relevant ones for our analysis. These columns are: 'gameid', 'league', 'datacompleteness', 'teamname', 'result', 'kills', 'dragons', 'elders', 'heralds', 'barons', 'towers', 'visionscore', and 'creepscore'.
- To assess the performance of the teams, we developed a formula that incorporates several of the remaining columns. We then created a new column called 'performance' that reflects our calculations, giving us a reliable way to measure and compare team performance.
- Another step we took was to create a new column called 'gametype'. This column identifies whether the game played was international or regional, providing us with a valuable way to later on group by and analyze the data. 

| gametype      | gameid                | league   | datacompleteness   | teamname           |   result |   kills |   dragons |   elders |   heralds |   barons |   towers |   visionscore |   creepscore |   performance |
|:--------------|:----------------------|:---------|:-------------------|:-------------------|---------:|--------:|----------:|---------:|----------:|---------:|---------:|--------------:|-------------:|--------------:|
| international | ESPORTSTMNT03_2701896 | MSI      | complete           | T1                 |        1 |      23 |         2 |        0 |         2 |        1 |       10 |           175 |          840 |        167.65 |
| international | ESPORTSTMNT03_2701896 | MSI      | complete           | Saigon Buffalo     |        0 |      11 |         1 |        0 |         0 |        0 |        1 |           170 |          811 |         52.61 |
| international | ESPORTSTMNT03_2701916 | MSI      | complete           | Team Aze           |        0 |       2 |         2 |        0 |         1 |        0 |        2 |           162 |          858 |         55.88 |
| international | ESPORTSTMNT03_2701916 | MSI      | complete           | DetonatioN FocusMe |        1 |      14 |         2 |        0 |         1 |        1 |        8 |           230 |          842 |        155.92 |
| international | ESPORTSTMNT03_2701926 | MSI      | complete           | ORDER              |        0 |       9 |         0 |        0 |         0 |        0 |        3 |           149 |          875 |         49.1  |

## Univariate Analysis
<iframe src="assets/univariate.html" width=800 height=600 frameBorder=0></iframe>
The histogram presented displays the probability distribution of performance based on the game type, specifically, the stage of play (regional or international). Based on the plot, we can deduce that the likelihood of teams performing better on the regional stage is greater than that on the international stage.

## Bivariate Analysis
<iframe src="assets/bivariate.html" width=800 height=600 frameBorder=0></iframe>
The histogram presented shows the probability distribution of performance based on the game type, specifically, the stage they're playing on (regional or international). Based on the plot, we can infer that the likelihood of teams performing better on the regional stage is greater than that on the international stage.

## Interesting Aggregates

| teamname           |   international |   regional |   international - regional |
|:-------------------|----------------:|-----------:|---------------------------:|
| DRX                |        148.75   |    133.522 |                   15.2285  |
| DWG KIA            |        143.648  |    145.315 |                   -1.66705 |
| T1                 |        146.571  |    153.621 |                   -7.04987 |
| KT Rolster         |        129.254  |    136.913 |                   -7.65869 |
| MAD Lions          |        123.716  |    132.528 |                   -8.81172 |
| Liiv SANDBOX       |        103.511  |    119.649 |                  -16.1378  |
| Fnatic             |        120.183  |    139.615 |                  -19.4322  |
| Beyond Gaming      |        108.96   |    128.56  |                  -19.5995  |
| Evil Geniuses      |        122.945  |    144.628 |                  -21.6834  |
| Gen.G              |        131.599  |    156.39  |                  -24.7903  |
| G2 Esports         |        121.25   |    147.585 |                  -26.3359  |
| Saigon Buffalo     |        104.968  |    135.998 |                  -31.0307  |
| Rogue              |        105.187  |    140.531 |                  -35.3441  |
| LOUD               |        113.955  |    154.048 |                  -40.0932  |
| DetonatioN FocusMe |        114.675  |    156.186 |                  -41.5106  |
| RED Canids         |         91.1071 |    139.501 |                  -48.3934  |
| 100 Thieves        |         86.305  |    137.141 |                  -50.8356  |
| PSG Talon          |        100.079  |    154.216 |                  -54.1371  |
| Isurus             |         78.462  |    135.479 |                  -57.0175  |
| CTBC Flying Oyster |         79.59   |    147.402 |                  -67.812   |
| Cloud9             |         66.995  |    138.358 |                  -71.3626  |
| GAM Esports        |         85.245  |    156.643 |                  -71.3976  |
| Team Aze           |         59.7883 |    140.571 |                  -80.7827  |

To analyze the differences in team performance across regional and international stages, we got the data on only the teams that participated in both stages and created a pivot table. Using team names as the index and their performances in each stage as columns, we calculated the means using 'mean' as the aggregation function. Next, we added a new column by subtracting the mean performance value in the regional column from that in the international column (International vs Regional). This allowed us to compare the differences in the means of the performances for each team between the international and regional stages.

# Assessment of Missingness
## NMAR Analysis
We believe that the 'performance' column can be considered as not missing at random (NMAR) since it was generated using a formula that builds upon multiple columns, making 'performance' dependent on all of these columns.
## Missingness Dependency
In this section, we will perform permutation tests on certain columns to determine if the missingness of performance is dependent on a that particular column.
#### Datacompleteness Column
Before Permutation:
<iframe src="assets/dcmissing.html" width=800 height=600 frameBorder=0></iframe>

After Permutation:
<iframe src="assets/dcmissingperm.html" width=800 height=600 frameBorder=0></iframe>

Empirical Distribution of Test Statistics:
0.0066,
0.0058,
0.014,
0.0049,
0.0264,
0.0173,
0.0,
0.0108,
0.0075,
0.0024,
0.0133,
0.0083,
0.0173,
0.0165,
0.0074,
0.0083,
0.0173,
0.0049,
0.0116,
0.0116,
0.0041,
0.0075,
0.0009,
0.0281,
0.0149,
0.0173,
0.0166,
0.0289,
0.0041,
0.0099,
0.0024,
0.0017,
0.0058,
0.0207,
0.0074,
0.0042,
0.0075,
0.0042,
0.0058,
0.0231,
0.0033,
0.0091,
0.0083,
0.0115,
0.0149,
0.0355,
0.0041,
0.0091,
0.0049,
0.0124,
0.0041,
0.0206,
0.0115,
0.005,
0.014,
0.0042,
0.0124,
0.0149,
0.0042,
0.0207,
0.0091,
0.005,
0.0066,
0.0042,
0.0041,
0.0323,
0.0099,
0.0074,
0.0025,
0.0,
0.0265,
0.0157,
0.0041,
0.0099,
0.0223,
0.0141,
0.0397,
0.005,
0.0017,
0.0166,
0.0124,
0.0206,
0.005,
0.0141,
0.0166,
0.0042,
0.0025,
0.0191,
0.0099,
0.0075,
0.0133,
0.0157,
0.0191,
0.0133,
0.0173,
0.0,
0.0149,
0.0165,
0.0166,
0.0067

#### League Column
Before Permutation:
<iframe src="assets/lgmissing.html" width=800 height=600 frameBorder=0></iframe>

After Permutation:
<iframe src="assets/lgmissingperm.html" width=800 height=600 frameBorder=0></iframe>

#### Gametype Column
Before Permutation:
<iframe src="assets/gtmissing.html" width=800 height=600 frameBorder=0></iframe>

After Permutation:
<iframe src="assets/gtmissingperm.html" width=800 height=600 frameBorder=0></iframe>

#### Conclusions
Using permutation tests, we examined the missingness in the 'performance' column using 'datacompleteness', 'league', and 'gametype' columns. The null hypothesis was that the missingness in the 'performance' column was independent of any other columns, whereas the alternative hypothesis proposed that missingness in the 'performance' column was dependent on other columns. We repeatedly simulated 100 column shuffles and obtained p-values of <0.05 for 'datacompleteness' and 'league', but >0.05 for 'gametype'. As a result, we rejected the null hypothesis for 'datacompleteness' and 'league' columns, but failed to do so for the 'gametype' column. This implies that the missingness in the 'performance' column is dependent on 'datacompleteness' and 'league' columns, but we could not reach a conclusion for the 'gametype' column.

# Hypothesis Testing
- <mark>Null hypothesis</mark>: There is no significant difference between the performance of teams on the international stage and their usual performance.
- <mark>Alternative hypothesis</mark>: The performance of teams on the international stage is worse than their usual performance.
- <mark>Test statistic</mark>: Mean performance values. We chose this because this hypothesis is one-directional and the variable being measured is continuous.
- <mark>Significance level</mark>: 0.05

<iframe src="assets/hyptest.html" width=800 height=600 frameBorder=0></iframe>
