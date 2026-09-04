from google.colab import files
import pandas as pd

# Upload the Hospital dataset
uploaded = files.upload()

# Get uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Fill missing numerical values with mean
df["Visits"] = df["Visits"].fillna(df["Visits"].mean())
df["Bill_Amount"] = df["Bill_Amount"].fillna(df["Bill_Amount"].mean())
df["Age"] = df["Age"].fillna(df["Age"].mean())

# Display the updated dataset
print(df)


<img width="688" height="190" alt="Screenshot 2026-09-04 204753" src="https://github.com/user-attachments/assets/37ea9945-e596-4f78-9697-6b544bfd1ec5" />
