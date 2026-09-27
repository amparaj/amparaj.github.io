---
layout: post
title: "Interesting pandas tips and tricks"
date: 2024-11-06
author: Ayush Parajuli
---

Pandas is a powerful python library for data manipulation and analysis. I've learned some interesting pandas techniques that I thought is worth documenting for others and also as a personal learning.

## Working with parquet files
- Important to install right dependencies like pyarrow or fastparquet for handling such files in pandas.

## Monitoring loading of large data files
- Integrating tqdm in the code to see a progress bar
- Using tqdm with pandas for progress tracking especially when iterating over row or performing transformations on large dataframes.

```python
from tqdm import tqdm
import pandas as pd

file_path = "large_data.csv"
chunk_size = 100000  # Process in chunks if needed

# Read in chunks and show a progress bar as each chunk loads
chunks = pd.read_csv(file_path, chunksize=chunk_size)
df = pd.concat(tqdm(chunks, desc="Loading", unit="chunk"))
print(df.info())
```

## Using tqdm for DataFrame iteration
- Iterating through rows or applying transformations on large datasets can be monitored via a progress bar using tqdm.

```python
# Enable tqdm for pandas, adds .progress_apply()
tqdm.pandas()

df["new_column"] = df["column1"].progress_apply(lambda x: x * 2)
```

## Grouping without aggregation
- This one is relatively simple concept but handy to know.
- Pandas makes it easy to group data by multiple columns w/o applying any aggregation using groupby() and as_index=False.
- For example:

```python
grouped_df = df.groupby(['column1', 'column2'], as_index=False).apply(lambda x: x)
```
