# Working with Tabular data
Tips for working with tabular data

## Dealing with missing values

`df.isna().sum` gives us the number of missing values in each column.

Instead of just removing the rows with missing data we should use this information and it might be more helpful for our model e.g.
* Make a column that tells if the value is missing or not for a specific column.
* Use some method to fill in the missing values.

Mostly just taking the mode of the column and replacing missing values with that works just fine instead of doing complex things.

`modes = df.mode().iloc[0]` returns the modes of each column in a dataframe.

`df.fillna(modes,inplace=True)` fills the missing values of each column with their mode.

## Dealing with Skewed or long tailed data

If we have data that is skewed to one side it creates problems for a **Linear Model** but it can be easily solved by taking the log of values

`np.log1p()` Return the natural logarithm of one plus the input array, element-wise.

## Random Forest

For More detail See:
* https://www.youtube.com/watch?v=AdhG64NF76E&t=350s
* https://github.com/fastai/fastbook/blob/master/09_tabular.ipynb

For **Tabular Data** Random Forests Mostly do very well.

Also If you have multiple **columns/features** you can get the most important/useful ones using `feature_importances_`

