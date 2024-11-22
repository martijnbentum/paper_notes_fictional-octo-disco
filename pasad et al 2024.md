Pasad et al.
A. Pasad, C.-M. Chien, S. Settle, and K. Livescu. What Do Self-Supervised Speech Models
Know About Words? Transactions of the Association for Computational Linguistics, 12:
372–391, Apr. 2024. ISSN 2307-387X. doi: 10.1162/tacl{\ }a{\ }00656. URL https:
//doi.org/10.1162/tacl_a_00656.
# What Do Self-Supervised Speech Models Know About Words? 
S3Ms encode acoustic/phonetic features, but may encode higher-level
# RQ: 
##(i) "how is word-related information distributed
across frames within a word segment? "
##(ii)
"in which layers, and how well, do S3Ms encode
segment-level pronunciation, syntactic, and se-
mantic information?"

# Method
Canonical correlation analysis (CCA) (not task-specific classifiers). CCA can be used with both discrete and continuous labels.
Word segment representations extracted in context.
## DVs:
### CCA correlation with 
- word identity (one-hot vector)
- word-level pronunciation variations (Acoustically Grounded Word Embeddings (AGWEs): written embeddings trained with acoustic embeddings)
- syntactic features (45-dim vector based on PoS)
- semantic features (from SemCor, WordNet-annotated Brown Corpus; vector has sense attribute to remove syntactic and other confounds in e.g., Word2Vec)
### Acoustic word discrimination
- Are two waveforms same word?
### Word segmentation
With training-free algorithm, using behavior frame-level representations near boundaries. Smoothed dissimilarity -> peaks in dissimilarity. 
- F1 scores etc. for word boundary detection.
### Sentence semantics
- correlation with similarities in corpus of spoken STS (corpus of sentence pairs annotated with sentence similarity)
## IV
Ten models
## Items
7k word instances.
For word ID:
- either as single frame (one of five locations)
- mean pool quarter of contiguous frames
- mean pool all frames
Other DVs: mean pooling.
# Results
Good for all tasks.
- Peak in middle layers for word identity
## Frame-specific
- AWD: less for some models
- "non-trivial word segmentation capacity" for all models, better if visually-grounded.
"Specifically, the single center frame and the 2nd and 3rd quarter spans are all as highly correlated with the word identity as the mean-pooled representations. These findings are consistent across all S3Ms analyzed."
## Pooled-span
## Pretraining
Form of pretraining affects which layers correlate the most with word level properties.
## Temporal location
Closer to the center of each segment = more word-identifying
## Other
Different S3Ms, different complexity to use encoded knowledge. Visuallly grounded are better. Evaluation domain has impact, but layer-wise trends invariant. Easy to get near-perfect word discrimination with single-layer RNN.
# Conclusion: 
