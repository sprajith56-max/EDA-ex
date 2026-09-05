from google.colab import files
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Upload the Hospital dataset
uploaded = files.upload()

# Get the uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Select numerical columns
num_data = df.select_dtypes(include=['number'])

# Correlation matrix
corr_matrix = num_data.corr()

# Draw heatmap
plt.figure(figsize=(8, 6))

sns.heatmap(
    corr_matrix,
    annot=True,
    cmap="coolwarm",
    fmt=".2f"
)

plt.title("Hospital Dataset Correlation Matrix Heatmap")
plt.show()

<img width="625" height="528" alt="5 b eda" src="https://github.com/user-attachments/assets/03f8fcbc-43d8-4c0e-838d-916652892fff" />
