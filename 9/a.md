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
print("p-value :", p_value)

<img width="655" height="75" alt="Screenshot 2026-09-05 180606" src="https://github.com/user-attachments/assets/4f686cd2-6a3e-4431-9d26-299c054f77e8" />
