Algayres et al., 2023

https://aclanthology.org/2023.emnlp-main.182.pdf

# Generative Spoken Language Model based on continuous word-sized audio tokens

- Is it possible to train a generative spoken language model (GSLM) based on larger audio embeddings (text based GLM show that word / subword outperform character based models)
   - How to create larger audio embeddings (200 ms) -> no finite lexicon as with text based LMs
- Audio embeddings are challenging
	- boundary problem -> finding word boundaries is non-trivial
  - clustering problem -> clustering speech segments is non-trivial due to the invariance problem

# Lexical embedder

Learns a mapping between acoustic space (with phonetic properties) and lexical space (with semantic and syntactic properties)

Training of acoustic embeddings is done with a baseline approach  -> set a boundary every 200ms

The acoustic embeddings are based Wav2vec 2 base transformer embeddings (layer 8).

# Very short section on interpretability

sWUGGY pairs of word / non-word synthesised by Google TTS
sBLIMP pairs of synthesised sentences syntactically correct / incorrect

The model should attribute high probability to the correct element in the pair

- they compare acoustic and lexical embeddings with ABX sem & pos
Based on distance between embeddings the model should assign lower distance to the embeddings from within category items compared to the distractor. No information is given if / how the embeddings (acoustic / lexical) are aggregated over a word, reference is made to:
Algayres et al., 2022. Dp-parse: Finding word boundaries from raw speech with an instance lexicon.

- Normalized edit distance (NED)
Probably based on word segments (based on human annotations). The associated embeddings (probably acoustic and lexical embeddings) are paired based on distance (probably cosine similarity) with k-NN. Starting with the higher similarities we retrieve as much pairs to cover the whole set.
- The phoneme transcription of the pairs can be compared with the NED. The final NED is the average over all pairs.

- t-SNE plots to visualize the difference between the acoustic space and the lexical space.

