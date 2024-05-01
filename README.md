from google.colab import files

uploaded = files.upload()
#datavisualization
import pandas as pd

# Load the dataset
df = pd.read_csv('Book2.csv')
# Display the first few rows of the dataset
print(df.head())

# Check for missing values
print(df.isnull().sum())

# Summary statistics
print(df.describe())
# Drop rows with missing values
df.dropna(inplace=True)

# Fill missing values with a specific value
df.fillna(value=0, inplace=True)

# Impute missing values using interpolation or other methods
df['Total.Length.of.Fwd.Packets'].interpolate(inplace=True)
# Remove duplicate rows
df.drop_duplicates(inplace=True)

from google.colab import files

uploaded = files.upload()
#data analysis
import pandas as pd

# Assuming you have a CSV file containing network traffic data
# Replace 'network_traffic.csv' with the actual filename
data = pd.read_csv('Book2.csv')

# Display the first few rows of the data to understand its structure
print(data.head())

# Perform basic statistics on the data
print(data.describe())

# Analyze traffic by source IP
source_ip_counts = data['Fwd.Packet.Length.Std'].value_counts()
print("fwd packet length:\n", source_ip_counts.head(10))

# Analyze traffic by destination IP
dest_ip_counts = data['Flow.Bytes.s'].value_counts()
print("Top 10 flow bytes:\n", dest_ip_counts.head(10))

# Analyze traffic by protocol
protocol_counts = data['Protocol'].value_counts()
print("Protocol distribution:\n", protocol_counts)

from google.colab import files
uploaded = files.upload()

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
data = pd.read_csv('Book2.csv')
# Line plot
plt.figure(figsize=(10, 6))
plt.plot(data['Subflow.Fwd.Packets'], data['Subflow.Bwd.Packets'], label='Y1 Data')
plt.plot(data['Subflow.Fwd.Packets'], data['Subflow.Bwd.Bytes'], label='Y2 Data')
plt.title('Line Plot')
plt.xlabel('X')
plt.ylabel('Y')
plt.legend()
plt.grid(True)
plt.show()

# Bar chart
plt.figure(figsize=(10, 6))
plt.bar(data['Subflow.Fwd.Packets'], data['Subflow.Bwd.Packets'], label='Y1 Data')
plt.bar(data['Subflow.Fwd.Packets'], data['Subflow.Bwd.Bytes'], label='Y2 Data', alpha=1.0)
plt.title('Bar Chart')
plt.xlabel('X')
plt.ylabel('Y')
plt.legend()
plt.grid(True)
plt.show()


# Scatter plot
plt.figure(figsize=(10, 6))
plt.scatter(data['Subflow.Fwd.Packets'], data['Subflow.Bwd.Packets'], label='Y1 Data')
plt.scatter(data['Subflow.Fwd.Packets'], data['Subflow.Bwd.Bytes'], label='Y2 Data')
plt.title('Scatter Plot')
plt.xlabel('X')
plt.ylabel('Y')
plt.legend()
plt.grid(True)
plt.show()

# Pair plot (using seaborn)
sns.pairplot(data, hue='Subflow.Fwd.Packets')
plt.title('Pair Plot')
plt.show()
