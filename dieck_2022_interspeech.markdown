Dieck et al. 2022

https://www.isca-archive.org/interspeech_2022/dieck22_interspeech.pdf

# Wav2vec behind the Scenes: How end2end Models learn Phonetics

Investigated how the Wav2vec 2.0 model analysis speech: Frequency analysis, phonetic information. Different parts of the model encode information in a different manner. Influence of gender is high in CNN output but vanishes after temporal contextualisation. Context sensitive representations show more language related patterns

# questions
- Is wav2vec 2.0 an acoustic model or can it be broken down into a feature extractor and a temporal context analysis?
- Is it possible to derive fundamental phonetic concepts from the embeddings?
- arrangement of FVs closely resembled the vowel
triangle

# materials
- Common Phone corpus (total 116 hours, multiple languages)
- finetuned Wav2vec 2 English base model with a 102 phone symbols in the vocabulary, trained and tested on Common Phone corpus ~18 PER
- Selected frame that emitted a phone symbol (CTC is a state machine that outputs nothing if the state has not changed)
- Investigate the CNN (last layer) and transformer (last layer)

# method
- PCA on embeddings to investigate whether vowel triangle could be reconstructed and compare long and short vowel to see whether short vowels would be closer to the center of the vowel space
- PCA on embeddings to investigate obstruents and compare plosives and fricatives
- Compare PCA on embeddings of CNN and transformer to compare different encodings


# results

- embeddings encode vowel space similar to F1 & F2. 
- Shorter vowels are closer to the vowel space center.
- CNN embeddings encode gender (in vowel space shift)
- Transformer embeddings of vowels encode language information, probably based on phonotactic information (ie context)
- place and manner of articulation of consonants and representations depend on layers of model
- layer specificity of information encoding