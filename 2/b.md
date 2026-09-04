from google.colab import files
import pandas as pd
import matplotlib.pyplot as plt

# Upload the hospital dataset
uploaded = files.upload()

# Get the uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Count patients in each department
department_count = df["Department"].value_counts()

print("Patient Count by Department:")
print(department_count)

# Create Pie Chart
plt.figure(figsize=(7, 7))

department_count.plot(
    kind="pie",
    autopct="%1.1f%%"
)

plt.title("Patient Distribution by Department")
plt.ylabel("")

plt.show()<img width="713" height="422" alt="Screenshot 2026-09-04 201808" src="https://github.com/user-attachments/assets/09d20945-36e4-48eb-85f1-2124a1fdb408" />
