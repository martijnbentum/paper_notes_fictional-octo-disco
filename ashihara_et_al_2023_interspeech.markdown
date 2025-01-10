# url
https://www.isca-archive.org/interspeech_2023/ashihara23_interspeech.pdf

# SpeechGLUE:How Well Can Self-Supervised Speech Models Capture Linguistic Knowledge?

GLUE -> General language understanding evaluation
SpeechGLUE speech version created with TTS one speaker

# Materials
GLUE text materials converted to speech with TTS single speaker
validated by applying ASR systems and computing ASR

# Methods
tests
- grammatical acceptability (CoLA)			unacceptable /acceptable
- sentiment analysis (SST-2) 			positive / negative
- paraphrase corpus (MRPC)	 semantics		equivalent / not equivalent
- question pairs (QQP) semantics	 	equivalent / not equivalent
- semantic textual similarity (STS-B) 		similarity score 1 - 5
natural language inference with sentence pairs:
- multi-genre natural language inference (MNLI) entailment / contradiction / neutral
- question-answering natural language inference (QNLI) entailment / not entailment
- recognizing textual entailment (RTE) entailment / not entailment
- winograd natural language inference (WNLI) entailment / not entailment

# Models
Speech
- Wav2vec 2 base large XLSR
- WavLM base large
- Hubert base large
- dat2vec

NLP
- data2vec
- Bert base large

baseline
fbank (MFFC)
phoneme ??
random initialised model

# probing
weighted sum of all hiddenlayersf ollowed by 256 dim linear layer with tah function, mean-poling across whole sequences and final linear layer for classification or regression taks

 
# results

								nlp			speech			chance
grammaticality		51.4		29.6				- 				mcc		wavlm
sentiment				90.5		82.7				50.9				acc		wavlm
semantics				79.2		75.7				68.4				acc		wavlm
semantics				85.4		83.3				63.2				acc		wavlm
semantics				82.8		79.5				-					acc		wavlm


grammaticality judgements much poorer compared to NLP, sentiment and semantics somewhat comparable.

# conclusion
speech models performed better than chance and baselines -> capture some general linguistic knowledge from speech alone






# bib

@inproceedings{ashihara23_interspeech,
  title     = {SpeechGLUE: How Well Can Self-Supervised Speech Models Capture Linguistic Knowledge?},
  author    = {Takanori Ashihara and Takafumi Moriya and Kohei Matsuura and Tomohiro Tanaka and Yusuke Ijima and Taichi Asami and Marc Delcroix and Yukinori Honma},
  year      = {2023},
  booktitle = {Interspeech 2023},
  pages     = {2888--2892},
  doi       = {10.21437/Interspeech.2023-1823},
  issn      = {2958-1796},
}