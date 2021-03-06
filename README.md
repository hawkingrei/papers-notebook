# 论文笔记

这个repo记录我平时阅读的paper并记录下笔记，希望自己不只是一个会拼凑代码的程序员。


## 目录(TOC)

* [论文笔记](#%E8%AE%BA%E6%96%87%E7%AC%94%E8%AE%B0)
   * [目录(TOC)](#%E7%9B%AE%E5%BD%95toc)
   * [数据结构]
   * [分布式(Distributed System)](#分布式distributed-system)
			
		* [存储(Storage)](#存储storage)
			* [Spanner](#spanner)
		* [一致性(Consensus)](#一致性Consensus)
			* [raft](#raft)
          * [Zookeeper](#Zookeeper)
   * [系统(System)](#系统system)
      
       * [文件系统(File System)](#文件系统file-system)
          * [F2FS](#f2fs)
          * [LFS](#LFS)

                 
#### Spanner
* [Spanner: Google’s Globally-Distributed Database](http://static.googleusercontent.com/media/research.google.com/zh-CN//archive/spanner-osdi2012.pdf)

```
// TODO Wait to read
```

* [MapReduce: Simplified Data Processing on Large Clusters](https://static.googleusercontent.com/media/research.google.com/zh-CN//archive/mapreduce-osdi04.pdf)  
* [Finding a needle in Haystack: Facebook’s photo storage](https://www.usenix.org/legacy/event/osdi10/tech/full_papers/Beaver.pdf)
* [In Search of an Understandable Consensus Algorithm (Extended Version)](https://pdos.csail.mit.edu/6.824/papers/raft-extended.pdf)
* [ZooKeeper: Wait-free coordination for Internet-scale systems](https://pdos.csail.mit.edu/6.824/papers/zookeeper.pdf)
* [PacificA: Replication in Log-Based Distributed Storage Systems](https://www.microsoft.com/en-us/research/wp-content/uploads/2008/02/tr-2008-25.pdf)

#### Time Series Database

* [Gorilla: A Fast, Scalable, In-Memory Time Series Database](http://www.vldb.org/pvldb/vol8/p1816-teller.pdf)



#### F2FS
 
[F2FS: A New File System for Flash Storage](https://www.usenix.org/system/files/conference/fast15/fast15-paper-lee.pdf)

随着NAND Flash被越来越多的应用到各式设备中，传统的文件系统以HDD为设计对象，已经不再适合于NAND flash。 因此论文设计了F2FS文件系统来提高NAND flash性能和寿命。

在flash中，即使写入一个字节，也需要擦除整个BLock,然后在写入数据，同时频繁的擦写容易造成SSD损坏，所以在SSD中采用out­ of ­place来更新，这里有别与HDD的in place。因此每次写操作都会使数据块的地址发生改变。在LFS中，如果leaf data block更新了，需要递归地修改direct index block，indirect index block等都需要改变，引起了Wandering tree问题。因此引入了NAT

同时F2FS引入了Multi-head logging，F2FS利用flash存储的并行性,可以同时操作多个log，来提高效率。F2FS还通过roll-forward recovery来加速fsync。
 
#### LFS

[The Design and Implementation of a Log-Structured File System](https://people.eecs.berkeley.edu/~brewer/cs262/LFS.pdf)

* [Large-scale cluster management at Google with Borg](http://static.googleusercontent.com/media/research.google.com/zh-CN//pubs/archive/43438.pdf)
* [The Bw-Tree: A B-tree for New Hardware Platforms](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/bw-tree-icde2013-final.pdf)
* [BzTree: A High-Performance Latch-free Range Index for Non-Volatile Memory](https://www.cs.cmu.edu/~jarulraj/papers/2018.bztree.vldb.pdf) 
* [High Throughput Compression of Double-Precision Floating-Point Data](http://cs.txstate.edu/%7Eburtscher/papers/dcc07a.pdf)

#### 数据结构

* [The Adaptive Radix Tree:ARTful Indexing for Main-Memory Databases](https://db.in.tum.de/~leis/papers/ART.pdf)
* [The ART of Practical Synchronization](https://db.in.tum.de/~leis/papers/artsync.pdf)



* [Orca: A Modular Query Optimizer Architecture for Big Data](https://15721.courses.cs.cmu.edu/spring2016/papers/p337-soliman.pdf)
* [Filter Before You Parse:Faster Analytics on Raw Data with Sparser](http://www.vldb.org/pvldb/vol11/p1576-palkar.pdf)
