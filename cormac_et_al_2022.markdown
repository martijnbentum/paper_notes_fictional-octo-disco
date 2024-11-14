Cormac et al. 2022 

# Domain-Informed Probing of wav2vec 2.0 Embeddings for Phonetic Features

Use probing to investigate phonetic and phonemic representation in the internal layers of the wav2vec 2 model.

Used pre-trained base model wav2vec 2 model trained on Librispeech corpus (960 hours, English).

Used TIMIT dataset

Averaged embeddings over the length of a phoneme as transcribed in TIMIT, for each transformer layer.

Trained multi-layer perceptron (MLP) with default scikit-learn parameters

# Results
- Best performing phoneme classification probes start at middle layer, performance drops at the last layers.
- Manner of articulation classification -> performance rather flat over layers. Vowel / closure best performing. Affricative worst performing (still .82 % correct)
- Place of articulation -> performance flat, worst result .7 % correct. (plot hard to interpret, to many colors)
- confusion matrix
- dendogram -> development at later layers, representations of obstruents become more positional less acoustic.

Label imbalance was not addressed (just accuracies reported)


