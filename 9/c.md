<img width="425" height="118" alt="Screenshot 2026-09-01 204658" src="https://github.com/user-attachments/assets/c1d720dc-8103-4d1b-b85e-517ab41e46ea" />
import pandas as pd

# Load the dataset
df = pd.read_csv("sports_dataset.csv")

# Group statistics
stats = df.groupby("Sport")["Score"].agg(["count", "mean", "std", "min", "max"])

print("Score Statistics by Sport")
print(stats)<img width="425" height="118" alt="Screenshot 2026-09-01 204658" src="https://github.com/user-attachments/assets/15e9b241-61f0-4e14-8f3b-b19854cabfbd" />
