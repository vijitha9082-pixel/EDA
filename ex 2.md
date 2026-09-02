 
# Program 1: Bar Chart 
 
import pandas as pd 
import matplotlib.pyplot as plt 
 
# Load the dataset 
df = pd.read_csv("Data Set.csv") 
 
# Count products in each category 
category_count = df['Category'].value_counts() 
 
# Create Bar Chart 
plt.figure(figsize=(8,5)) 
category_count.plot(kind='bar') 
 
plt.title("Product Count by Category") 
plt.xlabel("Category") 
plt.ylabel("Number of Products") 
 
plt.show()
output:<img width="556" height="304" alt="Screenshot 2026-09-02 154319" src="https://github.com/user-attachments/assets/8f08dd2e-82f8-4012-81e6-3670fe1c9419" />
program 2
 
# Program 2: Pie Chart 
 
import pandas as pd 
import matplotlib.pyplot as plt 
 
# Load the dataset 
df = pd.read_csv("Data Set.csv") 
 
# Count products in each category 
category_count = df['Category'].value_counts() 
 
# Create Pie Chart 
plt.figure(figsize=(7,7)) 
category_count.plot(kind='pie', autopct='%1.1f%%') 
 
plt.title("Product Category Distribution") 
plt.ylabel("") 
 
plt.show()
outout:<img width="624" height="347" alt="Screenshot 2026-09-02 154333" src="https://github.com/user-attachments/assets/684c0d8b-379e-41a2-929a-77f0e4ee9dd4" />
