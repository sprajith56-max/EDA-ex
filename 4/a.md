from google.colab import files
import pandas as pd

# Upload the dataset
uploaded = files.upload()

# Get the uploaded filename automatically
filename = next(iter(uploaded))

# Load the Hospital dataset
df = pd.read_csv(filename)

# Display original column names
print("Original Column Names:")
print(df.columns)

# Rename columns
df.rename(columns={
    'Date': 'Date',
    'Patient_Name': 'Patient_Name',
    'Department': 'Department',
    'Doctor': 'Doctor',
    'Visits': 'Number_of_Visits',
    'Bill_Amount': 'Bill_Amount',
    'Age': 'Patient_Age'
}, inplace=True)

# Display updated column names
print("\nRenamed Column Names:")
print(df.columns)

<img width="644" height="154" alt="Screenshot 2026-09-04 210524" src="https://github.com/user-attachments/assets/dbfe8242-4bcd-475d-8c4e-10bd93303c72" />
