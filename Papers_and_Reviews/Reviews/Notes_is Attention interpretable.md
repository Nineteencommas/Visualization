In the experiment, they run the model twice to investigate on the impact of some input sets $\Gamma’ \subset\Gamma$ 

First time we run the model without modification, second time we reform the attention distribution with $\Gamma'$ attention set to zero(zeroed out) erase based work????

Why first zero and then renormalize? To avoid that the intermediate representation artificially close to 0,(not in reality)

$p$ is original and $q_{\Gamma‘}$ which we erase attention for $\Gamma’$

一个是擦去前一个是擦去后

我们用了什么方法呢？ JS divergence and whether argmaxes of 前and后differ, indicating a decision 





一个问题：只有在very large的attention的时候才会有ΔJS 明显大于0的情况

二个问题： Only in classification , how about other problem like machine translation？？

