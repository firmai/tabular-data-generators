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

###### CTGAN:

Tabular data usually contains a mix of discrete and continuous columns. Continuous columns may have multiple modes whereas discrete columns are sometimes imbalanced making the modeling difficult. Existing statistical and deep neural network models fail to properly model this type of data. We design TGAN, which uses a conditional generative adversarial network to address these challenges. In CTGAN, we invent the ```mode-specific normalization``` (In CTGAN, we use variational Gaussian mixture model (VGM) to normalize continuous columns 25% improvement) to overcome the non-Gaussian and multimodal distribution (Section 4.2). We design a ```conditional generator``` (imbalanced data; 20% improvent) and ```training-by-sampling``` (conditional loss) to deal with the imbalanced discrete columns (Section 4.3). Ablation study necessary. They use  WGANGP. The identity (original data) always had the best performance. 

[TVAE] - Variational autoencoder (VAE) for mixed-type tabular data generation. VAEs directly use data to build the generator;

###### TVAE:
Benefit here is that no conditioning is used for imbalanced data and this model still performs at a similar level to CTGAN above. On real datasets,TVAE and CTGAN outperform CLBN and PrivBN, whereas other GAN models cannot get as good a result as Bayesian networks. 

TVAE outperforms CTGAN in several cases, but GANs do have several favorable attributes, and this does not indicate that we should always use VAEs rather than GANs to model tables. The generator in GANs does not have access to real data during the entire training process; thus, we can make CTGAN achieve differential privacy [14] easier than TVAE. (This might not be true, it has to be tested)

[CLBN](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.133.9772&rep=rep1&type=pdf) - Approximating discrete probability distributions with dependence trees

###### CLBN and PrivBN

For simulated data from Gaussian mixture,CLBNandPrivBNsuffer because continuousnumeric data has to be discretized before modeling using Bayesian networks. With respect to large scale real datasets, learning a high-quality Bayesian network is difficult. So models trained on CLBN and PrivBN synthetic data are 36.1% and 51.8% worse than models trained on real data.


[TableGAN](https://dl.acm.org/ft_gateway.cfm?id=3242929&type=pdf) - Data synthesis based on generative adversarial networks

[VEEGAN](https://papers.nips.cc/paper/6923-veegan-reducing-mode-collapse-in-gans-using-implicit-variational-learning.pdf) - Veegan: Reducing mode collapse in gans using implicit variational learning. [Chris Russell](https://www.turing.ac.uk/people/chris-russell) - Alan Turing.

###### CTGAN:

A GAN variant that avoids mode collapse. Create a reconstruction network to map the data distribution to a Gaussian, but also to approximately reverse the action of the generator.  Intuitively, if the reconstructor learns both to map all of the true data to the noise distribution and is an approximate inverse of the generator network, this will encourage the generator network to map from the noise distribution to the entirety of the true data distribution, thus resolving mode collapse. There was a previous [iteration](https://arxiv.org/pdf/1811.11264.pdf) that did not use conditional GANS. 




### Other

[Evaluation](https://github.com/Baukebrenninkmeijer/On-the-Generation-and-Evaluation-of-Synthetic-Tabular-Data-using-GANs) - A range of implementation and evaluation metrics as part of a masters thesis by Bauke Brenninkmeijer.


We always want to compare our method with benchmarks, first we want to use the original data as is used in training synthesisers, then we want to sample each column using a uniform distribution, second we can sample each column using a gaussian mixture model if continuous and a probability mass function if discrete. 

