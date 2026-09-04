from google.colab import files
import pandas as pd
import matplotlib.pyplot as plt

# Upload the Hospital Dataset
uploaded = files.upload()

# Get uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Remove extra spaces from column names
df.columns = df.columns.str.strip()

# Create Scatter Plot
plt.figure(figsize=(8, 5))

plt.scatter(df["Age"], df["Bill_Amount"])

plt.title("Age vs Bill Amount")
plt.xlabel("Age")
plt.ylabel("Bill Amount")

plt.grid(True)

plt.show()<img width="822" height="434" alt="Screenshot 2026-09-04 202959" src="https://github.com/user-attachments/assets/580e73b3-9227-4205-a73d-b035cdd316db" />
