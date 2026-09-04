from google.colab import files
import pandas as pd


uploaded = files.upload()
filename = next(iter(uploaded))


df = pd.read_csv(filename)


print("Before Conversion:")
print(df.dtypes)


df["Bill_Amount"] = df["Bill_Amount"].astype(float)


df["Visits"] = df["Visits"].astype(int)


df["Age"] = df["Age"].astype(int)


print("\nAfter Conversion:")
print(df.dtypes)
<img width="446" height="327" alt="Screenshot 2026-09-04 210800" src="https://github.com/user-attachments/assets/cdb49610-3e0c-41b5-b3e9-adaf9f949b8f" />
