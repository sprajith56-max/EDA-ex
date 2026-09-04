from google.colab import files
import pandas as pd
import matplotlib.pyplot as plt

# Upload Hospital Dataset
uploaded = files.upload()

# Get filename automatically
filename = next(iter(uploaded))

# Load dataset
df = pd.read_csv(filename)

# Remove extra spaces from column names
df.columns = df.columns.str.strip()

# Create Histogram for Age
plt.figure(figsize=(8, 5))

plt.hist(df["Age"], bins=10, edgecolor="black")

plt.title("Distribution of Patient Age")
plt.xlabel("Age")
plt.ylabel("Frequency")

plt.grid(True)

plt.show()<img width="702" height="418" alt="Screenshot 2026-09-04 202143" src="https://github.com/user-attachments/assets/74f96f45-66b6-47e6-935d-ac8bd0fa8b2d" />
