program 1
import pandas as pd

df = pd.read_csv("Resample_Dataset.csv")

df["Date"] = pd.to_datetime(df["Date"], format="%d/%m/%Y")

df.set_index("Date", inplace=True)

monthly_data = df.resample("ME").sum(numeric_only=True)

print("Monthly Summary")
print(monthly_data)

output:<img width="408" height="97" alt="Screenshot 2026-09-03 120005" src="https://github.com/user-attachments/assets/2028ced3-e149-4c4f-bcc0-e9422fdf90f8" />

program 2:
import pandas as pd

df = pd.read_csv("Resample_Dataset.csv")

df["Date"] = pd.to_datetime(df["Date"], dayfirst=True)

df.set_index("Date", inplace=True)

monthly_data = df.resample("ME").mean(numeric_only=True)

daily_data = monthly_data.resample("D").ffill()

print("Up-Sampled Daily Data")
print(daily_data.head(15))

output:<img width="440" height="103" alt="Screenshot 2026-09-03 120055" src="https://github.com/user-attachments/assets/33a2d0c3-4033-4a67-af73-34d1bda09093" />
