# data-sourcing-challenge

## Technology Used 

| Technology Used | Resource URL | 
| ------------- |:-------------:| 
| Python | [https://www.w3schools.com/python/python_reference.asp](https://www.w3schools.com/python/python_reference.asp) | 
| Git | [https://git-scm.com/](https://git-scm.com/) | 

## Description 
In this project I extracted data from the NASA API, specifically from two sources—its GST data and its CME data—then merge the data together and compute the average time it takes for a CME to cause a GST. Later, this data can be used with Machine Learning models to create predictions.

## Code Example 

<---- We apply the extract_activityID_from_dict function to each row in the 'linkedEvents' column and created a new column called 'CME_ActivityID' using loc indexer, removing rows with missing CME_ActivityID, then define the extract_activityID_from_dict function, since we can't assign them to CMEs----->
         
     def extract_activityID_from_dict(event_dict):
         try:
        
         activity_id = event_dict['activityID']
         return activity_id
     except KeyError as e:
       
         print(f"KeyError: The key 'activityID' was not found in the dictionary. Error: {e}")
         return None  # Return None if the key is missing
     except Exception as e:
       
         print(f"An error occurred: {e}")
         return None


     gst_df_exploded['CME_ActivityID'] = gst_df_exploded['linkedEvents'].apply(lambda event: extract_activityID_from_dict(event))

 
     gst_df_exploded_cleaned = gst_df_exploded.dropna(subset=['CME_ActivityID'])


     gst_df_exploded_cleaned.reset_index(drop=True, inplace=True)


     gst_df_exploded_cleaned.head()


 <---- We converted gst_json to a Pandas DataFrame Keep only the columns: activityID, startTime, linkedEvents ----->

     gst_df = pd.json_normalize(gst_json)

     gst_df['activityID'] = gst_df['linkedEvents'].apply(lambda x: x[0]['activityID'] if x else None)

     gst_df = gst_df[["activityID", "startTime", "linkedEvents"]]

     gst_df.head()


<---- We converted the 'GST_ActivityID' column to string format then converted startTime to datetime format. renaming startTime to startTime_CME and activityID to cmeID, before dropping linkedEvents ----->

        
     cme_df_cleaned['GST_ActivityID'] = cme_df_cleaned['GST_ActivityID'].astype(str)

     cme_df_cleaned['startTime'] = pd.to_datetime(cme_df_cleaned['startTime'], errors='coerce')

     cme_df_cleaned.rename(columns={'startTime': 'startTime_CME', 'activityID': 'cmeID'}, inplace=True)

     cme_df_cleaned.drop(columns=['linkedEvents'], inplace=True)


     cme_df_cleaned.head()


## Challenges
This proved to be an exceptional challenge.. no pun intended. I was stuck at almost every step, due to the complexity of how to expand information from certain rows in the table, and merging two data frames. The learning curve with Panda's syntax. But with the aid of W3 schools and ChatGPT anything that I was unfamiliar with I was able to gain understanding about through these sources. This one hurt.



## Learning Points 
Best friends as follows: Google, W3, Geeks for geeks, Youtube and ChatGPT

## Author Info
Armand Araujo
Age: 29
Location: Las Vegas, NV

 
* [LinkedIn](https://www.linkedin.com/in/armand-araujo-a82ba2291/) 
* [Github](https://github.com/Armand57araujo) 


## Credits 

W3 Schools, chatgpt, MDN
