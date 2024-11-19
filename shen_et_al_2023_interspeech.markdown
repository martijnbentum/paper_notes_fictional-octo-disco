Shen et al., 2023

https://www.isca-archive.org/interspeech_2023/shen23_interspeech.pdf

# Wave to Syntax: Probing spoken language models for syntax

- Test the encoding of syntax in several self-supervised and visually grounded models of spoken language

# Models

- wav2vec 2.0 (speech based)
- HuBERT (speech based)
- FaST-VGS (visually grounded, SpokenCOCO)
- Fast-VGS+ (visually grounded, SpokenCOCO & LibriSpeech)
- BERT (text based)
- BoW (bag of words, baseline)

# Data
- SpokenCOCO, image, caption, recording of spoken caption
- Librispeech, audiobooks 

# Method

- Mean-pooling along time axis of hidden state outputs of the models.
- Use stanza parser to generate constituency trees for all utterances.

- TreeDepth Probe (figure 1), predict the depth of the constituency tree of a given utterance
- TreeKernel Probe (figure 2), RSA (representational similarity analysis) -> correlate similarity structures of two representational spaces. Cosine similarity is used a similarity between vectors in the input space (model embeddings) and pairs in the output space (pairs of syntax trees).
  - Tree kernel is a way of measuring similarity between syntactic tress.
   - the trees were delexicalized to only probe on structure and not word overlap.

# Results

TreeDepth, spoken language models best syntax encoding in middle layers, adding word count features to embeddings improves performance of the probe. Syntactic information is encoded more strongly in text models (ie. BERT) across all layers.

Treekernel, spoken language models (finetuned wav2vec 2 large) come close to text model results.

Since performance is on par with BoW it could be the case that syntactic representation is entangled with lexical representations rather than being abstract.