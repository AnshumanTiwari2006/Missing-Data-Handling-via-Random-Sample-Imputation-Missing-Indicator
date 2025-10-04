🎲 Missing Data Handling via Random Sample Imputation & Missing Indicators
Preserving Data Distribution While Filling Gaps

A smart, distribution-aware approach to imputing missing values that maintains the original variance, shape, and statistical integrity of your features — far beyond simple mean or median filling.

✅ Ideal for datasets where preserving real-world variability is critical for unbiased modeling.

📌 Overview
This notebook explores Random Sample Imputation, a powerful technique that replaces missing entries by drawing values at random from the observed data of the same feature. Unlike central-tendency methods, this approach keeps the original distribution intact — making it especially valuable for numerical and categorical features alike.

✨ Why It Stands Out

Maintains variance and covariance structure
Preserves distribution shape (confirmed via visual density plots)
Works seamlessly for both numerical and categorical data
Avoids the artificial “spike” at the mean/median that distorts model learning
🔍 Key Workflow Highlights

📊 Distribution Preservation
Instead of collapsing missing values to a single point (like the mean), random sampling pulls from the actual pool of existing values. This ensures the post-imputation feature closely mirrors the original in both spread and shape — validated through statistical summaries and kernel density estimates.

🔤 Categorical Consistency
The same logic applies to text-based features like Category or Stock: missing labels are replaced by randomly selected existing categories, preserving their natural proportions in the dataset. This prevents skewing class balances during preprocessing.

📈 Impact Assessment
The notebook includes side-by-side comparisons showing:

How mean/median imputation flattens variance and distorts distributions
How random sampling retains the original statistical profile
Why this leads to more reliable and generalizable models
💡 Key Takeaways for Data Scientists

🧪 Imputation is transformation: Every method changes your data — always validate its impact
📏 Prefer median over mean for central-tendency imputation (robust to outliers)
🎯 Random Sample Imputation shines when data is Missing At Random (MAR) — it’s simple, effective, and statistically sound
🔒 Prevent data leakage: Always derive your imputation strategy (including the pool of values to sample from) only from the training set, then apply it consistently to test data
🛠️ Use pipelines: Scikit-learn’s fit/transform pattern enforces best practices automatically
🚀 When to Use This Method

Your feature has meaningful variance you don’t want to lose
You’re working with mixed data types (numeric + categorical)
You need a general-purpose, model-agnostic imputation strategy
Downstream models are sensitive to distributional shifts (e.g., linear models, clustering)
📬 Feedback & Contributions
Want to compare with KNN imputation, add missing indicator flags, or test on new datasets?
👉 Open an issue or submit a pull request — all contributions are welcome! 🤝
