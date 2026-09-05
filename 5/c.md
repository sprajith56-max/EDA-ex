from google.colab import files
import pandas as pd

# Upload the Hospital dataset
uploaded = files.upload()
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Select numerical columns
num_data = df.select_dtypes(include=['number'])

# Correlation matrix
corr_matrix = num_data.corr()

print("Correlation Values\n")

for i in range(len(corr_matrix.columns)):
    for j in range(i + 1, len(corr_matrix.columns)):
        value = corr_matrix.iloc[i, j]

        print(
            corr_matrix.columns[i],
            "<-->",
            corr_matrix.columns[j],
            "=",
            round(value, 2)
        )

        <img width="500" height="93" alt="Screenshot 2026-09-05 101519" src="https://github.com/user-attachments/assets/1c87af19-5699-4851-b117-3d94b62320f5" />
