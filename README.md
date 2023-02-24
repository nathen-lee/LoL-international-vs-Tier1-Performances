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

# Data Cleaning 

|    | gametype   | gameid           | league   | datacompleteness   | teamname           |   result |   kills |   dragons |   elders |   heralds |   barons |   towers |   visionscore |   creepscore |   performance |\n|---:|:-----------|:-----------------|:---------|:-------------------|:-------------------|---------:|--------:|----------:|---------:|----------:|---------:|---------:|--------------:|-------------:|--------------:|\n|  0 | regional   | 8401-8401_game_1 | LPL      | partial            | Oh My God          |        1 |      13 |         2 |      nan |       nan |        1 |        8 |           162 |          nan |           nan |\n|  1 | regional   | 8401-8401_game_1 | LPL      | partial            | ThunderTalk Gaming |        0 |       6 |         1 |      nan |       nan |        0 |        3 |           155 |          nan |           nan |\n|  2 | regional   | 8401-8401_game_2 | LPL      | partial            | Oh My God          |        1 |      22 |         2 |      nan |       nan |        1 |        9 |           180 |          nan |           nan |\n|  3 | regional   | 8401-8401_game_2 | LPL      | partial            | ThunderTalk Gaming |        0 |       8 |         1 |      nan |       nan |        0 |        2 |           159 |          nan |           nan |\n|  4 | regional   | 8402-8402_game_1 | LPL      | partial            | FunPlus Phoenix    |        1 |      12 |         4 |      nan |       nan |        2 |       10 |           274 |          nan |           nan |
