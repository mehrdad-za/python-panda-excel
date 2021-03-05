# python-panda-excel
#Using python panda for comparing two excel files via same col
#samecolname means same column name in two files for comparing via that...
#here is the code:

import pandas as pd
import numpy as np

# Read both Excel files
file1 = pd.read_excel("file1.xlsx", na_values=['NA'])
file2 = pd.read_excel("file2.xlsx", na_values=['NA'])


df2 = file1
df1 = file2



res = df1[df1['samecolname'].isin(df2['samecolname'].unique())]
                   
res2 = df2[df2['samecolname'].isin(df1['samecolname'].unique())]               

res.to_excel('diff1-insecond-but-not-in-first.xlsx',index=False)
res2.to_excel('diff2-in-first-not-in-second.xlsx',index=False)
