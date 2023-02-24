# LoL-international-vs-Tier1-Performances
This is a exploratory data analysis project for DSC80. This project explores the difference in performances of League of Legends teams on the international stage and the regional stages.

## Introduction
Our project will investigate the differences between the performances of League of Legends professional teams in 2022 on regional stages and international stages. Our research gives insight on how the performance of teams are influenced by the type of stage they are on. The dataset being used is a cleaned version of the data provided by https://oracleselixir.com/tools/downloads with rows and columns corresponding to our research focus. This dataset has 6548 total rows and 15 total columns. Each row in our dataset corresponds to a team's statistics in a certain game. 
The columns correspond to those statistics:
gametype states whether the game was played on a regional stage or international stage. 
gameid corresponds to identification number of the game played.
league corresponds to the league/tournament the game was from.
datacompleteness states whether or not the data collection process was completely successful for that particular game.
teamname corresponds to the name of the team
result declares whether or not a team won(1) or a team lost(0).
kills corresponds to the total sum of the kills of each player of the team. 
dragons corresponds to the total number of dragons the team killed over the course of the game.
elders corresponds to the total number of elder dragons the team killed over the course of the game.
heralds corresponds to the total number of rift heralds the team killed over the course of the game.
barons corresponds to the total number of baron nashors the team killed over the course of the game.
towers corresponds to the total number of towers the team destroyed over the course of the game.
visionscore corresponds to the total sum of the vision granted or denied by the players on the team. 
creepscore corresponds to the total sum of the minions and monsters killed by the players on the team.
