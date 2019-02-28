# upGrad-Cricket-Challenge-2019
Analyse the ODI matches between IND and AUS 2019 and predict the results.

Data
-
The data was completely collected from the link http://stats.espncricinfo.com/ci/engine/stats/index.html. Data collected as below details.
  1. ODI Team data for the teams India and Australia (Innings by Innings List) starting from Jan 2000.
  2. ODI Team data for all matches in India (Innings by Innings List) starting from 1800's.
  3. ODI Team data for the teams India and Australia (Match Results) starting from Jan 2000.
  4. ODI Batting data for Players of India and Australia (Innings by Innings List) starting from Jan 2000.
  5. ODI Bowling data for Players of India and Australia (Innings by Innings List) starting from Jan 2000. 
  6. ODI Grounds and the countries to which these venues belong was compiled from the above datasets manually for only India and Australia 
  
Data Merging
-
  1. The dataset 1 and 2 were merged manually into one file using excel.
  2. The function merge_espn_data was used to merge the datasets (1+2) and 3 mentioned to get the final dataset Data.csv.
  
Data Cleaning
-
Each of the dataset had to undergo various cleaning steps as below
  1. Dropping the duplicate rows
  2. Converting the data to lowercase.
  3. Dropping the rows with unwanted data like DNB,TDNB,NA,TIE..etc.
  4. Removing special characters like * from the numeric columns.
  5. Removing character v from the opposition column.
  6. The data was stripped off their leadinga and trailing spaces.
  7. The date column was changed to datatime datatype column.
  8. All the numeric cloumns were converted to numeric datatype. 
  9. Column data was changed like 1 to 1st, 2 to 2nd etc. for better readability.
  10. New columns were derived based on the data as below.
    a. won and lsot from result
    b. score range from scores
    c. wickets from scores
    d. year from date
    e. series from ground
    f. country from player
    g. series from country
    
Plots
-
Seaborn plots are being used to provide a visualisation of the various data being used for the analysis. Various customized functions (for Team stats, Ground stats, Averages, Batting stats, Bowling stats etc.) have been built to plot graphs with values such as dataset, teams, venues, host_country, analysis_year, plot_type etc. provided as inputs. Typically the below plots are being used based on their requirement to represent any data effictively.
  1. Bar plot
  2. Horizontal Bar Plot
  3. Line Plot
  4. Point Plot
  5. Box Plot
  6. Swarm Plot
  
Analysis
-
The whole prediction for the games are based on simple EDA of various data and plots. No machine learning or prediction models have been used to reach at the results for teh prediction. Each prediction has been based solely on the data and the plots provided in the file stats/stats_2015. Even though the data had been collected starting from 2000 only data after year 2010 has been used for getting the match results and data after 2015 has been used to derive the player predictions because most of the players involved in the current series are new and any records beyond the past 5 to 10 years is not going to provide any insights into the current form of the team or player. Only for the ground stats the records have been used starting from 1800's.

Prediction
-
Please refer the file Stats/Stats_2015 (https://github.com/sahooaniket/upGrad-Cricket-Challenge-2019/blob/master/Stats/Stats_2015.pdf) for the player and Stats/Stats_2010 (https://github.com/sahooaniket/upGrad-Cricket-Challenge-2019/blob/master/Stats/Stats_2010.pdf) for the result related plots. Based on those plots below are the inferences being drawn and the final prediction being made.

Fig 1.1 Innings Stats (2010)
-
India: Prefers to bat 2nd (127/90)
Australia: Prefers to bat 1st (109/75)
Inference: India likes to chase and Australia like to defend.

Fig 1.2 Toss Stats
-
India: Almost equal chance of winning a toss (89/95)
Australia: Almost equal chance of winning a toss (114/103)
Inference: Both the teams have equal likely chances of winning the toss.

Fig 2.1  Win Percentage (against all teams)
-
India: Winning percentage has been on rise (63% to 78%)
Australia: Winning percentage is deteriorating (67% to 15%)
Inference: Currently, India's form is on rise and Australia's on fall. India has significantly high chance of winning a match.

Fig 2.2  Win Percentage (against each other)
-
Australia: Winning percentage is deteriorating (100% to 20%)
India: Winning percentage has been on rise (0% to 80%)
Inference: Though both the teams have won equal matches with each other (13/13). 
Current trend shows India has a upper hand in winning matches against Australia.
-

Fig 2.3 & 2.4  Win Percentage vs Toss (against all teams)
-
India: Winning percentage is high whenever the toss is won (72% as against 62% on losing the toss)
Australia: Winning percentage is low whenever the toss is won (54% as against 66% on losign toss)
Inference: India's chances of winning increases significantly with win of toss, while toss hardly matters for Australia, as it has higher win percentage even when they have lost the toss.

Fig 2.5  Win Percentage vs Toss (against each other)
-
Australia: Winning percentage is high whenever the toss is won (56%)
India: Winning percentage is high whenever the toss is won (60%)
Inference: Both teams' chance of winning increases with win of toss.Toss has a significant role in deciding the winner during a match between India and Australia but as both the teams have equal likely chance of winning the toss, so we can ignore the role of toss while predicting.

Fig 2.6 & 2.7  Win Percentage vs Innings (against all teams)
-
India: Winning percentage increases significantly while batting 2nd almost 10% than while batting 1st.
Australia: Winning percentage remains almost same while batting 1st or 2nd (only 4%-5% change) 
Inference: India's chances of winning increases significantly while batting second.

Fig 2.8  Win Percentage vs Innings (against each other)
-
India: Winning percentage increases significantly while batting 2nd almost 18% than while batting 1st.
Australia: Winning percentage increases significantly while batting 2nd almost 18% than while batting 1st.
Inference: Both teams' chance of winning increases significantly while batting second. Team batting second will have a better chance of winning a match between India and Australia.

Fig 2.9 & 2.10  Win Percentage vs Home/Away Series (against all teams)
-
India: Winning percentage increases significantly by 10% in home series (63% away to 73% at home)
Australia: Winning percentage increases drastically by 21% in home series (49% away to 72% at home)
Inference: Both teams' are pretty good at their home turfs with Australia doing far worse in away series than India.

Fig 2.11  Win Percentage vs Home/Away Series (against each other)
-
India: Winning percentage is pretty high 75%.
Australia: Winning percentage is pretty low 25%.
Inference: India has a very high chance i.e almost 75% of winning a series in India against Australia. This is almost like 3-2 series win for India

Fig 2.12  Win Percentage vs Scores (against all teams)
-
India: There is a fair chance of winning a match 60-80% for scores between 150-330 and 100% for scores more than 330.
Australia: There is a fair chance of winning a match 60-80% for scores between 250-350 and 100% for scores more than 380.
Inference: India has a very fair chance of winning a match with an average score above 250 while Australia has a fair chance of winning a match with an average score above 300.

Fig 2.13  Win Percentage vs Wickets (against all teams)
-
India: There is a fair chance of winning a match 60-80% till the loss of 6th wicket.
Australia: There is a fair chance of winning a match 60-80% till the loss of 8th wicket.
Inference: India tends to lose matches where it loses more than 6 wickets but Australia on losing 8 wickets.

Fig 2.14  Win Percentage vs Scores (against each other)
-
Inference: India tends to lose more matches for scores between 240 to 330 against Australia.

Fig 2.15  Win Percentage vs Wickets (against each other)
-
Inference: India loses matches where it loses more than 7 wickets against Australia.

Fig 3.1  Impact of Toss on grounds
-
Delhi: Significant role of toss. 61% win for team winning toss.
Hyderabad: Toss does not play any significant role.
Mohali: Significant role of toss. 58% win for team winning toss.
Nagpur: Significant role of toss. 59% win for team winning toss.
Ranchi: Toss does not play any significant role. As only 3 matches have been conducted here. Not enough to decide significance.

Fig 3.2 & 3.3 Toss on grounds (Both Teams)
-
Delhi: India has a equal chance of winning the toss (9/9). Australia has a equal chance of winning the toss (3/2). 
Hyderabad: India has a less chance of winning the toss (5/7). Australia has a equal chance of winning the toss (0/1).
Mohali: India has a pretty high chance of winning the toss (10/5). Australia has a equal chance of winning the toss (3/3). 
Nagpur: India has a equal chance of winning the toss (8/9). Australia has a good chance of winning the toss (4/2). 
Ranchi: India has a equal chance of winning the toss (1/2). Australia has a equal chance of winning the toss (0/0) as it has never played here. 

Fig 3.4  Impact of Innings on grounds
-
Delhi: Innings does not play any significant role on wins.
Hyderabad: Innings does not play any significant role on wins.
Mohali: Team batting first tends to win 62% of the matches.
Nagpur: Innings does not play any significant role on wins.
Ranchi: Innings does not play any significant role on wins.


Fig 3.5 & 3.6  Innings on grounds (Both Teams)
-
Delhi: India has batted 2nd more number times (8/11). Australia has batted 1st more number times (3/2).
Hyderabad: India has batted 2nd more number times (5/7). Australia has batted 1st more number times (3/0).
Mohali: India has batted 1st more number times (9/6). Australia has batted equally in the innings (3/3).
Nagpur: India has batted 2nd more number times (8/9). Australia has batted equally in the innings (3/3).
Ranchi: India has batted 2nd more number times (0/3). Australia has never played here.

Fig 3.7  Win Percentage on grounds (Both Teams)
-
Delhi: India has won 67% of matches played here. Australia has won 40% of matches played here.
Hyderabad: India has won 67% of matches played here. Australia has won 67% of matches played here.
Mohali: India has won 67% of matches played here. Australia has won 83% of matches played here.
Nagpur: India has won 53% of matches played here. Australia has won 50% of matches played here.
Ranchi: India has won 67% of matches played here. Australia has never played here.

Fig 4.1  Wickets Lost (Both Teams)
-
India: Loses on average 7 wickets in 1st innings and 5 wickets in 2nd innings.
Australia : Loses on average 6 wickets in 1st innings and 7 wickets in 2nd innings.

Fig 4.2  Scores (Both Teams)
-
India: Scores on average 297 in 1st innings and 254 wickets in 2nd innings.
Australia : Loses on average 301 in 1st innings and 231 wickets in 2nd innings.

Fig 4.3  Scores on grounds
-
Delhi: Average 1st innings score of 239 and 2nd innings score of 211.
Hyderabad: Average 1st innings score of 253 and 2nd innings score of 214.
Mohali: Average 1st innings score of 268 and 2nd innings score of 228.
Nagpur: Average 1st innings score of 278 and 2nd innings score of 246.
Ranchi: Average 1st innings score of 233 and 2nd innings score of 228.

Fig 4.4 - 4.8 Scores on grounds (Both Teams)
-
Delhi: India : Average 1st innings score of 244 and 2nd innings score of 217.
Delhi: Australia : Average 1st innings score of 253 and 2nd innings score of 232.
Hyderabad: India : Average 1st innings score of 298 and 2nd innings score of 238.
Hyderabad: Australia : Average 2nd innings score of 238.
Mohali: India : Average 1st innings score of 283 and 2nd innings score of 230.
Mohali: Australia : Average 1st innings score of 232 and 2nd innings score of 280.
Nagpur: India : Average 1st innings score of 306 and 2nd innings score of 261.
Nagpur: Australia : Average 1st innings score of 303 and 2nd innings score of 206.
Ranchi: India : 2nd innings score of 228.
Ranchi: Australia : Has not played.

As per the analysis from plots 1 to 4
-
India will win the series by 3-2
-
Delhi: Australia
-
Hyderabad: India
-
Mohali: Australia
-
Nagpur: India
-
Ranchi: India
-

As per the analysis from plots 5
-
Virat Kohli will be the highest run getter.
-
As he has the highest average against against Australia in India. The Box plots give a better idea why he will get more runs than others. Aaron Finch has not been considered due to the less number of matches being played by him in India.

As per the analysis from plots 5
-
Virat Kohli will hit the highest number of 4s.
-
As he has the highest number of fours against Australia in India. The Bar plots give a better idea why he will be better than others. Aaron Finch has not been considered due to the less number of matches being played by him in India.

As per the analysis from plots 5
-
Rohit Sharma will hit the highest number of 6s.
-
As he has the highest number of sixes against Australia in India. The Bar plots give a better idea why he will be better than others. Aaron Finch has not been considered due to the less number of matches being played by him in India.

As per the analysis from plots 6
-
Coulter Nile will be the highest wicket taker.
-
As he has a consistent average of 2 wickets in all the stats considered in plots 6.
