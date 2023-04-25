# stream


Count min sketch algorithm

The Count-Min Sketch algorithm is a probabilistic data structure that serves as a frequency table of events in a stream of data. It uses hash functions to map events to frequencies, but unlike a hash table uses only sub-linear space, at the expense of overcounting some events due to collisions¹. 

It is used for summarizing data streams and allows fundamental queries in data stream summarization such as point, range, and inner product queries to be approximately answered very quickly; in addition, it can be applied to solve several important problems in data streams such as finding quantiles, frequent items, etc³. 

The time and space bounds we show for using the CM sketch to solve these problems significantly improve those previously known—typically from 1/ε2to 1/εin factor³. 

Working
The Count-Min Sketch algorithm works by aggregating the count of all items in your dataset into several counter arrays. Upon a query, it returns the item’s minimum count of all arrays, which promises to minimize the count inflation caused by collisions¹. 

The idea of the Count-Min Sketch is to use a collection of independent hash functions to hash each element in the stream, keeping track of the number of times each bucket is hashed to. The hope is that for each heavy hitter, one of the buckets it hashes to witnesses few hashes from other elements². 


Heavy Hitters
The Count-Min Sketch algorithm can be used to solve the heavy hitters problem. The heavy hitters problem is the problem of finding the most frequent items in a data stream. The Count-Min Sketch algorithm can be used to solve this problem by keeping track of the frequency of each item in the stream1.
To form a Count-Min Sketch, we repeat the modified bloom filter d times. We can use the idea of a count bloom filter to build an algorithm that correctly estimates the heavy hitter counts with high probability. We will simply repeat the count bloom filter independently d times and take the minimum value (Count-Min)2.

