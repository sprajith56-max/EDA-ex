from google.colab import files
import pandas as pd
import matplotlib.pyplot as plt

# Upload Hospital dataset
uploaded = files.upload()

# Get the uploaded filename automatically
filename = next(iter(uploaded))

# Load dataset
df = pd.read_csv(filename)

# Count patients in each department
category_count = df["Department"].value_counts()

print("Patient Count by Department:")
print(category_count)

# Create Bar Chart<img width="703" height="400" alt="Screenshot 2026-09-04 201403" src="https://github.com/user-attachments/assets/a9195c2d-1ed6-4017-a593-a7bb6304bd1c" />
<img width="703" height="400" alt="Screenshot 2026-09-04 201403" src="https://github.com/user-attachments/assets/7ff326f9-bd23-4949-a33f-e22c97050d09" />

plt.figure(figsize=(8, 5))

category_count.plot(kind="bar")

plt.title("Patient Count by Department")
plt.xlabel("Department")
plt.ylabel("Number of Patients")
plt.xticks(rotation=45)

plt.tight_layout()
plt.show()
