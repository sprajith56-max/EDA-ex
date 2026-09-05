
import pandas as pd

# Load the dataset
df = pd.read_csv("sports_dataset.csv")

# Group statistics
stats = df.groupby("Sport")["Score"].agg(["count", "mean", "std", "min", "max"])

print("Score Statistics by Sport")
print(stats)

<img width="505" height="135" alt="Screenshot 2026-09-05 181048" src="https://github.com/user-attachments/assets/9b817b90-a107-464e-a15c-b00f4a1dc3b2" />
