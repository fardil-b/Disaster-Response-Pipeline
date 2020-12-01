# Disaster Response Pipeline Project
Analyze disaster data from Figure Eight to build a model for an API that classifies disaster messages

## Motivation
Following a disaster there are normally millions of communications either directly or via social media, right at the time when disaster response organizations have their least capacity to filter and then pull out the messages which are the most important. Furthermore, not all messages are relevant to the disaster response professionals (maybe 1 in 1000). The way that disasters are typically responded to, is that different organizations will take care of different parts of the problem. One organization will care about water, another about medical supplies, another will care about blocked roads…. Keyword searching might not be ideal; for example searching for the word “water”, might not necessarily match with someone who needs drinking water it may miss people who do not use the word “water” instead say the word “thirsty” . So supervised machine learning based approaches are going to be a lot more accurate that key word searching.

The main goal of this project is to build an app  that can help emergency workers analyze incoming messages and sort them into specific categories to speed up aid and contribute to more efficient distribution of people and other resources.
## Project Description
There are three components you'll need to complete for this project.

### 1. ETL Pipeline
write a data cleaning pipeline that:

- Loads the messages and categories datasets
- Merges and clean the two datasets
- Stores it in a SQLite database
### 2. ML Pipeline
write a machine learning pipeline that:

- Loads data from the SQLite database
- Use NLTK to build a text processing and machine learning pipeline 
- Trains and tunes a model using GridSearchCV
- Exports the final model as a pickle file
### 3. Flask Web App
- display the results in a Flask web app

## Files structure:
- process_data.py : ETL script to clean data into proper format by splitting up categories and making new columns for each as target variables.
- train_classifier.py : Script to tokenize messages from clean data and create new columns through feature engineering. The data with new features are trained with a ML pipeline and pickled.
- run.py : Main file to run Flask app that classifies messages based on the model and shows data visualizations.

### Instructions:
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
        ![terminal1](https://user-images.githubusercontent.com/61830624/100752406-dc840180-33e8-11eb-95e7-fb9d25c0a353.PNG)
        
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`
        ![terminal2](https://user-images.githubusercontent.com/61830624/100752518-ff161a80-33e8-11eb-8790-702886af8902.PNG)


2. Run the following command in the app's directory to run your web app.
    `python run.py`
         ![run_app](https://user-images.githubusercontent.com/61830624/100752653-22d96080-33e9-11eb-8575-e99a863c7f12.PNG)


3. Open another Terminal Window
    type `env|grep WORK´
     - ![terminal3](https://user-images.githubusercontent.com/61830624/100752987-84013400-33e9-11eb-9e26-8ba656f53f69.PNG)
    
4. In a new web browser window, type in the following:
      `https://SPACEID-3001.SPACEDOMAIN´
    
    For our example - https://view6914b2f4-3001.udacity-student-workspaces.com/
    
5. Access the web app:

    ![app-pic2](https://user-images.githubusercontent.com/61830624/100710669-5350d880-33b0-11eb-9320-170fa42abc35.png)

