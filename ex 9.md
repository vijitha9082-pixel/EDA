program 1
import pandas as pd
from scipy.stats import ttest_ind

df = pd.read_csv("TTest_Dataset.csv")

clothing = df[df["Category"] == "Clothing"]["Sales"]
footwear = df[df["Category"] == "Footwear"]["Sales"]

t_value, p_value = ttest_ind(clothing, footwear)

print("t-value :", t_value)
print("p-value :", p_value)

 output:<img width="296" height="75" alt="Screenshot 2026-09-03 121357" src="https://github.com/user-attachments/assets/3b35a084-f744-4de2-b0af-0702ceacddec" />

program 2

import pandas as pd
from scipy.stats import ttest_ind

df = pd.read_csv("TTest_Dataset.csv")

clothing = df[df["Category"] == "Clothing"]["Sales"]
footwear = df[df["Category"] == "Footwear"]["Sales"]

t_value, p_value = ttest_ind(clothing, footwear)

alpha = 0.05

print("t-value :", t_value)
print("p-value :", p_value)

if p_value < alpha:
    print("\nConclusion:")
    print("Reject the Null Hypothesis (H0)")
    print("There is a significant difference between the Sales of Clothing and Footwear products.")
else:
    print("\nConclusion:")
    print("Fail to Reject the Null Hypothesis (H0)")
    print("There is no significant difference between the Sales of Clothing and Footwear products.")

output:<img width="281" height="77" alt="Screenshot 2026-09-03 121512" src="https://github.com/user-attachments/assets/6cc46c40-8122-43eb-b9d8-15aa49be5d08" />

program 3

import pandas as pd

df = pd.read_csv("TTest_Dataset.csv")

stats = df.groupby("Category")["Sales"].agg(["count", "mean", "std", "min", "max"])

print("Sales Statistics by Category")
print(stats)

output:<img width="405" height="118" alt="Screenshot 2026-09-03 121557" src="https://github.com/user-attachments/assets/f7621f84-5bd0-4838-8b1f-8289f4b2e45f" />
