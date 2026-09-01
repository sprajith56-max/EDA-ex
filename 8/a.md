import pandas as pd
import numpy as np
# Load dataset
df = pd.read_csv("Sports_Dataset.csv")
# Convert Date column into datetime format
df["Date"] = pd.to_datetime(df["Date"], format='%d/%m/%Y')
# Sort by date
df = df.sort_values('Date').reset_index(drop=True)
# Calculate Rolling Mean (3-match window)
df["Rolling_Mean"] = df["Score"].rolling(window=3, min_periods=1).mean()
# Calculate Rolling Standard Deviation
df["Rolling_SD"] = df["Score"].rolling(window=3, min_periods=1).std()
# Display results
print(df[["Date", "Player", "Score", "Rolling_Mean", "Rolling_SD"]])




<img width="679" height="339" alt="Screenshot 2026-09-01 161455" src="https://github.com/user-attachments/assets/725c4ea2-77c5-4379-8e4b-b35be08501b7" />
