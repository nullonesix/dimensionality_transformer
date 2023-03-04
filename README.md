# Dimensionality Transformer

We increase at dimensionality with every epoch. The reasoning being that optimization techniques
can get trapped in local minima. An increase in the dimensionality provides new pathways to move
around the local minima. However, if the model uses all dimensions immediately it might waste
dimensions on increased precision, instead of providing new pathways for local minima that might
only be encountered later on during training. Therefore, dimensionality growth is progressively
introduced by zeroing out large parts of early gradients and smaller parts of later gradients.
-- nullonesix
