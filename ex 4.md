program 1
import pandas as pd
pd.set_option("future.infer_string", False)

# Load the dataset
df = pd.read_csv("ecommerce_sales.csv")

# Display original column names
print("Original Column Names:")
print(df.columns)

# Rename columns
df.rename(columns={
    'orderid': 'Order_ID',
    'cust': 'Customer_Name',
    'age': 'Age',
    'prod': 'Product',
    'qty': 'Quantity',
    'price': 'Price',
    'city': 'City'
}, inplace=True)

# Display updated column names
print("\nRenamed Column Names:")
print(df.columns)

output:<img width="643" height="135" alt="Screenshot 2026-09-03 110713" src="https://github.com/user-attachments/assets/31542dd1-42f7-4ee3-a70c-99d80c621eea" />

program 2
import pandas as pd
pd.set_option("future.infer_string", False)

# Load the dataset
df = pd.read_csv("ecommerce_sales.csv")

# Rename columns
df.rename(columns={
    'orderid': 'Order_ID',
    'cust': 'Customer_Name',
    'age': 'Age',
    'prod': 'Product',
    'qty': 'Quantity',
    'price': 'Price',
    'city': 'City'
}, inplace=True)

# Display data types before conversion
print("Before Conversion:")
print(df.dtypes)

# Convert Price to float
df["Price"] = df["Price"].astype(float)

# Convert Quantity to int
df["Quantity"] = df["Quantity"].astype(int)

# Display data types after conversion
print("\nAfter Conversion:")
print(df.dtypes)

output:<img width="239" height="396" alt="Screenshot 2026-09-03 110830" src="https://github.com/user-attachments/assets/f9159f96-b8b0-44c4-b86b-e8e618a55d55" />

program 3
import pandas as pd
pd.set_option("future.infer_string", False)

# Load the dataset
df = pd.read_csv("ecommerce_sales.csv")

# Rename columns
df.rename(columns={
    'orderid': 'Order_ID',
    'cust': 'Customer_Name',
    'age': 'Age',
    'prod': 'Product',
    'qty': 'Quantity',
    'price': 'Price',
    'city': 'City'
}, inplace=True)

# Equal-Width Binning
df["Age_EqualWidth"] = pd.cut(
    df["Age"],
    bins=4,
    labels=["Young", "Adult", "Middle Age", "Senior"]
)

# Equal-Frequency Binning
df["Age_EqualFrequency"] = pd.qcut(
    df["Age"],
    q=4,
    labels=["Young", "Adult", "Middle Age", "Senior"]
)

# Display result
print(df[["Age", "Age_EqualWidth", "Age_EqualFrequency"]])

output:<img width="397" height="558" alt="Screenshot 2026-09-03 110938" src="https://github.com/user-attachments/assets/00793bad-8253-46ee-8234-4b44b4566036" />
