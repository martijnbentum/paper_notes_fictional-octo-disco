Millet & Dunbar, 2022

https://arxiv.org/pdf/2205.15819

# Do self-supervised speech models develop human-like perception biases?

- What kind of representational spaces do the models construct?
- Is there specialisation toward a specific language (like humans for their native language)?

# Models
- wav2vec 2.0
- HuBERT
- CPC (contrastive predictive coding)
Pre-train a model on English (600 hours common voice), French (600 hours common voice) and acoustic scenes (~600 hours audioset), 400k updates (ie. training steps)
MFCC is used as a baseline (window 25 ms, stride 10 ms)

- Deepspeech, comparison supervised model
Trained on same data but with phoneme labels

- They use the best performing layer (Transformer for self-supervised models / RNN for Deepspeech)

training code:
https://github.com/JAMJU/Sel_supervised_models_perception_biases


# Method
- Compare perceptual spaces of the models with those of French and English speaking human listeners with phone discrimination experiments
- ABX discriminability metric (Schatz 2016)
- Compute DTW (dynamic time warping to aggregate frame-level cosine distance along the warping path. Higher score better discriminability
- Log-likelihood of binary regression model of responses (to compare items) and Spearman’s correlation between the models and participants (to compare reponses for a specific contrast


# Data
- Perceptimatic, benchmark dataset with 662 phone contrasts: https://docs.cognitive-ml.fr/perceptimatic/


# Results
- CPC shows a small native language effect; Supervised model (deepspeech) shows strongest native language effect
- Wav2vec 2 & HuBERT develop universal speech perception space
- Self supervised models are best at predicting human discrimination at stimuli level, but worse than MFFC when human results are averaged per contrast
(they did not test finetuned Wav2vec 2 / HuBERT CPC)
(they only investigated 1 (best performing layer) in the model)




# Other
Dataset:
- Interspeech 2008 Consonant challenge (Cooke and Scharenborg, 2008)
- Perceptimatic database,  Perceptimatic database
(Millet et al., 2019; Millet and Dunbar, 2020a,b;
Millet et al., 2021) 
https://docs.cognitive-ml.fr/perceptimatic/