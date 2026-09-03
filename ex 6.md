program 1
import pandas as pd
pd.set_option("future.infer_string", False)

df = pd.read_csv("Pairplot_Dataset.csv")

print("E-Commerce Sales Dataset")
print(df.head())

print("\nDataset Information")
print(df.info())

output:<img width="566" height="509" alt="Screenshot 2026-09-03 115554" src="https://github.com/user-attachments/assets/2dd66ffd-260b-4ef4-af5b-66e97736ba94" />

program 2
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

df = pd.read_csv("Pairplot_Dataset.csv")

sns.pairplot(
    df,
    vars=["Price", "Rating", "Sales", "Discount", "Stock"],
    hue="Category",
    diag_kind="hist"
)

plt.savefig("pairplot.png", dpi=130)
plt.show()

output:<img width="677" height="611" alt="Screenshot 2026-09-03 115646" src="https://github.com/user-attachments/assets/079bbcef-caee-4762-8a17-a75aa7720f31" />
