program 1
import pandas as pd
pd.set_option("future.infer_string", False)
df = pd.read_csv("ecommerce_sales.csv")
print("Original Column Names:")
print(df.columns)
df.rename(columns={
    'orderid': 'Order_ID',
    'cust': 'Customer_Name',
    'age': 'Age',
    'prod': 'Product',
    'qty': 'Quantity',
    'price': 'Price',
    'city': 'City'
}, inplace=True)
print("\nRenamed Column Names:")
print(df.columns)

output:<img width="643" height="135" alt="Screenshot 2026-09-03 110713" src="https://github.com/user-attachments/assets/31542dd1-42f7-4ee3-a70c-99d80c621eea" />

program 2
import pandas as pd
pd.set_option("future.infer_string", False)
df = pd.read_csv("ecommerce_sales.csv")
df.rename(columns={
    'orderid': 'Order_ID',
    'cust': 'Customer_Name',
    'age': 'Age',
    'prod': 'Product',
    'qty': 'Quantity',
    'price': 'Price',
    'city': 'City'
}, inplace=True)
print("Before Conversion:")
print(df.dtypes)
df["Price"] = df["Price"].astype(float)
df["Quantity"] = df["Quantity"].astype(int)
print("\nAfter Conversion:")
print(df.dtypes)

output:<img width="239" height="396" alt="Screenshot 2026-09-03 110830" src="https://github.com/user-attachments/assets/f9159f96-b8b0-44c4-b86b-e8e618a55d55" />

program 3
import pandas as pd
pd.set_option("future.infer_string", False)
df = pd.read_csv("ecommerce_sales.csv")
df.rename(columns={
    'orderid': 'Order_ID',
    'cust': 'Customer_Name',
    'age': 'Age',
    'prod': 'Product',
    'qty': 'Quantity',
    'price': 'Price',
    'city': 'City'
}, inplace=True)
df["Age_EqualWidth"] = pd.cut(
    df["Age"],
    bins=4,
    labels=["Young", "Adult", "Middle Age", "Senior"]
)

df["Age_EqualFrequency"] = pd.qcut(
    df["Age"],
    q=4,
    labels=["Young", "Adult", "Middle Age", "Senior"]
)

print(df[["Age", "Age_EqualWidth", "Age_EqualFrequency"]])

output:<img width="397" height="558" alt="Screenshot 2026-09-03 110938" src="https://github.com/user-attachments/assets/00793bad-8253-46ee-8234-4b44b4566036" />
