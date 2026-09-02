# Lab 2 - URLCount Solution

## Approach

I implemented URLCount using the Hadoop Streaming API with Python. My solution uses two Python programs: `URLMapper.py` and `URLReducer.py`.

The mapper reads the input one line at a time and uses a regular expression to find URLs contained in `href="..."` attributes. For every URL it finds, the mapper outputs the URL as the key and `1` as the value.

The reducer receives the mapper output after Hadoop performs the shuffle and sort phase. It adds the counts for identical URLs and outputs only URLs that occur more than 5 times.

## Software

The solution requires:

- Python 3
- Hadoop 3.3.6
- Hadoop Streaming
- Git

The program was developed and tested first in the CSEL coding environment.

## CSEL Testing

I first tested the mapper and reducer locally using:

`cat input/file01 input/file02 | python URLMapper.py | sort | python URLReducer.py`

I then tested the solution using Hadoop Streaming with `make stream`. The Hadoop job completed successfully with both map and reduce reaching 100%.

For the current input files, the reducer produced 10 URLs with counts greater than 5.

## Dataproc Timing Results

### 2 Worker Cluster

Execution time: To be measured.

### 4 Worker Cluster

Execution time: To be measured.

### Comparison

The execution times of the 2-worker and 4-worker clusters will be compared after both Dataproc runs are completed.

## Resources

I used the course Lab 2 README, the Hadoop documentation linked from the lab, and the provided `Mapper.py`, `Reducer.py`, and `Makefile` starter files. I also used ChatGPT for guidance while developing, debugging, and understanding the implementation.

## Collaboration

I completed the implementation individually.
