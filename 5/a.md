from google.colab import files
import pandas as pd

# Upload the Hospital dataset
uploaded = files.upload()

# Get the uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Select numerical columns
num_data = df.select_dtypes(include=['number'])

# Create correlation matrix
corr_matrix = num_data.corr()

# Display correlation matrix
print("Correlation Matrix")
print(corr_matrix)

<img width="531" height="112" alt="Screenshot 2026-09-05 100902" src="https://github.com/user-attachments/assets/5268f82c-e926-49aa-8ac2-b661cfea4132" />
