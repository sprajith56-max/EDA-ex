import pandas as pd

# Read the Excel file
df = pd.read_excel("sports.xlsx")

# Convert Date column to datetime
df["Date"] = pd.to_datetime(df["Date"])

# Set Date as index
df.set_index("Date", inplace=True)

# Create monthly data
monthly_data = df.resample("ME").agg({
    "Matches": "sum",
    "Score": "sum",
    "Age": "mean"
})

# Upsampling: Monthly → Daily
daily_data = monthly_data.resample("D").asfreq()

# Fill missing values
daily_data = daily_data.ffill()

print("UPSAMPLED DATA (MONTHLY → DAILY)")
print(daily_data)






<img width="324" height="285" alt="Screenshot 2026-09-01 160736" src="https://github.com/user-attachments/assets/e29ab185-4c30-4f3a-846a-05dab9637e7f" />
