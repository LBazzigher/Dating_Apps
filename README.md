# Dating_Apps
Project Data Analytics for Psychology and Business

## Questions / to discuss:

  1. How specific has the research question to be? 
  2. Text Text Text
     
## Research question: 
**What can we learn from user ratings about dating apps?**

- How are the different apps rated over the years?
- Which app has more favorable responses? <br>Have those favorable responses stayed   consistent through the years or have they increased/decreased?
- Do the app-ratings/comments distinguish from each other?
- What are the common issues for those who rate the app below 3/5?
- Are top rated reviews being found more useful to other users/potential users or the reverse?

## Relevance
Dating apps have become more and more important for singles all over the world. In comparison to the services which had come before, Tinder made dating simple, but it also, as studies have found, made it less about lasting connections and relationships and more about casual hook-ups and cheesy openers. 
<!-- blank line -->
<br>
<!-- blank line -->
By 2021 dating app revenues have increased every year since 2015, reaching $5.61 billion with over 323 million people worldwide using dating apps. This project picked four different dating apps to analyze which are somehow different in style and usage. 
<!-- blank line -->
<br>
<!-- blank line -->

<details>
<summary markdown="span">Tinder</summary>
<!-- blank line -->    
Tinder fundamentally changed online dating by removing the seriousness and giving users more control. 
</details>
<!-- blank line -->  
<br>
<!-- blank line -->

<details>
<summary markdown="span">Bumble</summary>
<!-- blank line -->    
Bumble is designed to give women control of the experience. Bumble was started by Tinder co-founder Whitney Wolfe Herd, who left after tensions at the company. Bumble is consideret the main rival in North Armerica.
</details>
<!-- blank line -->  
<br>
<!-- blank line -->

<details>
<summary markdown="span">OkCupid</summary>
<!-- blank line -->    
OkCupid features multiple-choice questions to match members. It is one of the older dating apps and is a U.S.-based, internationally operating online dating, friendship, and formerly also a social networking website and application. 
</details>
<!-- blank line -->  
<br>
<!-- blank line -->
<!-- blank line -->

<details>
<summary markdown="span">Hinge</summary>
<!-- blank line -->    
Hinge may have been destined to be one of the many dating app failures, but the team reformed the app for long-term relationships and has hit the ground running in North America.
</details>
<!-- blank line -->  
<br>
<!-- blank line -->
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
<br>
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
