
## Tree

```
.
└── [ 12M]  coveo_browsing_100k.parquet.snappy

  12M used in 0 directories, 1 file
```

## Processing

```python
!wget -q --show-progress https://staticassets.coveo.com/ai-labs/SIGIR-ecom-data-challenge.zip
!unzip SIGIR-ecom-data-challenge.zip

import pandas as pd
df = pd.read_csv('train/browsing_train.csv')
df_sample = df.sample(n=100000, random_state=42)
print(df_sample.info())
print(df_sample.columns)
df_sample.to_parquet('coveo_browsing_100k.parquet.snappy', compression='snappy')
```