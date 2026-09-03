program 1
import pandas as pd

df = pd.read_csv("Rolling_Dataset.csv")

df["Date"] = pd.to_datetime(df["Date"], dayfirst=True)

df.set_index("Date", inplace=True)

df["Rolling_Mean"] = df["Sales"].rolling(window=7).mean()

df["Rolling_SD"] = df["Sales"].rolling(window=7).std()

print(df[["Sales", "Rolling_Mean", "Rolling_SD"]])

output:<img width="370" height="535" alt="Screenshot 2026-09-03 120708" src="https://github.com/user-attachments/assets/7cb9c883-516a-4091-8c5a-ddb806c80346" />

program 2
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("Rolling_Dataset.csv")

df["Date"] = pd.to_datetime(df["Date"], dayfirst=True)

df.set_index("Date", inplace=True)


df["Rolling_Mean"] = df["Sales"].rolling(window=7).mean()

plt.figure(figsize=(10,5))
plt.plot(df.index, df["Sales"], label="Original Sales")
plt.plot(df.index, df["Rolling_Mean"], linewidth=3, label="7-Day Rolling Mean")
plt.title("Sales vs 7-Day Rolling Mean")
plt.xlabel("Date")
plt.ylabel("Sales")
plt.legend()
plt.savefig("plot_mean.png", dpi=130)
plt.show()

output:<img width="675" height="358" alt="Screenshot 2026-09-03 120533" src="https://github.com/user-attachments/assets/ec65e04f-6c75-48b9-a213-5ad2f5ba206c" />

program 3
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("Rolling_Dataset.csv")

df["Date"] = pd.to_datetime(df["Date"], dayfirst=True)

df.set_index("Date", inplace=True)

df["Rolling_SD"] = df["Sales"].rolling(window=7).std()

plt.figure(figsize=(10,5))
plt.plot(df.index, df["Rolling_SD"], linewidth=3)
plt.title("7-Day Rolling Standard Deviation")
plt.xlabel("Date")
plt.ylabel("Standard Deviation")
plt.savefig("plot_sd.png", dpi=130)
plt.show()

output:<img width="672" height="344" alt="Screenshot 2026-09-03 120757" src="https://github.com/user-attachments/assets/edc084cc-53c1-4c03-86a0-d3b770d17182" />
