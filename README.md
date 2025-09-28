# Missing-Data-Handling-via-Random-Sample-Imputation-Missing-Indicator

4. Random Sample Imputation
Handling_Missing_Data_by_Random_Sample_Imputation.ipynb

This notebook introduces a statistically superior method that aims to preserve both the distribution and variance of the original data.

Method: Missing values are replaced by randomly selected values from the non-missing subset of the same feature.

Advantages over Mean/Median: This method helps to preserve the original variance and covariance because the imputed values are drawn from the actual distribution, not fixed at a single central point.

Analysis & Impact Assessment:

Random Sampling Implementation: It demonstrates how to calculate the number of missing values (null_count) and then sample that many non-missing values (dropna().sample(null_count)), ensuring replace=True for small datasets.

Variance Preservation: The notebook confirms that the variance (var()) of the imputed column remains nearly identical to the original column's variance.

Distribution Comparison: KDE Plots for Price and Rating  visually confirm that the original distribution shape is largely retained, unlike with mean/median imputation.

Categorical Application: The same logic is applied to categorical features (Category, Stock) to demonstrate how random sampling preserves the proportionality of categories, making it a highly effective general-purpose imputation strategy.

💡 Key Takeaways for Data Scientists
Imputation is a Data Transformation: Every imputation technique alters the original data. It is essential to analyze the impact on distributions, variance, and correlations.

Use Median over Mean: The median is almost always safer for numerical imputation as it is less susceptible to outliers.

Prefer Random Sample Imputation: For Missing At Random (MAR) data, Random Sample Imputation is highly effective because it helps maintain the original variance and distribution shape, leading to less biased model training.

Fit on Training, Transform on Test: Always calculate the statistical measures (mean, median, mode, or random sample pool) only on the training data and use those calculated values/samples to transform both the training and test sets. This prevents data leakage. Scikit-learn's fit_transform/transform methods enforce this best practice.
