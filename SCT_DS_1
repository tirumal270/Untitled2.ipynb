import pandas as pd
import matplotlib.pyplot as plt
from google.colab import files

# Upload the file
uploaded = files.upload()
file = list(uploaded.keys())[0]

# reading with different header rows
df = None
for h in range(5):   # try first 5 rows
    temp = pd.read_excel(file, sheet_name="Data", header=h)
    if "Country Name" in temp.columns:
        df = temp
        break

if df is None:
    raise ValueError("Could not find 'Country Name' column. Check the sheet manually.")

#Filter for India
india = df[df["Country Name"] == "India"]

# Select years 2000–2022
years = list(map(str, range(2000, 2023)))
population = india[years].values.flatten()

# Plot bar chart
plt.figure(figsize=(12,6))
plt.bar(years, population, color="skyblue")
plt.xticks(rotation=45)
plt.title("India's Population Growth (2000–2022)")
plt.xlabel("Year")
plt.ylabel("Population")
plt.show()
     
