
Sicherman and adi, 2023

https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=10097097

# Analysing discrete self supervised speech representation for spoken language modeling

Not a great paper (not include??)

RQ: what is the relation of discrete units to phonemes, speaker identity & gender?

# Model
- HuBERT
- CPC
In the context of GSLM

# Data
- TIMIT for phoneme analysis
- Librispeech for speaker and gender analysis



# Method
- ABX
- Clustering

- Discrete units from HuBERT and CPC, use MFCCs as baseline

V-Measure (a normalized mutual information score) between the discrete unites and speech properties (phonemes, speaker, gender)

- Decode the units to speech and transcribe the generated audio and measure transcription error.

- Circular resynthesis (CR)
resynthesize speech and apply speech to unit (with HuBERT & CPC) and compare the speech to unit on the original speech to the speech to unit on the resynthesized speech with unit-edit-distance measure.

They use the CR value to weight the k-means clustering to improve the discrete units in the model.