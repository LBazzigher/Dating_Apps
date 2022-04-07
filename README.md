# Dating_Apps
Project Data Analytics for Psychology and Business

## Questions / to discuss:

  1. Text Text Text
  2. Text Text Text
     
## Research question: 
**What can we learn from user ratings about dating apps?**

- How are the different apps rated over the years?
- Which app has more favorable responses? Have those favorable responses stayed   consistent through the years or have they increased/decreased?
- Do the app-ratings/comments distinguish from each other?
- What are the common issues for those who rate the app below 3/5?
- Are top rated reviews being found more useful to other users/potential users or the reverse?

## Relevance
The goal of this project is to analyze how the user view has developed over the years.Therefore an analysis of the rating, the user comments and the Number of Thumbs up received by a person will be made. We hope that this project will help app developers or investors who want to improve their dating app or pick out the next big dating app.

## Data
The data set contains information of four different dating apps. 

| App | cases  | timescale  |
| :---:   | :-: | :-: |
| Tinder | >500'000 | 2013 - 2022 |
| Bumble | >104'000 | 2015 - 2022 |
| OkCupid | >127'000 | 2010 - 2022 |
| Hinge | >53'000 | 2017 - 2022 |

### Data cleansing

First, we had to install a package: 
<!-- blank line -->  
<details>
<summary markdown="span">Package</summary>
<!-- blank line -->    
install.packages("readxl")<br>
library(readxl)<br>  
</details>
<!-- blank line -->  
Then, we hat to upload the different data sets and merche them together.
<!-- blank line -->  
<details>
<summary markdown="span">Data sets</summary>
<!-- blank line -->  
Tinder <- read_excel(file.choose(), na = "NA")<br>
Bumble <- read_excel(file.choose(), na = "NA")<br>
OkCupid <- read_excel(file.choose(), na = "NA")<br>
Hinge <- read_excel(file.choose(), na = "NA")<br>
<!-- blank line -->
<br>
<!-- blank line -->
#Create full data set<br>
Dating_Data_all <- rbind(Tinder, Bumble, OkCupid, Hinge)<br>
</details>
<!-- blank line -->  
After this, we explored our data set. 
<details>
<summary markdown="span">Explore</summary> 
<!-- blank line -->   
str(Dating_Data_all)
</details>
<!-- blank line -->  
Some variables had to be renamed. 
<details>
<summary markdown="span">Rename</summary> 
<!-- blank line -->  
Dating_Data_all <- Dating_Data_all %>% rename(Date_Time = at) <br>
colnames(Dating_Data_all)
<!-- blank line -->
<br>
<!-- blank line -->
Dating_Data_all <- Dating_Data_all %>% rename(replied_Date_Time = repliedAt)<br>
colnames(Dating_Data_all)
</details>
<!-- blank line -->   
Also, the timestamp had to be changed to a date. 
<details>
<summary markdown="span">Change timestamp</summary>      
#Change Timestamp<br>
Dating_Data_all$Date <- as.Date(Dating_Data_all$Date_Time)<br>
Dating_Data_all$Date_Reply <- as.Date(Dating_Data_all$replied_Date_Time)
</details>
<!-- blank line -->  
The variables we had to drop. 
<details>
<summary markdown="span">Remove variables</summary>       
#Drop variables and create final data set<br>
Dating_App_Final <- within(Dating_Data_all, rm(Time, Date_Time, replied_Date_Time))
</details>
<!-- blank line -->  
And finally, we could save the new data file. 
<details>
<summary markdown="span">Save data</summary>    
#save Datafile<br>
write_csv2(Dating_App_Final, file="Dating_app_cleared.csv")<br>
save(Dating_App_Final, file = "Dating_app_cleared.Rdata")
</details>
<!-- blank line -->  
### Data exploration 
Here comes text

### Data analysis
Here Comes textr

## About the authors:
Lina, Arbnor & Laura 
