from google.colab import files
import pandas as pd

# Upload the Hospital dataset
uploaded = files.upload()

# Get the uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Display the first 5 rows
print(df.head())

<img width="628" height="113" alt="Screenshot 2026-09-04 213952" src="https://github.com/user-attachments/assets/6abb1dde-e435-4a96-816e-38acc4a02280" />
