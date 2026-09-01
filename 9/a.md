import pandas as pd
from scipy.stats import ttest_ind

# Load the dataset
df = pd.read_csv("sports_dataset.csv")

# Create two groups
cricket = df[df["Sport"] == "Cricket"]["Score"]
football = df[df["Sport"] == "Football"]["Score"]

# Perform Independent Sample t-test
t_value, p_value = ttest_ind(cricket, football)

# Display results
print("t-value :", t_value)
print("p-value :", p_value)<img width="156" height="55" alt="Screenshot 2026-09-01 204246" src="https://github.com/user-attachments/assets/b4b82ab2-d205-4fba-bbf4-93b295af2e98" />
