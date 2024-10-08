# Census_2011

## Description

The 2011 census of India or the 15th Indian census was conducted in two phases. Census has been conducted in India since 1872 and 2011 marks the first time biometric information was collected. According to the provisional reports released on 31 March 2011, the Indian population increased to 1.21 billion with a decadal growth of 17.70%. Adult literacy rate increased to 74.04% with a decadal growth of 9.21%. The motto of the census was Our Census, Our Future.

## Problem statement

The task is to clean, process, and analyze census data. The goal is to ensure uniformity, accuracy, and accessibility of the census data for further analysis and visualization.

## Steps followed

-step 1 : From the given url the data is loaded into Colab notebook.

          'https://docs.google.com/spreadsheets/d/1YWdOUGGFy1h-WKuXtkiKDTm3jcEY4Y7XuSZt_rzXtgc/edit? 
           gid=1084285986#gid=1084285986'

-step 2 : script to download the csv file from local

         'import pandas as pd
          dataset=pd.read_csv('/content/census_2011 - census_2011.csv.csv')
          dataset'

-step 3 : For uniformity in the dataset and taking into consideration the census year,some columns are renamed.

-step 4 : The State/UT names are in all caps in the given census data. For uniformity across dataset, only the first 
          character of each word in the name is changed into upper case and the rest are into lower case.
          
-step 5 : In 2014 Telangana was formed after it split from Andhra Pradesh, Renamed the State/UT from “Andhra Pradesh” to 
          “Telangana” for the given districts.
          
-step 6 : In 2019 Ladakh was formed after it split from Jammu and Kashmir, Renamed the State/UT from “Jammu and Kashmir” to 
         “Ladakh” for the given districts. 
         
-step 7 : Some null values in the dataset are retrieved by using aggregation

-step 8 : Comparison of the amount of missing data before and after the data-filling process for each column is done.
         
        # count of missing values before cleaning

           null_count=dataset_old.isnull().sum()

           null_df=null_count.reset_index()
           null_df.columns=['column','Missing values']

        # count of missing values after cleaning

         null_count1=dataset.isnull().sum()

         null_df1=null_count1.reset_index()
         null_df1.columns=['column','Missing values']

        # finding the percentage of amount of missing data before data cleaning
         null_df['percentage_missing_value before_cleaning']=(null_df['Missing values']/len(dataset_old))*100

        # finding the percentage of amount of missing data after data cleaning
         null_df['percentage_missing_value after_cleaning']=(null_df1['Missing values']/len(dataset))*100

         null_df'

-step 9 : Pymongo installation 

         # pymongo installation
         !python -m pip install "pymongo[srv]"
      
-step 10 : The processed data is saved to mongoDB with a collection named “census”.

-step 11 : Sqlalchemy installation 

         # installing sqlalchemy to convert DataFrame into Database table
           !pip install sqlalchemy
           
-step 12 : Data is fetched from  mongoDB and uploaded to a relational database(SQLite) using python code.

-step 13 : Streamlit installation 

          # installing streamlit
            !pip install streamlit

-step 14 : Localtunnel installation 

          # localtunnel installation
            !npm install -g localtunnel
            
-step 15 : Sql queries are executed and output is shown on streamlit




          
