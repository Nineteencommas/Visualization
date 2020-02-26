Transformer is the first transduction???? model relying entirely on self-attention to compute representations of its input and output without using sequence-aligned RNNs or convolution. 

![image-20200214230138212](C:\Users\yun65\AppData\Roaming\Typora\typora-user-images\image-20200214230138212.png)

Encoder and decoder construction

Encoder: N=6 identical layers.  Each layer two sub-layers. The first is a multi-head self-attention mechanism, second one is a simple.

Decoder: The decoder is composed of a stack of N = 6 identical layers. In addition to the two sub-layers same as the encoder, an additional masked is added, to make sure that the position $i$ only depend on the known outputs at positions less than $i$

What is the attention function in the model?

map a query and a set of key-value pairs to an output, where query ,keys values, and output are all vectors. Output is computed as a weighted sum f the values, and weight is computed by a compatibility function of the query with the corresponding key.







