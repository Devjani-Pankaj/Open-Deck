# Course Recommendation Engine based on online Study patterns

## Project Description
The project aims to recommend courses to students based on their study patterns and cognitive level. It was built as a part of my Specialization Project in Mca .
Trivially recommendations are made based on course ratings which leads to only highly rated courses being recommended. This approach ignores the fact that the cognitive level of the student might not be suitable for those courses.

Hence this recommendation engine takes the user activity of a user in courses he/she has already finished. Then it finds similar users who had shown similar patterns in activities in other courses.
Now those courses shall be recommended to the user where he/she shall be expected to complete the course as the course difficulty level matches his/her cognitive level.

This approach is a type of collaborative filtering approach to generate recommendations.

## Model Description
The model begins by processing extensive log files tracking a student's online activities. The **Input processing module** is designed to transform these logs into a functional feature matrix through a two-step conversion process. After this, the model assesses the cosine pairwise similarity among users based on these features, identifying those with similar behaviors. Ultimately, it generates a ranked list of top N recommendations. This functionality is encapsulated within a straightforward API constructed using the Flask framework.
## How to run the app
First you need to set the system path. You can do that by setting the project path in configs.py file

Now, while being in the directory containing server.py file type the following command:

`python3 server.py`

You will get a prompt to open your localhost where you can try out generating recommendations.

The app asks for an index value to randomly pick up an userID from the database. It asks for the number of recommendations to be generated as well. 
(The number is set between 1-100 based on the dataset size).

## Dataset used
The orignal dataset contained raw log files of uder activities. The orignal dataset can be found at http://moocdata.cn/data/user-activity.
I have added a sample of converted dataset which essentially is a feature matrix containing pairs of userID and courseID along with the frequency of different activities that the user performed in that course.

## Description of folders/modules

### Data
It contains the sample data to be used.

### Input Preprocessing 
The preprocessing.py module contains functions used for converting the initial log files to usable CSV files in usable form. 
Next it has the function to convert the raw data containing CSV file to feature matrix which is used by the model.

## Recommendation_Generator
The generator.py file contains the main model that generates the recommendation list.

## Author
Pankaj Devjani
#   O p e n - D e c k 
 
 
