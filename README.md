# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:

```
import seaborn as sns
import matplotlib.pyplot as plt
df = sns.load_dataset("tips")
df

```

<img width="623" height="549" alt="image" src="https://github.com/user-attachments/assets/b2a8dfa1-6b71-4434-a83a-aad75a7cb693" />

```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle="solid",legend="auto",palette="Set1")

```

<img width="819" height="622" alt="image" src="https://github.com/user-attachments/assets/0ba9f067-f527-45ac-a00b-f99aba2112a4" />


```
x=[1,2,3,4,5]
y1=[3,5,2,6,1]
y2=[1,6,4,3,8]
y3=[5,2,7,1,4]
sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)
plt.title("Multi-line plot")
plt.xlabel("X label")
plt.ylabel("Y label")
```
<img width="526" height="436" alt="image" src="https://github.com/user-attachments/assets/e95a3a01-6bad-47ed-a8f9-9ae51ec967a5" />

```
tips = sns.load_dataset("tips")
avg_total_bill = tips.groupby("day")["total_bill"].mean()
avg_tip = tips.groupby("day")["tip"].mean()
plt.figure(figsize=(8,6))
p1 = plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill")
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="Tip")
plt.xlabel("Day of the week")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Day")
plt.legend()
plt.show()

```

<img width="519" height="407" alt="image" src="https://github.com/user-attachments/assets/d9a9a5e0-1010-4309-84e6-f66172366ad0" />

```
avg_total_bill=tips.groupby("time")["total_bill"].mean()
avg_tip=tips.groupby("time")["tip"].mean()
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill",width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="Tip",width=0.4)
plt.xlabel("Time of the day")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Time of the Day")
plt.legend()
```

<img width="528" height="431" alt="image" src="https://github.com/user-attachments/assets/57fb219c-e350-46b7-b469-285858e9f2e8" />


```
import seaborn as sns
df=sns.load_dataset("tips")
sns.barplot(x="day",y="total_bill",hue="sex",data=df,palette="Set3")
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Total Bill by Day and Gender")
```

<img width="543" height="445" alt="image" src="https://github.com/user-attachments/assets/19603271-05f1-4b99-b7ca-d4f40296f34e" />


```
df=sns.load_dataset("tips")
sns.scatterplot(x="total_bill",y="tip",hue="sex",data=df,palette="Set1")
plt.xlabel("Total Bill")
plt.ylabel("Tip")
plt.title("Scatter Plot of Total Bill vs Tip Amount")
```

<img width="541" height="443" alt="image" src="https://github.com/user-attachments/assets/c624baf7-7329-4b68-bb60-69e757387812" />

```
sns.histplot(data=df,x="total_bill",hue="smoker",kde=True,palette="Set1")
plt.xlabel("Total Bill")
plt.ylabel("Frequency")
plt.title("Distribution of Total Bill by Gender")

```

<img width="531" height="437" alt="image" src="https://github.com/user-attachments/assets/2ef69b53-cda6-4899-8e00-adf7a70eb884" />

```
import seaborn as sns
import pandas as pd
df=sns.load_dataset("tips")
sns.boxplot(x="day",y="total_bill",hue="sex",data=df,palette="Set2")

```

<img width="512" height="405" alt="image" src="https://github.com/user-attachments/assets/1f8d0dc3-62fe-4832-907a-838a0b78b2ad" />

```
sns.boxplot(x="day",y="total_bill",hue="smoker",data=df,linewidth=2,width=0.6,fliersize=7,flierprops={"marker":"o","markerfacecolor":"grey"},boxprops={"facecolor":"red","edgecolor":"black"},whiskerprops={"color":"darkblue","linestyle":"--","linewidth":"-","linewidth":2},palette="Set1")

```

<img width="497" height="391" alt="image" src="https://github.com/user-attachments/assets/5d3728a4-bc98-4bbc-9fce-a1788d153e88" />

```
sns.violinplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=2,width=0.6,palette="Set1",inner="quartile")
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")

```

<img width="522" height="422" alt="image" src="https://github.com/user-attachments/assets/40999896-35b1-47c8-9e75-e35a36de2488" />

```
import seaborn as sns
sns.set(style="whitegrid")
tip=sns.load_dataset("tips")
sns.violinplot(x="day",y="tip",data=tip,palette="Set2")

```

<img width="516" height="394" alt="image" src="https://github.com/user-attachments/assets/711bbba3-fe17-410c-a4f1-63a3f2850bea" />

```

import seaborn as sns
sns.set(style="whitegrid")
tip=sns.load_dataset("tips")
sns.violinplot(x=tip["total_bill"],palette="Set1")

```

<img width="471" height="398" alt="image" src="https://github.com/user-attachments/assets/4786f697-20ee-42cf-af32-d6e05a283275" />

```
import seaborn as sns
sns.set(style="whitegrid")
tips=sns.load_dataset("tips")
sns.violinplot(x="tip",y="day",data=tip,palette="rainbow")

```

<img width="534" height="405" alt="image" src="https://github.com/user-attachments/assets/cf94332c-2d7a-4b8c-bf82-b3cbadc6e45e" />

```
sns.kdeplot(data=tips,x="total_bill",hue="time",multiple="layer",linewidth=3,palette="Set2",alpha=0.8)

```

<img width="550" height="413" alt="image" src="https://github.com/user-attachments/assets/417956a7-5a95-4e9e-b47e-6e209a7af737" />

```
sns.kdeplot(data=tips,x="total_bill",hue="time",multiple="stack",linewidth=3,palette="Set3",alpha=0.8)

```

<img width="513" height="401" alt="image" src="https://github.com/user-attachments/assets/96df4932-9c84-4f84-ae3b-7594c3a3c1e7" />


```
sns.kdeplot(data=tips,x="total_bill",hue="time",multiple="fill",linewidth=3,palette="Set1",alpha=0.8)

```

<img width="529" height="404" alt="image" src="https://github.com/user-attachments/assets/a21fce53-822f-46df-9cf3-e3ef182ea6eb" />

```
import seaborn as sns
tip=sns.load_dataset("tips")
num=tips.select_dtypes(include=["float64","int64"]).columns
corr=tips[num].corr()
sns.heatmap(corr,annot=True)

```

<img width="495" height="408" alt="image" src="https://github.com/user-attachments/assets/2026c992-22df-4128-9910-dda2cf30ded5" />

```
sns.heatmap(corr)
```

<img width="515" height="433" alt="image" src="https://github.com/user-attachments/assets/fa04cb06-da6d-41d0-afc2-9098ded8499f" />


# Result:

 Data Visualization has been performed using seaborn python library for the given datas.
