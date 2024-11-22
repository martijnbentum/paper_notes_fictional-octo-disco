Higy et al., 2021

https://aclanthology.org/2021.blackboxnlp-1.11.pdf

# Discrete representations in neural models of spoken language

RQ: How to best analyse discrete units in SSL models?
What is the equivalence between VQ layers and linguistic units (morphemes, syllables & phonemes)

Models are trained on limited data, results might be hard to relate to other papers. Nice explanation and comparison of different methods (i.e. RSA, ABX, NMI, DC) 

#  Models (pre transformer)
- SSL model (van Niekerk et al. 2020) trained on 15 hours of speech
- visually grounded model similar to Harwath et al. 2020, trained on 6000 images and 34 hours of speech

# Data
- Zerospeech 2020
- Flickr8k

# Method

- NMI normalised mutual information between codevector? and phoneme label

- DC diagnostic classifiers, a probe trained to predict information of interest (linguistic annotation - phoneme label) based on a neural representation 

- ABX compare phoneme triplet representations with a distance metric

- RSA representational similarity analysis, correlate distances in two spaces (e.g. phonemes, embeddings)

# Results
_(models are trained on tens of hours of speech)_

Different methods reveal different results:
- DC vs NMI are similar (as expected)
- (DC & NMI) vs RSA -> rsa is sensitive to the purity of the representation (if the discrete representation encodes speaker identity in addition to phoneme identity this will hurt performance)
- ABX vs rest
results are most divergent compared to the other metrics
DC, NMI & RSA were tested on full utterance, ABX only on phoneme trigram

# Conclusion
_(models are trained on tens of hours of speech)_

- Vector quantisation induces representations that correlate moderately with linguistic units.
- Since the different metrics reveal different results, it is advisable to use multiple analyses to corroborate results.
