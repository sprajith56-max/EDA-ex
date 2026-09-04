from google.colab import files
import pandas as pd

# Upload the dataset
uploaded = files.upload()

# Get the uploaded filename
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Display the dataset
print(df)<img width="626" height="201" alt="Screenshot 2026-09-04 195857" src="https://github.com/user-attachments/assets/fb4b521b-7970-4d56-ae9b-918ab976e6ef" />
