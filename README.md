import numpy as np
import statistics as st
import matplotlib.pyplot as plt
o=range(0,25)
p=range(0,25)
plt.plot(o,p)
incame=[5,20,10,7]
expanditure=[4,19,10,7]
plt.scatter(incame,expanditure, label='skitscat' ,color='#EA2027' ,marker='*',s=50)
plt.suptitle('Scatter plot before regression analysis', fontsize=16)
plt.xlabel('incame')
plt.ylabel('expanditure')
plt.legend()
plt.show()
men=st.mean(incame)
men2=st.mean(expanditure)
sum=0
value=0
valuex=0
sum2=0
value2=0
result=0
lists=[]
lists2=[]
analysis=[]
sumfinal=0
for i in incame:
    value=(i-men)
    lists.append(value)
    sum= sum + (value*value)
for j in expanditure:
    value2=(j-men2)
    lists2.append(value2)
mlutlist=(np.multiply(lists,lists2))

for i in mlutlist:
    sumfinal=sumfinal+i

B1=sumfinal/sum
print("B1= {:.2}".format(B1))
B0=men2-B1*men
print("B0={:.2}".format(B0))

for w in incame:
    before=(B0+(B1*w))
    analysis.append("{:2.2}".format(before))
print(analysis)
o=range(0,25)
p=range(0,25)
plt.plot(o,p)
plt.scatter(incame,analysis, label='skitscat' ,color='#5f27cd' ,marker='*',s=50)
plt.suptitle('Scatter plot after regression analysis', fontsize=16)
plt.xlabel('incame')
plt.ylabel('analysis')
plt.legend()
plt.show()
