# Priority Queue
Priority queue is a queue output in the sequence according to their priority property. If output with decreasing priority sequence, we call it **Max-Priority Queue**; If output with increasing priority sequence, we call it **Min-Priority Queue**.

The three basic operations in a Min-Priority Queue:
* Insert: to insert a data to the queue
* IncreaseKey: Change the priority of the data, the key alias to the priority of data.
* ExtractMin: Get the data with max priority, and remove it from queue.

Six implementations:
1. Leftist Tree
2. Binomial Heap
3. Fibonacci Heap
4. Pairing Heap
5. Symmetric Min-Max Heap
6. Interval Heap

The first four data structures are called **Single-End Priority Queue(SEPQ)**, which means it can only get Minimum(Maximum) data from the Min(Max)-Priority Queue.<br/>
The last two data structures are called **Double-End Priority Queue(DEPQ)**, which means it can get the minimum and also maximum data simultaneously.
