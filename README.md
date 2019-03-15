# Sparkily-Customer-Churn-Prediction

### Table of Contents

1. [Project Motivation](#motivation)
2. [Feature Engineering ](#files)
3. [Model and Result](#use)
4. [Data Source](#source)

## Project Motivation<a name="motivation"></a>

Predicting churn rates is a challenging and common problem that data scientists and analysts regularly encounter in any customer-facing business. Additionally, the ability to efficiently manipulate large datasets with Spark is one of the highest-demand skills in the field of data.

In this project, I'll practice manipulating large and realistic datasets with Spark to engineer relevant features for predicting churn. I' ll also use Spark MLlib to build machine learning models with large datasets, far beyond what could be done with non-distributed technologies like scikit-learn.

Sparkify is a music app, this dataset contains two months of sparkify user behavior log. The log contains some basic information about the user as well as information about a single action. A user can contain many entries. In the data, a part of the user is churned, through the cancellation of the account behavior can be distinguished.


## Feature Engineering<a name="use"></a>
1. Original fields in the raw dataset:  
**userId**: unique identifier for each user  
**firstName**: demographic information of each user  
**lastName**: demographic information of each user  
**location**: demographic information of each user  
**gender**: demographic information of each user  
**userAgent**: device that the user used  
**sessionId**:unique identifier for each session   
**itemInSession**: unique identifier for each page visited in a same session  
**page**: the specific page of website that the user visited, can be used to identify churn  
**song**: if the page is 'NextSong', this field will show the name of the song, otherwise only show 'null'  
**artist**: if the page is 'NextSong', this field will show the name of the artist, otherwise only show 'null'  
**level**: categorical features that only has 2 values, free or paid, showing the status of user     
**registration**: the timestamp of user registration  
**ts**: the timestamp of user action

2. By manipulating original fields, I create following features to predict customer churn:  
- **Session Related Feature :**  
**number of visited session**, **average visit time of each session**, **average gap days of sessions**   

- **Time Related Feature :**  
**days between first visit and last visit**, **days between most resent date and first visit date**,  
**days between most resent date and last visit date**  

- **Page View Related Feature:**    
**total number of visited pages**, **proportion of different types of visited pages**

- **Music Related Features :**  
**total number of listened songs**, **number of unique listened songs**, **number of unique artists listened**  

- **User Information :**   
**gender**, **device used**


## Model and Result<a name="use"></a>
Since this is a classification problem, so I choose common classification models including **Logistic Regression**, **Decision Tree** and **Random Forest**.  

In the original dataset, the churn rate is about 23%. So I use recall rate and precision rate of churn group on test dataset to compare model performance.  



## Data Source<a name="source"></a>
Must give credit to [Udacity](https://www.udacity.com/) for the data.

