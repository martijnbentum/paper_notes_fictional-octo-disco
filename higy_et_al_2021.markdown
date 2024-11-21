Higy et al., 2021

https://aclanthology.org/2021.blackboxnlp-1.11.pdf

# Discrete representations in neural models of spoken language

RQ: How to best analyse discrete units in SSL models?
What is the equivalence between VQ layers and linguistic units (morphemes, syllables & phonemes)

#  Models
- SSL model (van Niekerk et al. 2020)
- visually grounded model similar to Harwath et al. 2020

# Data
- Zerospeech 2020
- Flickr8k

# Method

- NMI normalised mutual information between codevector? and phoneme label

- DC diagnostic classifiers, a probe trained to predict information of interest (linguistic annotation - phoneme label) based on a neural representation 

# Results

# Conclusion

Vector quantisation induces representations that correlate moderately with linguistic units.