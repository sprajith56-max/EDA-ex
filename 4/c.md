from google.colab import files
import pandas as pd

# Upload the Hospital dataset
uploaded = files.upload()

# Get the uploaded filename automatically
filename = next(iter(uploaded))

# Load the dataset
df = pd.read_csv(filename)

# Equal-Width Binning
df["Age_EqualWidth"] = pd.cut(
    df["Age"],
    bins=4,
    labels=["Young", "Adult", "Middle Age", "Senior"]
)

# Equal-Frequency Binning
df["Age_EqualFrequency"] = pd.qcut(
    df["Age"],
    q=4,
    labels=["Young", "Adult", "Middle Age", "Senior"],
    duplicates="drop"
)

# Display result
print(df[["Age", "Age_EqualWidth", "Age_EqualFrequency"]])
<img width="583" height="195" alt="Screenshot 2026-09-04 211108" src="https://github.com/user-attachments/assets/37aab2e9-65c6-4d55-aca9-327d9dbab215" />
