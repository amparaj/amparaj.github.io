---
layout: post
title: "Interesting pandas tips and tricks"
date: 2024-11-06
author: Ash Parajuli
---

Pandas is a powerful python library for data manipulation and analysis. I've learned some interesting pandas techniques that I thought is worth documenting for others and also as a personal learning.

## Working with parquet files
- Important to install right dependencies like pyarrow or fastparquet for handling such files in pandas.
---

## Monitoring loading of large data files
- Integrating tqdm in the code to see a progress bar
- Using tqdm with pandas for progress tracking especially when iterating over row or performing transformations on large dataframes.

```python
from tqdm import tqdm
import pandas as pd

# Enable tqdm for pandas
tqdm.pandas()

file_path = "large_data.csv"
chunk_size = 100000  # Process in chunks if needed

# Process with a progress bar
df = pd.concat(
    pd.read_csv(file_path, chunksize=chunk_size, iterator=True).progress_apply(lambda x: x)
)
print(df.info())
```
---

## Using tqdm for DataFrame iteration
- Iterating through rows or applying transformations on large datasets can be monitored via a progress bar using tqdm.
---

## Grouping without aggregation
- This one is relatively simple concept but handy to know.
- Pandas makes it easy to group data by multiple columns w/o applying any aggregation using groupby() and as_index=False.
- For example:

```python
grouped_df = df.groupby(['column1', 'column2'], as_index=False).apply(lambda x: x)
```
---