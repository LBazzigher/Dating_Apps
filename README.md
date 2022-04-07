# Dating_Apps
Project Data Analytics for Psychology and Business

## Questions / to discuss:
```ruby
     1. Text Text Text
     2. Text Text Text
     end
     ```
## Research question: 
What can we learn from user ratings about dating apps?

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

<details>
  <summary markdown="span">Codes for the cleaning</summary>

  install.packages("readxl")
library(readxl)
Tinder <- read_excel(file.choose(), na = "NA")
Bumble <- read_excel(file.choose(), na = "NA")
OkCupid <- read_excel(file.choose(), na = "NA")
Hinge <- read_excel(file.choose(), na = "NA")

#Creat full data set
Dating_Data_all <- rbind(Tinder, Bumble, OkCupid, Hinge)

str(Dating_Data_all)

#Rename variables
Dating_Data_all <- Dating_Data_all %>% rename(Date_Time = at)
colnames(Dating_Data_all)

Dating_Data_all <- Dating_Data_all %>% rename(replied_Date_Time = repliedAt)
colnames(Dating_Data_all)

#Change Timestamp
Dating_Data_all$Date <- as.Date(Dating_Data_all$Date_Time)
Dating_Data_all$Date_Reply <- as.Date(Dating_Data_all$replied_Date_Time)

#Remove Rows that have score 0 in variable "Score"
subset(Dating_Data_all, score == 0)

#Drop variables and create final data set
Dating_App_Final <- within(Dating_Data_all, rm(Time, Date_Time, replied_Date_Time))

str(Dating_App_Final)

#save Datafile
write_csv2(Dating_App_Final, file="Dating_app_cleared.csv")
save(Dating_App_Final, file = "Dating_app_cleared.Rdata")

</details>


### Data exploration 
Here comes text

### Data analysis
Here Comes textr

## About the authors:
Lina, Arbnor & Laura 
