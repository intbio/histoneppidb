### convertation script
```
import pandas as pd
import numpy as np
df=pd.read_csv('db_22.12.20.csv')
df=df.replace({np.nan:None})
import json
with open('db_22.12.2020.json','w') as f:
    json.dump({'data':df.to_dict(orient='records')},f)

for name in df.columns:
    print('{ "data": "'+name+'" },')
for name in df.columns:
    print('<th>'+name+'</th>')
```
