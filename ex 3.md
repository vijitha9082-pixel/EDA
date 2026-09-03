program 1
import pandas as pd

df = pd.read_csv("data.csv")
df.reset_index(inplace=True)
df.rename(columns={"index": "Index"}, inplace=True)
print(df)

output:<img width="564" height="454" alt="Screenshot 2026-09-03 104958" src="https://github.com/user-attachments/assets/5c6df89f-512b-45fb-bf48-99a9a50c5f6c" />

program 2

import pandas as pd

df = pd.read_csv("data.csv")
print(df.isnull().sum())
output:<img width="162" height="141" alt="Screenshot 2026-09-03 105102" src="https://github.com/user-attachments/assets/38b80c66-29a6-48f0-a319-403493406a1c" />

program 3
import pandas as pd

df = pd.read_csv("data.csv")
df.reset_index(inplace=True)
df.rename(columns={"index": "Index"}, inplace=True)

df["Price"] = df["Price"].fillna(df["Price"].mean())
df["Rating"] = df["Rating"].fillna(df["Rating"].mean())
df["Stock"] = df["Stock"].fillna(df["Stock"].mean())

print(df)

output:<img width="632" height="464" alt="Screenshot 2026-09-03 105147" src="https://github.com/user-attachments/assets/77b75242-4660-4165-8c8c-4a6b23b70e5f" />

program 4
import pandas as pd

df = pd.read_csv("data.csv")
df.reset_index(inplace=True)
df.rename(columns={"index": "Index"}, inplace=True)

print(df)
output:<img width="556" height="474" alt="Screenshot 2026-09-03 105249" src="https://github.com/user-attachments/assets/c08598ee-2a5e-4ad0-ae36-e6ba84746e56" />

program 5
import pandas as pd

df = pd.read_csv("data.csv")
df.reset_index(inplace=True)
df.rename(columns={"index": "Index"}, inplace=True)

duplicates = df[df.duplicated(subset=["Product_ID", "Product_Name", "Category", "Price", "Stock"], keep=False)]
print(duplicates)
output:<img width="528" height="80" alt="Screenshot 2026-09-03 105501" src="https://github.com/user-attachments/assets/c0efb5b7-8fec-42b5-928e-0c3d6b6cf18e" />

program 6
import pandas as pd

df = pd.read_csv("data.csv")
df.reset_index(inplace=True)
df.rename(columns={"index": "Index"}, inplace=True)

df = df.drop_duplicates(subset=["Product_ID", "Product_Name", "Category", "Price", "Stock"], keep="first")
print(df)

output:<img width="571" height="456" alt="Screenshot 2026-09-03 105608" src="https://github.com/user-attachments/assets/5b28a577-b2ee-47ad-9b16-28ee16474a91" />

program 7
import pandas as pd

df = pd.read_csv("data.csv")
df.reset_index(inplace=True)
df.rename(columns={"index": "Index"}, inplace=True)

df["Category"] = df["Category"].str.strip().str.title()
print(df)

output:<img width="563" height="462" alt="Screenshot 2026-09-03 105719" src="https://github.com/user-attachments/assets/d2bef43f-7e45-4743-a73d-213ef79923d3" />

program 8:
import pandas as pd

df = pd.read_csv("data.csv")
df.reset_index(inplace=True)
df.rename(columns={"index": "Index"}, inplace=True)

df["Price"] = df["Price"].fillna(df["Price"].mean())
df["Rating"] = df["Rating"].fillna(df["Rating"].mean())
df["Stock"] = df["Stock"].fillna(df["Stock"].mean())
df["Category"] = df["Category"].str.strip().str.title()
df = df.drop_duplicates(subset=["Product_ID", "Product_Name", "Category", "Price", "Stock"], keep="first")

print("Missing Values:")
print(df.isnull().sum())
print("\nDuplicate Records:", df.duplicated().sum())
print("\nCleaned Dataset:")
print(df)

output:<img width="634" height="578" alt="Screenshot 2026-09-03 105828" src="https://github.com/user-attachments/assets/07c7b150-0ca5-4bdb-b37b-5729d03cea50" />
