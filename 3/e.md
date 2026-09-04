from google.colab import files
import pandas as pd

# Upload the Hospital dataset
uploaded = files.upload()

# Get uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Display duplicate records
print(df[df.duplicated()])

<img width="694" height="50" alt="Screenshot 2026-09-04 205306" src="https://github.com/user-attachments/assets/67540896-1241-4e05-89d1-67bc097e98a9" />
