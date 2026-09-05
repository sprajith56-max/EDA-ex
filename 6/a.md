from google.colab import files
import pandas as pd

# Upload the Hospital dataset
uploaded = files.upload()

# Get the uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Display first five records
print("Hospital Dataset")
print(df.head())

# Display dataset information
print("\nDataset Information")
print(df.info())

<img width="666" height="416" alt="Screenshot 2026-09-05 102102" src="https://github.com/user-attachments/assets/5181d13c-b68d-4301-bed6-0243979f4db1" />
