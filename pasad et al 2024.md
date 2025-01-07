https://direct.mit.edu/tacl/article/doi/10.1162/tacl_a_00656/120586/What-Do-Self-Supervised-Speech-Models-Know-About

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
Frame-level and span-level	
# Results
## Pretraining
Form of pretraining affects which layers correlate the most with word level properties.
## Temporal location
Closer to the center of each segment = more word-identifying
## Other
Different S3Ms, different complexity to use encoded knowledge. Visuallly grounded are better. Evaluation domain has impact, but layer-wise trends invariant. Easy to get near-perfect word discrimination with single-layer RNN.
# Conclusion: 
