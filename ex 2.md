 
# Program 1: Bar Chart 
 
import pandas as pd 
import matplotlib.pyplot as plt 
df = pd.read_csv("Data Set.csv")  
category_count = df['Category'].value_counts() 
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
df = pd.read_csv("Data Set.csv") 
category_count = df['Category'].value_counts() 
plt.figure(figsize=(7,7)) 
category_count.plot(kind='pie', autopct='%1.1f%%') 
plt.title("Product Category Distribution") 
plt.ylabel("") 
plt.show()
output:<img width="624" height="347" alt="Screenshot 2026-09-02 154333" src="https://github.com/user-attachments/assets/684c0d8b-379e-41a2-929a-77f0e4ee9dd4" />

program 3
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("Data Set.csv")
df.columns = df.columns.str.strip()
plt.figure(figsize=(8,5))
plt.hist(df["Final MRP Old"], bins=10, edgecolor="black")
plt.title("Distribution of Final MRP Old")
plt.xlabel("Final MRP Old")
plt.ylabel("Frequency")
plt.grid(True)
plt.show()
output:<img width="612" height="314" alt="Screenshot 2026-09-03 092339" src="https://github.com/user-attachments/assets/cb0fe14f-5e8e-4813-99c4-47163f2be1a3" />

program 4
# Program 4: Box Plot
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("Data Set.csv")
df.columns = df.columns.str.strip()
plt.figure(figsize=(6,5))
plt.boxplot(df["Final MRP Old"])
plt.title("Box Plot of Final MRP Old")
plt.ylabel("Final MRP Old")
plt.grid(True)
plt.show()
output:<img width="603" height="282" alt="Screenshot 2026-09-03 092356" src="https://github.com/user-attachments/assets/9eb23275-b0d6-4c5d-8536-9f17cea5fed7" />


program 5
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("Data Set.csv")
df.columns = df.columns.str.strip()
plt.figure(figsize=(8,5))
plt.scatter(df["TP 1"], df["Final MRP Old"])
plt.title("TP 1 vs Final MRP Old")
plt.xlabel("TP 1")
plt.ylabel("Final MRP Old")
plt.grid(True)
plt.show()
output:<img width="646" height="355" alt="Screenshot 2026-09-03 092405" src="https://github.com/user-attachments/assets/b599837b-bcb9-4ae4-afb7-e51ee207eda9" />
