# App Rating Prediction

Analysis & Perdicting app rating using Python.

## Description

### Objective: 
Make a model to predict the app rating, with other information about the app provided.

### Problem Statement:

Google Play Store team is about to launch a new feature wherein, certain apps that are promising, are boosted in visibility. The boost will manifest in multiple ways including higher priority in recommendations sections (“Similar apps”, “You might also like”, “New and updated games”). These will also get a boost in search results visibility.  This feature will help bring more attention to newer apps that have the potential.

### Fields in the data –

App: Application name

Category: Category to which the app belongs 

Rating: Overall user rating of the app

Reviews: Number of user reviews for the app

Size: Size of the app

Installs: Number of user downloads/installs for the app

Type: Paid or Free

Price: Price of the app

Content Rating: Age group the app is targeted at - Children / Mature 21+ / Adult

Genres: An app can belong to multiple genres (apart from its main category). For example, a musical family game will belong to Music, Game, Family genres.

Last Updated: Date when the app was last updated on Play Store

Current Ver: Current version of the app available on Play Store

Android Ver: Minimum required Android version

### Steps to perform:

1. Load the data file using pandas.
2. Check for null values in the data. Get the number of null values for each column.
3. Drop records with nulls in any of the columns.
4. Variables seem to have incorrect type and inconsistent formatting. You need to fix them:
   i. Size column has sizes in Kb as well as Mb. To analyze, you’ll need to convert these to numeric.
   ii. Extract the numeric value from the column
   iii. Multiply the value by 1,000, if size is mentioned in Mb
5. Reviews is a numeric field that is loaded as a string field. Convert it to numeric (int/float).
6. Installs field is currently stored as string and has values like 1,000,000+. Treat 1,000,000+ as 1,000,000, remove ‘+’, ‘,’ from the field, convert it to integer
7. Price field is a string and has $ symbol. Remove ‘$’ sign, and convert it to numeric.
8. Sanity checks:
  i. Average rating should be between 1 and 5 as only these values are allowed on the play store. Drop the rows that have a value outside this range.
  ii. Reviews should not be more than installs as only those who installed can review the app. If there are any such records, drop them.
  iii. For free apps (type = “Free”), the price should not be >0. Drop any such rows.
9. Performing univariate analysis
10. Outlier treatment
11. Bivariate analysis
12. Data preprocessing
13. Train test split  and apply 70-30 split. Name the new dataframes df_train and df_test.
14. Separate the dataframes into X_train, y_train, X_test, and y_test.
15 . Model building
16. Use linear regression as the technique
17. Report the R2 on the train set
12. Make predictions on test set and report R2.
