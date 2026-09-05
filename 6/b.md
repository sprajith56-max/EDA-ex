from google.colab import files
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Upload the Hospital dataset
uploaded = files.upload()

# Get the uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Create Pair Plot
sns.pairplot(
    df,
    vars=["Age", "Visits", "Bill_Amount"],
    hue="Department",
    diag_kind="hist"
)

# Display the plot
plt.show()

<img width="881" height="741" alt="eda 6" src="https://github.com/user-attachments/assets/17a405cb-f675-4cfd-a850-f4c0a746107c" />
