program 1
import pandas as pd
df = pd.read_csv("Correlation_Dataset.csv")

print("Dataset:")
print(df.head())

# Select numerical columns
num_data = df.select_dtypes(include=['number'])

corr_matrix = num_data.corr()


print("\nCorrelation Matrix:")
print(corr_matrix)

output:<img width="564" height="418" alt="Screenshot 2026-09-03 111555" src="https://github.com/user-attachments/assets/a69ef5b4-b01d-4329-b19f-11307c7e9e10" />

program 2
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("Correlation_Dataset.csv")

num_data = df.select_dtypes(include=['number'])

corr_matrix = num_data.corr()

plt.figure(figsize=(8,6))
sns.heatmap(corr_matrix,
            annot=True,
            cmap="coolwarm",
            fmt=".2f")
plt.title("Correlation Matrix Heatmap")
plt.tight_layout()
plt.savefig("heatmap.png", dpi=130)
plt.show()

output:<img width="675" height="536" alt="Screenshot 2026-09-03 111647" src="https://github.com/user-attachments/assets/8de256ef-fd37-4475-8ea1-2a8bad647b13" />

program 3
import pandas as pd

df = pd.read_csv("Correlation_Dataset.csv")

num_data = df.select_dtypes(include=['number'])

corr_matrix = num_data.corr()

print("Highly Correlated Variable Pairs (r > 0.8 or r < -0.8)\n")

for i in range(len(corr_matrix.columns)):
    for j in range(i+1, len(corr_matrix.columns)):
        value = corr_matrix.iloc[i, j]
        if value > 0.8 or value < -0.8:
            print(corr_matrix.columns[i],
                  "<-->",
                  corr_matrix.columns[j],
                  ":", round(value, 2))
output:<img width="444" height="158" alt="Screenshot 2026-09-03 111735" src="https://github.com/user-attachments/assets/d6d6a59e-30ed-44b6-aad4-6f58cda72a56" />
