# Hadoop-In-Action-Introductory-Patent-Dataset-Analysis
A basic introductory example of hadoops mapreduce libraries to load and analyse large datasets in this case a US patent dataset sourced from [here](https://www.nber.org/research/data/us-patents) , This is an implementation and extension of Ideas from the book *Hadoop in Action* by Chuck Lam.

## Idea

While small datasets can be handelled by python scripts directly , large datasets ( in the order of 50+TB ) cannot be directly loaded in to memory and processed , MapReduce algorithms were initially developed with this problem in mind . Hadoop abstracts out the details of the distributed systems and takes complete care of handling them . This project is a simple example where we load a 250 MB odd text file , to which we apply a basic map reduce function to come up with a frequency distribution plot for the given patent dataset .

After extraction of the frequency distribution data , using this small python snippet we have obtained the following output.
#### CODE
```python
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("data",sep ='\t',header = None)
plt.yscale('log')
plt.xscale('log')
plt.xlabel("Number of Citations")
plt.ylabel("Number of Patents")

plt.plot(data[1],marker = '.',color='darkslateblue')
plt.show()
```
#### OUTPUT
![alt text][logo]

[logo]: https://github.com/jayantakumar/Hadoop-In-Action-Introductory-Patent-Dataset-Analysis/tree/master/finalOutput/output.png "Output"
