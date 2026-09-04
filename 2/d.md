import pandas as pd
import matplotlib.pyplot as plt

# Upload the dataset
from google.colab import files
uploaded = files.upload()

# Get uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Remove extra spaces from column names
df.columns = df.columns.str.strip()

# Create Box Plot
plt.figure(figsize=(6, 5))

plt.boxplot(df["Bill_Amount"])

plt.title("Box Plot of Hospital Bill Amount")
plt.ylabel("Bill Amount")

plt.grid(True)

plt.show()<img width="602" height="411" alt="Screenshot 2026-09-04 202622" src="https://github.com/user-attachments/assets/db69d0ad-7feb-4b6a-88a8-70910171508d" />
