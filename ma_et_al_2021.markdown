# D. Ma, N. Ryant, and M. Liberman. Probing acoustic representations for phonetic properties.
In ICASSP 2021 - 2021 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP), pages 311–315, 2021. doi: 10.1109/ICASSP39728.2021.9414776

https://arxiv.org/pdf/2010.13007v3

# Data
TIMIT (different variants)

# Models
Wav2Vec, vq-Wav2Vec, Mockingjay, DeCoAR (and as baseline fbank and MFCCs)

# Method
Probing: three versions: Logistic Regression, SVM, simple feedforward NN.
Task: phone classification (does frame belong to specific class of phone(me)), feature classification (vowel, fricative, sonorant, all binary), speech (vs. non-speech) classification

ALl classifier input first reduced to 400 dimensions using Singular Vector Decomposition.

# Results
NN on models usually better than on acoustics, but especially for phone classification.  Best performance with DeCoAR (which is simplest).
