## Preprocessing Folder

**The Kiana Data file is the data files used for preprocessing and the Dataframe Files Folder holds the pandas dataframes for each location.**

**The Data Preprocessing.ipynb file does the following:**

1. Read in the files from Kiana with December data
2. Read in the location data from Google Maps and Google Reviews (lat/long, average rating)
3. Group Kiana data by latitude/longitude and merge with location data to get all data for each key locatioin
4. Create pandas dataframes with columns: Rating, Floor_Level, MacID, and Time

**Implementation Details for Processing.ipynb:**

Set the **locations_info** variable to the file path of the file with the latitudes/longitudes and Google ratings of all locations.

Ex: locations_info = 'Location Data (1).csv'

Set the **path** variable to the file path of the folder with the data.

Ex: path="/Users/jerrytong/Desktop/USC/inf 560/tps2_181-211" where tps_181-211 is the folder with the relevant data files

---

## ML Models Folder

**Each of the 26 locations has its own .ipynb file that shows the outputs at each step.**

**Each file does the following:**

1. Format the timestamps
2. Compute the wait times
3. Compute the distance from the location to key airport gates
4. Bin the data into risk levels (low, medium, high) based on wait times
5. Split data into train and test set (80/20) --> training set to be used for 10-fold cross-validation
6. Train and test various models
7. Evaluate the models and choose the best one
8. Pickled best model

**The models that were tested were:**

1. Logistic Regression
2. RBF SVM
3. Naive Bayes
4. KNN
5. Random Forest

**Implementation Details:**

If the location's latitude/longitude has changed, set the **Location** variable to the location's latitude/longitude

Ex: Location = (-22.8153,-43.2448) where -22.8153 is the latitude and -43.2448 is the longitude.


Set the **pandas_file** variable to the file path for the file with the pandas dataframe for the location.

Ex: pandas_file = '/gdrive/Shared drives/INF560/Code/Data Files/Dataframes/data2-Palaphita.csv'


Set the **output_file** variable to the output file path for the pickle file.

Ex: output_file = '/gdrive/Shared drives/INF560/Code/Code Files/pickles/loc2model.pkl' where loc2model.pkl is the name of the pickle file.

---

## Pickle Files Folder

**Each location has its own pickle file for a total of 26 pickle files. These pickle files are created from the files in the ML Models folder.**

---

## UI Folder

**The UI folder contains all the code to integrate the back-end with the front-end web application. The HTML, CSS, JS files are stored in the INF560_Project folder while Pickle_tester.ipynb is stored separately.**

**Implementation Details for Pickle_tester.ipynb:**

Set the **rootPath** variable to the file path for the folder called 'app'

Ex: rootPath = '/content/drive/Shared drives/INF560/INF560_project/app'

Set the **file_path** variable to the file path for the folder called 'pickles' with all the pickle files

Ex: file_path = '/content/drive/Shared drives/INF560/INF560_project/pickles'

To view the dashboard, use the **ngrok.io** link that appears after doing: app.run()
