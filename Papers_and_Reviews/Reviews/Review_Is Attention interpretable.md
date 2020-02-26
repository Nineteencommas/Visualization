# Review on 'Is Attention Interpretable?‘

* What the paper is all about?

Research Question: if attention can be used to explain the decisions models make. 

Research Approach: Manipulate attention weights in already-trained text classification models and analyzing the resulting differences in their predictions. Three tests are done:

>1. Zero out the most significant attention weight and compare the output with the original model's output, to see if $\Delta JS$ is larger than 0.
>
>2. If decision flips after zeroing  attention.
>3. Try to find the appropriate ranking method and if zeroing out certain set of attentions will result in the decision flip.

Results: 

>1. Indeed, in most of the cases $\Delta JS$  are larger than 0. However, significant different of the two models only occurs when attention weights are very large.
>
>2. For different dataset, majority of decisions do not flip, both for zeroing out an important attention and a random attention.
>3. A set of attention need to be zeroed out for the results to flip. Gradient ranking and Gradient * Attention appears to have smaller size of such sets. Also worth mention that RNN models outperform Convolution models in finding a smaller set.

Conclusion: Attention can explain the output for text classification to some degree. However, attention is not determinant factor for the output. 

* What is special about this paper?

Low level interpretability: examine how well attention represents the importance of intermediate quantities, which may themselves already have changed uninterpretably from the model's input.

* Further work can be done:

The work of the paper focus on text classification. But for machine translation, the decision flip are not that easy to identify meaningful differences. Further work can be done in the field of finding an analogous informative threshold in changes to model outputs.

Another limit is that the highest attention weights should identify the most influential representations in pushing towards any output class, not just the argmax.





