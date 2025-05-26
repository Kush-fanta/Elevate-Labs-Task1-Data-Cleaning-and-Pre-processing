

# Titanic Dataset Preprocessing

This project demonstrates basic preprocessing steps on the Titanic dataset using Python and pandas.

## Steps Performed

1. **Importing the Dataset**
   - The dataset is loaded using `pandas.read_csv()`.

2. **Handling Missing Values**
   - Missing values in the `Age` column are filled using the forward fill method (`ffill`), which replaces missing values with the previous non-null value.

3. **Dropping Unnecessary Columns**
   - The `Cabin` column is dropped as it contains many missing values.

4. **Encoding Categorical Data**
   - The `Sex` column is converted to a numerical format where `male` is mapped to `1` and `female` to `0`.

5. **Normalizing Fare**
   - The `Fare` column is normalized using Min-Max normalization:
     ```
     Fare = (Fare - Fare.min()) / (Fare.max() - Fare.min())
     ```

6. **Visualizing Outliers**
   - A boxplot and histogram are plotted to visualize the distribution of the `Fare` column and detect outliers.

7. **Removing Outliers**
   - Outliers in the `Fare` column are removed using the Interquartile Range (IQR) method:
     - Calculate Q1 (25th percentile) and Q3 (75th percentile)
     - Compute IQR = Q3 - Q1
     - Define lower and upper bounds:  
       `lower_bound = Q1 - 1.5 * IQR`  
       `upper_bound = Q3 + 1.5 * IQR`
     - Filter the dataset to keep only rows within these bounds

## Result

The resulting DataFrame `df_no_outliers` contains the cleaned and normalized dataset with outliers removed from the `Fare` column.
