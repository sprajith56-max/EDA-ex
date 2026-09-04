from google.colab import files
import pandas as pd

# Upload the Hospital dataset
uploaded = files.upload()

# Get uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Remove duplicate records
df = df.drop_duplicates()

# Display the updated dataset
print(df)

<img width="689" height="200" alt="Screenshot 2026-09-04 205507" src="https://github.com/user-attachments/assets/2c699062-c362-4f0d-a9a8-af6b469d574a" />
