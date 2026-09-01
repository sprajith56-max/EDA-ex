import pandas as pd
import matplotlib.pyplot as plt
# Load and process data (as above)
df = pd.read_csv("Sports_Dataset.csv")
df["Date"] = pd.to_datetime(df["Date"], format='%d/%m/%Y')
df = df.sort_values('Date').reset_index(drop=True)
df["Rolling_Mean"] = df["Score"].rolling(window=3, min_periods=1).mean()
# Plot
plt.figure(figsize=(10,5))
plt.plot(df.index, df["Score"], marker='o', label="Original Score")
plt.plot(df.index, df["Rolling_Mean"], linewidth=3, marker='s', label="3-Match Rolling
Mean")
plt.title("Score vs 3-Match Rolling Mean")
plt.xlabel("Match Index")
plt.ylabel("Score")
plt.legend()
plt.grid(True, alpha=0.3)
plt.show()


<img width="607" height="218" alt="Screenshot 2026-09-01 161703" src="https://github.com/user-attachments/assets/4cadb565-42cd-4689-a809-09dcaa46c283" />


