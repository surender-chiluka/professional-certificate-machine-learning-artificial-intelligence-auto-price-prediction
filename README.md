# Predict the Price of a used car?

##### Data analysis was done as a learning exercise of the Professional Certificate in Machine Learning and Artificial Intelligence - May 2023 offered via emeritus.org 
* This data is provided as part of course project is a subset of 426K cars information available in kaggle
  *	Vehicles data is available at: [data/vehicles.csv](data/vehicles.csv)
*	Data analysis and modeling in the Jupyter show cases some of the Data analysis and modeling taught in the course. 
  * [Jupyter Notebook](auto-price-prediction.ipynb)
  *	The data had a lot of missing data for different features
  *	Data is cleaned up in multiple steps
    *	Step 1 and 2 are used to parse the data for each missing(NaN) value for a feature and identify another data recorded that provided this value and used it reduce NaNs
    *	For these features of data - 'cylinders', 'fuel', 'transmission', 'drive', 'size', 'type', 
      *	used 'car' and 'model' to see if a values is available as part of another data entry.
    *	Similar identification and using 'manufacturer'  value based on the car 'model' feature.
    *	These step are implement in for loop and could take time.
    *	You could skip them and start at Step 3 of clean up
    *	Step 3 of clean up is dropping features and data entries the I decided to drop based on the data analysis and model adjusting.
    *	Some of the decision are purely based on time constraint to be able to finish the project in the time allocated.
    *	You can skip all the data clean up and start with modeling as the data is saved to csv and re loaded.
    *	In the data folder, you can see the 3 files that are generated at different steps of data clean up
*	Modeling is based on Ridge regression
  *	 Hot encoder is used for categorical features conversion
  *	 Polynomial features at degree 2 is used
  *	 StandardScaler used for scaling the data
  *  GridSearchCV is used to identify the best alpha for Ridge Regression 
  *	 Model score is: .79%
  *	 4 cores are used with the parameter n_jobs = 4 with GridSearchCV. If this creates the problem, you can reduce the it or remove it all together. Fitting could take a long time without n_jobs	 
