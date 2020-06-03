# A Collection of Cross-Sectional and Time-Series Generators


## Time-Series
[MTSS-GAN](https://github.com/firmai/mtss-gan) - Multivariate conditional time series simulation using stacked generative adversarial learning for multi-attribute generation.
  > Developed by Derek Snow @firmai
  
[Time-GAN](https://github.com/firmai/tsgan/tree/master/alg/timegan) - Multivariate time series generation with an emphasis on autoregression errors to preserve temporal correlations.
  > Developed by Jinsung Yoon, Daniel Jarrett, Mihaela van der Schaar, forked code and colab hosted by @firmai


## Cross-Sectional

### Privacy
[VAE-DP](https://colab.research.google.com/drive/1GR8Fx4zd7M-OKWI8gF20VwESS6Oml6Br) - Variational Autoencoder with Differential Privacy
  > Original model developed by [MIT](https://github.com/sdv-dev/SDGym), differential privacy included by Derek Snow @firmai

[PrivBN](https://dl.acm.org/doi/pdf/10.1145/3134428) - Privbayes: Private data release via bayesian networks

### General

[CTGAN](https://github.com/sdv-dev/CTGAN) - Conditional GAN for Tabular Data 

[TVAE] - 

[CLBN](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.133.9772&rep=rep1&type=pdf) - Approximating discrete probability distributions with dependence trees

[TableGAN](https://dl.acm.org/ft_gateway.cfm?id=3242929&type=pdf) - Data synthesis based on generative adversarial networks

[VEEGAN](https://papers.nips.cc/paper/6923-veegan-reducing-mode-collapse-in-gans-using-implicit-variational-learning.pdf) - Veegan: Reducing mode collapse in gans using implicit variational learning. [Chris Russell](https://www.turing.ac.uk/people/chris-russell) - Alan Turing.

```
A GAN variant that avoids mode collapse. Create a reconstruction network to map the data distribution to a Gaussian, but also to approximately reverse the action of the generator.  Intuitively, if the reconstructor learns both to map all of the true data to the noise distribution and is an approximate inverse of the generator network, this will encourage the generator network to map from the noise distribution to the entirety of the true data distribution, thus resolving mode collapse.
```



###### CTGAN:

Tabular data usually contains a mix of discrete and continuous columns. Continuous columns may have multiple modes whereas discrete columns are sometimes imbalanced making the modeling difficult. Existing statistical and deep neural network models fail to properly model this type of data. We design TGAN, which uses a conditional generative adversarial network to address these challenges.

### Other

[Evaluation](https://github.com/Baukebrenninkmeijer/On-the-Generation-and-Evaluation-of-Synthetic-Tabular-Data-using-GANs) - A range of implementation and evaluation metrics as part of a masters thesis by Bauke Brenninkmeijer.


We always want to compare our method with benchmarks, first we want to use the original data as is used in training synthesisers, then we want to sample each column using a uniform distribution, second we can sample each column using a gaussian mixture model if continuous and a probability mass function if discrete. 

