---
layout: post
title: 'MapReduce'
date: '2023-08-25 16:00:30'
---

## lets read the MapReduce paper

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

# from the notes 

<pre>
Input1 -> Map -> a,1 b,1 
Input2 -> Map ->     b,1
Input3 -> Map -> a,1     c,1
                  |   |   |
                  |   |   -> Reduce -> c,1
                  |   -----> Reduce -> b,2
                  ---------> Reduce -> a,2

Word-count-specific code
  Map(k, v)
    split v into words
    for each word w
      emit(w, "1")
  Reduce(k, v_list)
    emit(len(v_list))
</pre>

so this is my understanding of how distributed word count works as compared to serial word count.

#### the serial approach 

we have a file with words. we initialize a big dictionary <word: count> and store the results in it. we read one word at
a time. if curr_word is not in the dictionary, add it to the dictionary with the count 1. Otherwise, increment the
dictionary at curr_word by one. 

#### the distributed approach

We need to do a word count on a relatively big file of suppose 100,000 words in it and suppose our network has 11 nodes
(1 master + 10 workers) on it so our split could be into 10 files of size 10,000 words each. 

first those files go to the workers to finish the mapping phase. In the mapping phase, the workers produce a function call **emit(word, "1")** and write it to some intermediate files. <key, value> => <word, 1>.

after the mapping phase has finished, the worker nodes that have been designated to actually do the reducing phase which is accumulating 
or aggregating the values prodcued by the mapping. so basically adding up the the ones or in the given code example above it just gets 
the number of occurrences of a given key using the **len()** function call.

this should be a good overview of mapreduce.
