The encoder part is designed to be a bidirectional RNN, in order to make sure that the relevant information is stored in the vector, either in the start of the sentence or in the end of the sentence.

![image-20200214203248622](C:\Users\yun65\AppData\Roaming\Typora\typora-user-images\image-20200214203248622.png)



In the original encoder-decoder model in 2014[^1], 

![image-20200214210323250](C:\Users\yun65\AppData\Roaming\Typora\typora-user-images\image-20200214210323250.png)



The input sequence is mapped to a fixed-sized vector using one RNN, and then the vector is mapped into another RNN. 

The difference between the proposed model in this paper with the vanilla encoder decoder is that the input for each hidden unit in decoder also includes $c_{i}$. $c_{i}$ is known as the context vector that is different for each hidden unit in the decoder. 

$c_{i}$ depends on the sequence of $(h_{1},···，h_{Tx})$ . It is worth mention that $h_{i}$ contains information about all the input sequence with an emphasize on the $i$-th word of the input sequence. 

$c_{i} =  \sum_{j=1}^{T_{x}}\alpha_{ij}h_{j} $

The weight $\alpha_{ij} = \frac{exp(e_{ij})}{\sum_{k=1}^{T_{x}}exp(e_{ik})}$

with $e_{ij} = \alpha(s_{i-1},h_{j})$



$e{ij}$ is used to assess how well the inputs around position $j$ matches with output at position $i$ .  If it is highly correlated, the corresponding $\alpha_{ij}$ is higher, and contributes more to $c_{i}$. $e_{ij} = a(s_{i-1},h_{j})$ , which is used to score how well the inputs around position j and the output match. (But why $s_{i-1}$ and mentioned as $s_{i-1}$  just before emitting $y_{i}$ ????)

$a$ is a feedforward neural network, jointly trained with other variables. so does it mean that the loss from the decoder network can also be passed through the $a$ model to adjust the variable in it?

It‘s still quite vague how to back-prop through $\alpha$ , refer to the code!!!!!

The probability $\alpha_{ij}$ reflects the importance of the $h_{j}$ with respect to the previous hidden state $s_{i-1}$ in deciding the next state $s_{i}$ and generating $y_{i}$(which part of the source sentence to pay **attention ** to)

One way of visualization: visualize the $\alpha_{ij}$



[^1]: I. Sutskever. Sequence to sequence learning with neural networks. 2014  