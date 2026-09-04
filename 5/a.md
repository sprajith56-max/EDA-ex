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

