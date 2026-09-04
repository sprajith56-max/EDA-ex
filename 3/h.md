from google.colab import files
import pandas as pd

# Upload the Hospital dataset
uploaded = files.upload()

# Get the uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Perform data cleaning

# Fill missing numerical values with mean
df["Visits"] = df["Visits"].fillna(df["Visits"].mean())
df["Bill_Amount"] = df["Bill_Amount"].fillna(df["Bill_Amount"].mean())
df["Age"] = df["Age"].fillna(df["Age"].mean())

# Correct inconsistent department values
df["Department"] = df["Department"].replace({
    "cardiology": "Cardiology",
    "neurology": "Neurology",
    "orthopedics": "Orthopedics",
    "pediatrics": "Pediatrics"
})

# Remove duplicate records
df = df.drop_duplicates()

# Verify cleaned dataset
print("Missing Values:")
print(df.isnull().sum())

print("\nDuplicate Records:")
print(df.duplicated().sum())

<img width="659" height="440" alt="Screenshot 2026-09-04 210032" src="https://github.com/user-attachments/assets/e89b0a41-c0a1-48e1-a7f1-d08229e20426" />


print("\nCleaned Dataset:")
print(df)
