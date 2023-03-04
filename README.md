# Dimensionality Transformer

We increase at dimensionality with every epoch. The reasoning being that optimization techniques
can get trapped in local minima. An increase in the dimensionality provides new pathways to move
around the local minima. However, if the model uses all dimensions immediately it might waste
dimensions on increased precision, instead of providing new pathways for local minima that might
only be encountered later on during training. Therefore, dimensionality growth is progressively
introduced by zeroing out large parts of early gradients and smaller parts of later gradients.

The same technique can be applied to any kind of neural network.

As a preliminary test we compare the perplexities on a short language modelling task:

# Without Dimensionality Growth:

| end of epoch   3 | time: 38.23s | valid loss  5.64 | valid ppl   281.95
| End of training | test loss  5.55 | test ppl   257.58

# With Dimensionality Growth:

| end of epoch   3 | time: 37.22s | valid loss  5.57 | valid ppl   261.23
| End of training | test loss  5.48 | test ppl   238.97
