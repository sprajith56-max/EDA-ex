from google.colab import files
import pandas as pd
import numpy as np

# Upload the Sports dataset
uploaded = files.upload()
filename = next(iter(uploaded))

# Load dataset
df = pd.read_csv(filename)

# Rename the first column as Date
df.rename(columns={df.columns[0]: "Date"}, inplace=True)

# Convert Date column into datetime format
df["Date"] = pd.to_datetime(df["Date"], dayfirst=True)

# Sort by date
df = df.sort_values("Date").reset_index(drop=True)

# Calculate Rolling Mean (3-match window)
df["Rolling_Mean"] = df["Score"].rolling(
    window=3,
    min_periods=1
).mean()

# Calculate Rolling Standard Deviation
df["Rolling_SD"] = df["Score"].rolling(
    window=3,
    min_periods=1
).std()

# Display results
print(df[["Date", "Player", "Score", "Rolling_Mean", "Rolling_SD"]])
<img width="477" height="219" alt="Screenshot 2026-09-05 175834" src="https://github.com/user-attachments/assets/8fffce6a-98dd-4a56-8733-d6c145b2ae76" />
