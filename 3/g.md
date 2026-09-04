import pandas as pd

# Load the dataset
df = pd.read_csv("hospital dataset.csv")

# Correct inconsistent values
df["Department"] = df["Department"].replace("cardiology", "Cardiology")

print(df)
<img width="768" height="202" alt="Screenshot 2026-09-04 205820" src="https://github.com/user-attachments/assets/ba1e120b-d15e-4b40-86b5-ed207241d201" />
