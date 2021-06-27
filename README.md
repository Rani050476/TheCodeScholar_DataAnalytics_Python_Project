# TheCodeScholar_DataAnalytics_Python_Projectimport numpy as np
from IPython.display import display
from tabulate import tabulate
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sb

%matplotlib inline

tita_df = pd.read_csv('https://raw.githubusercontent.com/thecodescholar/DA_Python_Jun_21/main/Dataset/titanicDataset.csv')

print(tabulate(tita_df.head(),headers='keys',tablefmt='fancy_grid'))

#It is not necessary ,I just included
tita_df.describe()

print(tabulate(tita_df.describe(),headers='keys',tablefmt='fancy_grid'))

# last three columns of the titanicDataset
last_3col=tita_df.iloc[:,-3:]
print(tabulate(last_3col.head(),headers='keys',tablefmt='fancy_grid'))

#for unique  data of the Embarked field
tita_df['Embarked'].unique()

#count plot for sex using seaborn
#df=sb.load_dataset('titanicDataset')
sb.countplot('Sex',data=tita_df)
plt.show()

#Pie chart for the given number and label lists
Num_list=[500000,1800000,1200000]
Label_list=["Deaths","Total Cases","Cured"]
plt.pie(Num_list,labels=Label_list)

plt.show()

#Histogram for Age field
plt.hist(tita_df['Age'],bins=10)
plt.show()
