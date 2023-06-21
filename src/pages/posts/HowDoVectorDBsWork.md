---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Question: How do vector databases work?'
pubDate: 2023-04-01
description: 'Looking into how vector indexes work, an intuitive explanation.'
author: 'Stanislaw Kalinowski'
color: '2BA5FF'
---
**********What I know:**********

Hello there, so I’ve been seeing plenty of talk on vector databases, and I didn’t really know how they worked. I understood how databases work & I understood how vector embeddings work. But I didn’t know how vector databases worked, specifically in terms of how they speed up vector search.

I know bunch about databases and their different designs. Databases are essentially tools that store and organize data. They come with different formats and implementations, but they have the same core purpose: to make it easier for us to access the information we need. Databases usually have some sort of pre-organization of the data called an index. These indexes give us a way to access data quicker.

I also know about embeddings. Embeddings are representation of data as a vector, a column of numbers. These representation can be made through a model or some other method of creating a representation, like Bag-of-Words. But what matters is that embeddings capture some sort of representation of what they encode. So if we are encoding a picture, text, or some other data — it is put through the embedding function and a vector comes out representing the data.

With our embeddings, we can start comparing them. There are a number of comparison functions we could use such as cosine similarity, L2 norm, or even creating a custom comparison function. The comparison function works by taking in the two vectors and outputting a number representing the similarity.

********************************What I do not know:********************************

The concepts of databases and embeddings, I understand, but what I didn't know is how vector databases work to speed up search. I knew these databases used some sort of index to speed up the search process. However, I wasn’t actually sure what kind of indexes they used or how they worked. So I wanted to learn more about them and the mechanics behind speeding up search.

Additionally, I was curious about the tradeoffs that come with using these indexes. Balancing tradeoffs is important, and it’s good to understand what “buttons” we have available when setting up our vector databases.

**So heres what I found out:**

Lets setup our base naive approach first:

→We have a collection of vectors

→We have a comparison function, it takes two vectors and outputs a number representing similarity

→We have an input vector, that we want to find the closest vector in our collection.

![VDB_Setting.PNG](/Images/HowDoVectorDBS/VDB_Setting.png)

The naive way to find the closest element in our collection is to go through each element one by one and run the comparison function. And it’s clear that this method won't scale. With each additional vector added directly adds another comparison, a single comparison is small, but they add up as our collection grows and we process more input. Our objective is to lower the number of comparisons while still finding an accurate output.

******ANN******

This is where the first intuitive approach comes in. 

What we can do is grab some vectors from our collection and deem them as representatives. 

With our remaining vectors, we compare them to each representative and find the closest one, then put the vector in the according representatives “bin”. So each representative has its own collection, and we go through all the vectors and place them accordingly.

Now when we get an input, we first compare it only to the representatives, find the closest, and then get the representatives bin and compare our input vector to the ones in the bin. We have now cut down a fraction of the comparisons! We are only comparing with the representatives plus the vectors found in the bin.

![VDB_Bin.PNG](/Images/HowDoVectorDBS/VDB_Bin.png)

You might be thinking that this method does not always give us the best match. What if the second closest bin has the closest vector? And you are right, this method is an **approximate nearest neighbour method(ANN)**. We get an approximate vector and are not guaranteed to find the closest. 

But we are not limited to searching just the closest bin, we can look at the two closest bins, or three, or etc. So if we want more accuracy, we can choose to trade of speed for a more though search.

A more formal version of this method is a clustering method called **Inverted File Index(IVF)**. It constructs the index in a better way than just randomly picking representatives. But the principles of the idea still hold, we have representative vectors which we compare with our input, and then we get the collection of the representatives and search through that, and conclude with our closest match.

Our “knobs” are picking the number of bins to search, but we also have control in the way we construct our bins. We can pick how many representatives we want, where usually it's a fraction of the size of our collection.

Done? Well, the computer scientists eggs us on, “Oi, we can do better than that!”.

We have reduced the number of comparisons, but as our collection scales, we still end up searching through a lot of vectors. Increasing the number of bins doesn't help us with scaling, it will always be some fraction of our collection. We need a better way of searching through vectors, we need a way to get information from each comparison.

**HNSWG**

What info do we get with one comparison?

Well, there is a similar idea found in binary search.  In binary search, we compare with the middle element and cut out the half we don't need. With each comparison, we get closer and closer to our answer. 

So we want to take this idea and use it for our vector search. But vectors are different, we can’t just sort them on a line like in binary search. However, we do have a measure for closeness. Therefore by using our comparison function, we can construct a graph, and use the graph to move closer and closer with each comparison!

To build our graph, each vector in our collection is a node. Then for each node, we compare and find the k closest nodes, and make them the edges. This then gives us a graph we can use, awesome.(Connectivity is a concern, but there are techniques to make it fully connected, lets not worry about those details right now)

To search with our graph, we begin at any node, compare our input vector to the node and its edges. If one of the edges is closer to our input than that becomes our new main node, and repeat. Each iteration now moves us closer and closer to the answer.

But there is a problem, with a lot of nodes, our traversal can get quite slow.  It can take many iterations to reach the closest vector and this is especially influenced by our starting vector.

This is where the our next idea comes in, skip lists! 

The idea is to make a graph which lets us move further with each step. Then after using this graph, we go to the same spot in our main graph and find the precise answer.

We do this by constructing multiple graphs. We start with a top graph which only has a small number of nodes. Because it has fewer nodes, each edge is going to be “longer” and each iteration will move us further. Then once we reach the closest node, they are connected to a more dense graph underneath. We then repeat the process, and we continue doing this till we reach the minimum of the bottom layer. 

![VDB_Layers.PNG](/Images/HowDoVectorDBS/VDB_Layers.png)

![VDB_Graph.PNG](/Images/HowDoVectorDBS/VDB_Graph.png)

This method is more formalized as the **Hierarchical Navigable Small World Graphs(HNSWG).** There are a number of different “knobs” we can use to control performance. We can pick the number of layers as well as the number of edges each node has. Since this is still an approximation method, we don't have to find the absolute closest match in each layer, we can choose to stop after a certain amount of iterations, allowing us to create a more consistent search time. 

One caveat to this method is the storage requirements. Please keep in mind that the indexes require some space to store them. Therefore if you opt to use this method, be mindful of the storage upkeep of the graph layers!

So now we are getting some nice scaling! Yeah!

Then the computer scientist is enjoying his hash browns. Of course! How could we forget about hashing!

******Hashing!******

Hashes are great, they might not always be the answer, but they come with properties computer scientists love, constant time. The next idea diverges a bit from the last two because it’s based on hashing, but its hashing with a twist. 

Instead of avoiding collisions, we are trying to create collisions. Specifically we want to construct hash tables where similar vectors will collide with each other. If we achieve this, then our search process will consist of a few calculations and a few comparisons.

So we have two parts to the process, the hash calculations and comparing them with candidates.

What matters is that we need to develop a hash to take in vectors and group them based on similarity. This problem is one we glossed over earlier, putting vectors on a line. 

There are a number of approaches to how we could create these hashes. In all honesty my understanding of these methods is a bit fuzzy at best. What matters is we put our vector through a function and a value comes out, giving an index, and we want similar vectors to output the same index.

![VDB_Hash.PNG](/Images/HowDoVectorDBS/VDB_Hash.png)

With any such hashing method, because we are boiling vectors down to a point, we will loose some nuance with our hashing. We are transforming them from multidimensional vectors to single point indexes!

To help alleviate this, we can have multiple hashes. Our vectors can be chunked up by sections, and so these sections can represent distinct characteristics of our vector. We now have a fixed set of hashes to calculate, and we take a look at collisions. We can choose to compare each collision, or we choose to only grab candidates where j many hashes collide.

You might notice how this method is kinda similar to our first binning method, except instead of making a number of comparisons with representative vectors, we use a fixed set of hash functions which determine our second phase of comparisons.

**************************************Vector Quantization**************************************

Lastly, lets circle back and discuss a concept relevant to the storage part of vector databases, dimension reduction. When we have a lot of vectors, the column of numbers can begin to take up a bit of memory. We can reduce the memory by making our vector smaller, vector quantization. There could be a number of quantization methods, one approach it to break up the vector into parts, let’s say in threes. Then for each section of three we take the middle value. This process then gives us a new vector representing the old one and we reduced the space requirements by a third, nice.

![VDB_Quant.PNG](/Images/HowDoVectorDBS//VDB_Quant.png)

 

So thats pretty much it, just a high level overview of vector databases. Hopefully you intuition has been built up. I didn't want to focus on the particular maths nor the database portion of worrying about page tables and being memory aware. 

You now have an idea of the techniques and can look up anything.

If you want to actually use them then here is a good resource I found: