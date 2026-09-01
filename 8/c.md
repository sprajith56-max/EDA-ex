mport pandas as pd
import matplotlib.pyplot as plt
# Load and process data
df = pd.read_csv("Sports_Dataset.csv")
df["Date"] = pd.to_datetime(df["Date"], format='%d/%m/%Y')
df = df.sort_values('Date').reset_index(drop=True)
df["Rolling_SD"] = df["Score"].rolling(window=3, min_periods=1).std()
# Plot
plt.figure(figsize=(10,5))
plt.plot(df.index, df["Rolling_SD"], linewidth=3, marker='^', color='darkgreen')
plt.title("3-Match Rolling Standard Deviation")
plt.xlabel("Match Index")
plt.ylabel("Standard Deviation")
plt.grid(true,alpha=0.3)
plt.show()<img width="658" height="247" alt="Screenshot 2026-09-01 203253" src="https://github.com/user-attachments/assets/0ed13ab4-e88d-4ead-97d9-f6aff6134c81" />
