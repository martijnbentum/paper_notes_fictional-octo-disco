Choi et al. 2024 

# Self-Supervised Speech Representations are More Phonetic than Semantic

https://www.isca-archive.org/interspeech_2024/choi24b_interspeech.pdf

RQ: Are they encoding semantic or phonetic features (or both)?
Is S3M performance based on semantic knowledge?

BoW for intent classification shows high performance on  Fluent speech commands (FSC)
Test to what extend s3m have semantic representations

Use slicing and pooling in different versions, to compare phonetic/phonological and semantic representation in the internal layers of [ wav2vec2.0-Base, -Large; Hubert-Base, -Large, XLS-R-300M, WavLM-Large ].
Trained on English or multiple languages (XLS-R-300M).

Used LibriSpeech for construction of pairs.

IV: Items/pairs: 
	- Synonyms: from Wordnet and Open Multilingual Wordnet synsets
	- near-homophones: CMU pronuncation dict -> normalized Levenshtein distance < 0.4 (is 0.1% procent of random word pairs)
	- Random word pairs (from shuffled list of words)
	- Same word pairs (instances of same word)
	- Same speaker pairs (only English)
x
	English vs.
	multilingual (no Same-speaker; near-homophone and synset pairs always pair English-other language words)

# Method

## DVs:
	
Slicing: feature slicing (take model states from activation for whole utterance) vs. audio slicing (slice audio, present only relevant slice, extract model state)
Pooling on mean (of all slices), center (of all slices), centroid (most similar in cosine to all slices).

Compaired word representations with cosine similarity
	-random
 	-synonym
  	-near homophone
   	-same word


??Trained multi-layer perceptron (MLP) with default scikit-learn parameters??



# Results
## English
- Slicing type: Feature slicing makes all pairs similar (reason: context present?)
- Pooling type: "We observe that (i) centroid pooling and
mean pooling retain more semantic content (synonyms) than
center pooling, whereas (ii) center pooling preserves more word
identity information (same-words) than both centroid pooling
and mean pooling. These differences suggest that the tempo-
ral center (center pooling) is not necessarily at the center of the
representation space (centroid pooling). Also, each framewise
representation within a single word may model different aspects
of speech. These implications urge future work on the intra-
differences of word representations. We use the mean pooling
for the remainder of our analysis."
- RQ: More phonetic than semantic, because more similarity between near-homophones than synonyms. [TL: But is the phonetic distance between near-homophone pairs comparable to the semantic distance between synonyms? And are there no phonetic overlaps between synonyms and v.v.?]
 Layers same layers good at semantics and phonetics. 
- Speaker information diminishes over layers. Hubert-Large and WavLM-Large maintain phonetic info to end, wav2vec2.0-Large does not (drops off). See Fig 3 for other models (picture less clear than for these three, only these three mentioned in text).

## Multilingual (results)
- also similarity for synonyms across languages. Still, closer representations for near-homophones than synonyms.

# Conclusion: 
No hierarchy phonetics/ semantics.
