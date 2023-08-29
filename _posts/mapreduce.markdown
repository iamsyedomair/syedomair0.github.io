---
layout: post
title: 'MapReduce'
date: '2023-08-25 16:00:30'
---

# lets read the MapReduce paper

source: [paper](https://pdos.csail.mit.edu/6.824/papers/mapreduce.pdf)

MapReduce is a programming model designed to simplify processing of large datasets across distributed computing clusters.

### motivation

mapreduce was developed as an abstraction to abstract away all the intricacies of dealing with distributed data processing
making it easier to scale computers across a cluster of machines.

### the model

two main phases. "map" and "reduce"

#### map

in the map phase the data is distributed into smaller chunks and a function to process it is mapped on each chunk. extracts important information
and emits key-value pairs. and then they are sorted and grouped by key. 

#### reduce

the reducer processes the grouped data and performs computations and aggregations as needed.

### fault tolerance

mapreduce provides builtin fault tolerance by periodically saving intermediate data to stable storage. 

### applications

- distribured grep
- distribured sort
- inverted index construction
- reverse web link graph

### implementation

![mapreduce execution](/assets/mapreduce.jpg)

## distribured word count


