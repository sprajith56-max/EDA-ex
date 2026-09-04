from google.colab import files
import pandas as pd


# Upload the dataset
uploaded = files.upload()

# Get the uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Display missing values
print(df.isnull().sum())


<img width="516" height="167" alt="Screenshot 2026-09-04 203852" src="https://github.com/user-attachments/assets/a5c81d55-a8a2-427f-838f-fca160aae1f4" />
