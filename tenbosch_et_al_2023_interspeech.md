https://www.isca-archive.org/interspeech_2023/tenbosch23_interspeech.html#

# Phonemic competition in end-to-end ASR models

-Use information-theoretic measures to analyse phonetic competition in wav2vec 2 model

-phonetic structure is well maintained in the cnn output but disappears in higher transformer layers

# Model
Wav2vec-xlsr

# Data

CGN (spoken dutch corpus)

# Method

1) kmeans clustering to create codebooks for cnn transformer layer (tf) 12 and tf 24 and mapped frames for specific phones to the codebook entries. Created histograms for each phone label codebook entry combination, converted in to conditional probability of a codebook entry given a phone label and subsequently computed the KL divergences between all phone probability vectors

2) trained and tested MLP phone classifiers on cnn and tf 1, 12 and 24 for pretrained and finetuned model

3) computed phone probability distributions for the runner ups and created a synthetic phone probability distribution based on broad phonetic class (BPC) and compared these distributions with KL divergence

4) computed percentage of phone runner ups that are in the same BPC as the ground truth phone label for the cnn output and multiple tf layers.

5) visualised the structure of the cnn output and tf 1 - 18 with MDS

# Results
1, 3, 4 & 5 show that phonetic structure in the hidden states is mostly present in the cnn output and early tf layers.

2 shows that phone classification is feasible based on the hidden states

3 shows that if the whole probability distribution of the MLP phoneme classification is taken into account this does not reflect BPC

4 shows that the runner up phone label does correspond to the BPC of the winning phone label for plosive, fricatives and some mid vowels, but this deteriorates for middle layers and later layers for fine tuned model.

5 shows that the early layers reflect phonetic structure (e.g. vowel triangle) but this is lost in later layers. 