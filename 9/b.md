import pandas as pd
from scipy.stats import ttest_ind

# Load the dataset
df = pd.read_csv("sports_dataset.csv")

# Create two groups
cricket = df[df["Sport"] == "Cricket"]["Score"]
football = df[df["Sport"] == "Football"]["Score"]

# Perform Independent Sample t-test
t_value, p_value = ttest_ind(cricket, football)

# Significance level
alpha = 0.05

print("t-value :", t_value)
print("p-value :", p_value)

# Conclusion
if p_value < alpha:
    print("\nConclusion:")
    print("Reject the Null Hypothesis (H0)")
    print("There is a significant difference between Cricket and Football scores.")
else:
    print("\nConclusion:")
    print("Fail to Reject the Null Hypothesis (H0)")
    print("There is no significant difference between Cricket and Football scores.")

    <img width="657" height="131" alt="Screenshot 2026-09-05 180831" src="https://github.com/user-attachments/assets/6be0614c-20eb-4519-b061-e5377651c411" />

