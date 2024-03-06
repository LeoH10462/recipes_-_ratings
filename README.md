
# Getting the Data
Download the data here. You’ll download two CSV files:

RAW_recipes.csv contains recipes.
RAW_interactions.csv contains reviews and ratings submitted for the recipes in RAW_recipes.csv.
We’ve provided you with a subset of the raw data used in the original report, containing only the recipes and reviews posted since 2008, since the original data is quite large.

A description of each column in both datasets is given below.

RECIPES
For context, you may want to look at an example recipe directly on food.com.

Column	Description
'name'	Recipe name
'id'	Recipe ID
'minutes'	Minutes to prepare recipe
'contributor_id'	User ID who submitted this recipe
'submitted'	Date recipe was submitted
'tags'	Food.com tags for recipe
'nutrition'	Nutrition information in the form [calories (#), total fat (PDV), sugar (PDV), sodium (PDV), protein (PDV), saturated fat (PDV), carbohydrates (PDV)]; PDV stands for “percentage of daily value”
'n_steps'	Number of steps in recipe
'steps'	Text for recipe steps, in order
'description'	User-provided description
RATINGS
Column	Description
'user_id'	User ID
'recipe_id'	Recipe ID
'date'	Date of interaction
'rating'	Rating given
'review'	Review text
After downloading the datasets, you must follow the following steps to merge the two datasets and create a column containing the average rating per recipe:

Left merge the recipes and interactions datasets together.
In the merged dataset, fill all ratings of 0 with np.nan. (Think about why this is a reasonable step, and include your justification in your website.)
Find the average rating per recipe, as a Series.
Add this Series containing the average rating per recipe back to the recipes dataset however you’d like (e.g., by merging). Use the resulting dataset for all of your analysis. (For the purposes of Project 4, the 'review' column in the interactions dataset doesn’t have much use.)
Example Questions and Prediction Problems
Feel free to base your exploration into the dataset in Steps 1-4 around one of these questions, or come up with a question of your own.

What types of recipes tend to have the most calories?
What types of recipes tend to have higher average ratings?
What types of recipes tend to be healthier (i.e. more protein, fewer carbs)?
What is the relationship between the cooking time and average rating of recipes?
Feel free to use one of the prompts below to build your predictive model in Steps 5-8, or come up with a prediction task of your own.

Predict ratings of recipes.
Predict the number of minutes to prepare recipes.
Predict the number of steps in recipes.
Predict calories of recipes.
Make sure to justify what information you would know at the “time of prediction” and to only train your model using those features.

Special Considerations
Step 2: Data Cleaning and Exploratory Data Analysis
Some columns, like 'nutrition', contain values that look like lists, but are actually strings that look like lists. You may want to turn the strings into actual lists, or create columns for every unique value in those lists. For instance, per the data dictionary, each value in the 'nutrition' column contains information in the form "[calories (#), total fat (PDV), sugar (PDV), sodium (PDV), protein (PDV), saturated fat (PDV), and carbohydrates (PDV)]"; you could create individual columns in your dataset titled 'calories', 'total fat', etc.

Step 4: Assessment of Missingness
There are only three columns in the merged dataset that contain missing values; make sure you’re using the merged dataset for all of your analysis (and that you followed the steps at the top of this page exactly).
