from google.colab import files
import pandas as pd

# Upload the Hospital dataset
uploaded = files.upload()

# Get uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Fill missing categorical values with mode
df["Department"] = df["Department"].fillna(df["Department"].mode()[0])

# Display the updated dataset
print(df)

  <img width="662" height="200" alt="Screenshot 2026-09-04 205026" src="https://github.com/user-attachments/assets/d5eebfcd-195b-46c4-a969-83b82df56184" />
