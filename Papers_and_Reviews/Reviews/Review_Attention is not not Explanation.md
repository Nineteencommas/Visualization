# Review_Attention is not not Explanation 

Ideas to against: Attention is not explanation.

Approach: 4 alternative tests to determine when/whether can be used as explanation.

1. testing attention modules’ contribution to a model by applying a simple baseline where attention weights are frozen to a uniform distribution.

   Results: For some datasets, a frozen attention distribution performs just as well as learned attention weights -> randomly or adversarially-perturbed distributions are not evidence against attention.

2. expected variance in attention-produced weights by initializing multiple training sequences with different random seeds, allowing a better quantification of how much variance can be expected in trained models. We show that considering this background stochastic variation when comparing adversarial results with a traditional model allows us to better interpret adversarial results.

3. test attention distributions for their usefulness by using them as frozen weights in a non-contextual MLP

   Results: LSTM-trained wrights provide additional support for the coherence of trained attention scores, demonstrating a sense in which attention score, demonstrating a sense in which attention components indeed provide a model-agnostic meaningful interpretation for tokens in an instance. 

4. a model-consistent training protocol for finding adversarial attention weights.

   Approach: Train a model using a modified loss function which takes into account the distance from an ordinarily-trained base model's attention score, in order to learn parameters for adversarial attention distributions. 

Previous paper: 

1. Attention is not strongly correlated with other, well-grounded feature importance metrics, specifically gradient-based and leave-one-out methods. 
2. search for an alternative attention distributions which minimally change the prediction distributions, they found them which proves that the attention distributions are not explainable because they are not exclusive. Lack of comparable change in the prediction with alternative attention distributions. The problem with this approach is that they treat the output and the attention layer as an standalone unit.
3. In this paper, a simple MLP diagnostic network as an additional way for determining validity of attention distributions. 



Research Question: Attention might be explanation.

Background: 

1. Jain and Wallace argue that attention is not explanation for the reason that it's possible to find an alternative attention distributions which minimally change the prediction distributions. The author disagree with the statement. Attention scores and output should not be considered as a standalone score of the model.( ***Attention Distribution is not a Primitive.***)

2. Why Jain and Wallace are able to produce such results(different attention score same )?  It's quite easy for the final output layer to produce the same prediction result with different attention scores. ( ***Existence does not Entail Exclusivity.*** )

   

Approach:

Use the same setup as Jain and Wallace to train a base model.

1. test whether attention is necessary in the first place.(The result shows that no importance out score difference in the classification task)

1. propose a diagnosed model: