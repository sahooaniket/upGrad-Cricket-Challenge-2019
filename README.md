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
The whole prediction for the games are based on simple EDA of various data and plots. No machine learning or prediction models have been used to reach at the results for teh prediction. Each prediction has been based solely on the data and the plots provided in the file stats/stats_2015. Even though the data had been collected starting from 2000 only data after year 2015 has been used to derive at the results because most of the players involved in the current series are new and any records beyond the past 3 years is not going to provide any insights into the current form of the team. Only for the ground stats the records have been used starting from 1800's.

Prediction
-
Please refer the file Stats/Stats_2015 (https://github.com/sahooaniket/upGrad-Cricket-Challenge-2019/blob/master/Stats/Stats_2015.pdf) for the various plots. Based on those plots below are the inferences being drawn and the final prediction being made
