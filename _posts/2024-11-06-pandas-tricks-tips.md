---
layout: post
title: "Interesting pandas tips and tricks"
date: 2024-11-06
author: Ash Parajuli
---

Pandas is a powerful python library for data manipulation and analysis. I've learned some interesting pandas techniques that I thought is worth documenting for others and also as a personal learning.

## Working with parquet files
- Important to install right dependencies like pyarrow or fastparquet for handling such files in pandas.

## Monitoring loading of large data files
- Integrating tqdm in the code to see a progress bar
- Using tqdm with pandas for progress tracking especially when iterating over row or performing transformations on large dataframes.