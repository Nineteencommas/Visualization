Attention is mainly achieved by the finding the distribution over attended-to input units, presented as showing the importance of inputs. 

But it can be not plausible enough that the attention weights and output are actually related. 

Ideally, the high attention weights are responsible for model outputs.

The intention of the paper is to empirically investigate the relationship between attention weights, inputs and outputs.

" Assuming attention provides a faithful explanation for model predictions, we might expect the following properties to hold. (i) Attention weights should correlate with feature importance measures (e.g., gradient-based measures);??????? (ii) Alternative (or counterfactual) attention weight configurations ought to yield corresponding changes in prediction (and if they do not then are equally plausible as explanations). "

![image-20200214221530340](C:\Users\yun65\AppData\Roaming\Typora\typora-user-images\image-20200214221530340.png)

The adversarial $ \widetilde{\alpha} $  is it like a different distribution of $a_{ij}$ which leads to the same probability distribution for output?

 gradient-based measures of feature importance ??

>Research questions and findings:
>
>Q：To what extent do attention weights related to the  measures of feature importance – specifically, those resulting from gradients and leave-one-out (LOO) methods
>
>A: Weak relationship
>
>Q:  If we use different attention weights, will we have different prediction results?
>
>A: No, even randomly permuting attention weights can lead to same predictions results. 

  By contrast, attention weights in simple, feedforward (weighted average) encoders enjoy better behaviors with respect to these criteria.  ????



Research Questions:

If attention can explain the workings of neural models, further expressed as two questions:

1. To what extent do attention weights related to the  measures of feature importance – specifically, those resulting from gradients and leave-one-out (LOO) methods.

2. If use different attention weights, will the model obtain different prediction results?

   ( We report that neither property is consistently observed by a BiLSTM with a standard attention mechanism in the context of text classification, question answering (QA), and Natural Language Inference (NLI) tasks.  )

Research Approach:



Things to mention and used in our own model: Bi-RNN, average and CNN to test the relationship between Attention and other measure scores.

Correlation between gradient and attention is tested on different datasets.





