import pandas as pd

# Read the Excel file
df = pd.read_excel("sports.xlsx")

# Convert Date column to datetime
df["Date"] = pd.to_datetime(df["Date"])

# Set Date as index
df.set_index("Date", inplace=True)

# Downsampling: Daily → Monthly
monthly_data = df.resample("ME").agg({
    "Matches": "sum",
    "Score": "sum",
    "Age": "mean"
})

print("DOWNSAMPLED DATA (DAILY → MONTHLY)")
print(monthly_data)


<img width="378" height="280" alt="Screenshot 2026-09-01 160610" src="https://github.com/user-attachments/assets/96a8e3a7-640e-437f-8ae0-b760bf2ff68e" />
