# Tagin POS Corpus v1.0

[![Hugging Face Dataset](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-repleeka%2FTagin--POS--Corpus--v1.0-FFD21E)](https://huggingface.co/datasets/repleeka/Tagin-POS-Corpus-v1.0)
[![Paper DOI](https://img.shields.io/badge/DOI-10.13053%2FCyS--30--3--6642-blue)](https://doi.org/10.13053/CyS-30-3-6642)
[![License: CC BY-NC-ND 3.0](https://img.shields.io/badge/License-CC%20BY--NC--ND%203.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-nd/3.0/)
[![Language: Tagin (tgj)](https://img.shields.io/badge/Language-Tagin%20(tgj)-green)](#tagin-language)

This GitHub repository documents the **first silver-standard Part-of-Speech (POS) tagged corpus** for the **Tagin language (ISO 639-3: `tgj`)**, a low-resource Tani language spoken in Arunachal Pradesh, India and South-Tibet, China.

> **Dataset Hosting:** The full dataset is hosted on Hugging Face at **[`repleeka/Tagin-POS-Corpus-v1.0`](https://huggingface.co/datasets/repleeka/Tagin-POS-Corpus-v1.0)**.

This resource accompanies the following publication:

> Tungon Dugi and Koj Sambyo. **A Silver-Standard POS Corpus and Baseline Models for Tagin, a Low-Resource Language.** *Computación y Sistemas*, Vol. 30, No. 3, 2026, pp. 2009–2026. DOI: [10.13053/CyS-30-3-6642](https://doi.org/10.13053/CyS-30-3-6642) · [Article page](https://www.cys.cic.ipn.mx/index.php/CyS/article/view/6642)

## Table of Contents
- [Accessing the Dataset](#accessing-the-dataset)
- [Abstract](#abstract)
- [Dataset Summary](#dataset-summary)
- [Tagin Language](#tagin-language)
- [Contributions](#contributions)
- [Dataset](#dataset)
- [Dataset Structure](#dataset-structure)
- [Part-of-Speech Tagset](#part-of-speech-tagset)
- [Models and Experimental Setup](#models-and-experimental-setup)
- [Results](#results)
- [Conclusion](#conclusion)
- [Authors](#authors)
- [License](#license)
- [Citation](#citation)

## Accessing the Dataset

The corpus is publicly available on the Hugging Face Hub:
**[https://huggingface.co/datasets/repleeka/Tagin-POS-Corpus-v1.0](https://huggingface.co/datasets/repleeka/Tagin-POS-Corpus-v1.0)**

You can load the dataset directly in Python using the Hugging Face `datasets` library:

```bash
pip install datasets
```

```python
from datasets import load_dataset

dataset = load_dataset("repleeka/Tagin-POS-Corpus-v1.0")

print(dataset)
print(dataset["train"][0])
```

## Abstract
This study presents the design of a machine-learning-based part-of-speech (POS) tagger and a silver-standard POS tagged corpus for the low-resource Tagin language. Due to the lack of digitally available text data, applying modern NLP techniques to the Tagin language remains extremely challenging. To address this, we constructed a POS tagged corpus comprising 5,000 sentences collected from legacy Tagin dictionaries and grammar books, with 23,136 tokens and 4,139 unique word forms. We employed 21 UD v2–compatible POS tags with Tagin-specific morphosyntactic adaptations. For benchmarking, we evaluated four classical sequence-labeling models (HMM, CRF, Average Perceptron, and Maximum Entropy). Across all evaluation metrics, the CRF model achieved the best performance, with a word-level accuracy of 81.80% and OOV accuracy of 56.76%. The worst-performing model was the HMM, with a word accuracy of 77.18% and a notably low OOV accuracy of 39.62%.

**Keywords:** Part-of-speech tagging, low-resource language, Tagin language, conditional random fields, sequence labeling.

## Dataset Summary
- **Hugging Face Repository:** [`repleeka/Tagin-POS-Corpus-v1.0`](https://huggingface.co/datasets/repleeka/Tagin-POS-Corpus-v1.0)
- **Language:** Tagin (`tgj`)
- **Task:** Token Classification / Part-of-Speech Tagging
- **Total Sentences:** 5,000
- **Total Tokens:** 23,136
- **Vocabulary Size:** 4,139
- **POS Tags:** 21 (hybrid UD v2 + Tagin-specific)
- **Splits:** 80:20 train/test (4,000 / 1,000 sentences), random state 42
- **License:** CC BY-NC-ND 3.0

## Tagin Language
The Tagin language is spoken by the Tagin tribe of Arunachal Pradesh, India and South-Tibet, China. It belongs to the Tani branch of the Sino-Tibetan language family, which includes languages like Adi, Nyishi, Apatani, Mising, and Galo spoken in the same region. According to the 2011 Census of India, the total population of Tagin tribal people is 62,931. It is listed as Endangered/Unsafe in the UNESCO Atlas of the World's Languages in Danger.

Tagin uses a modified Roman script, which covers the pronunciation of Tagin vocabularies. It mostly follows subject-object-verb (SOV) word order and distinguishes between long and short sounds, so certain words convey different meanings when spoken with long or short tones. Central vowel sounds such as [ɨ] and [ə] are also found in spoken Tagin.

### Complexities in POS Tagging for Tagin
- **Lexico-grammatical ambiguity:** some Tagin words have different grammatical tags according to their position in a sentence. In *"Svlu nyido homa; svlu donyi nyido"* (It's not raining today; it's sunny), *nyido* acts as a Noun ("rain") and a Verb ("to ascend"). Written Tagin also lacks standard spelling: the common verb *kabmabv* ("don't cry") can be written *kabmab*, *kapmab*, *kabyo* or *kapyo*, which increases vocabulary size and creates sparsity.
- **Ambiguity in accent:** a long vowel sound is used interchangeably with a nasal vowel sound, as in *bvvnam* vs. *bvngnam* (to carry), *mwwnam* vs. *mwngnam* (to introspect), and *chimma* vs. *chingma* (don't know). Terminal suffixes also vary, as in *mwnww* vs. *mwnwng* (desire of doing something). These variants trigger high Out-of-Vocabulary (OOV) rates.
- **Resource scarcity:** there are no language tools and no digital training dataset for POS tagging in Tagin.

## Contributions
- The **first** meticulously curated, fully manually annotated silver-standard POS tagged corpus for the Tagin language, released on Hugging Face at [`repleeka/Tagin-POS-Corpus-v1.0`](https://huggingface.co/datasets/repleeka/Tagin-POS-Corpus-v1.0).
- A performance benchmark for Tagin NLP, evaluating the corpus with traditional machine learning architectures.
- Released resources that provide the computational infrastructure for downstream applications and support the preservation of Tagin in the digital age.

## Dataset

### Tagin Text Corpus
Texts were initially mined from old Tagin grammars, Tagin-English dictionaries and Tagin primary-level textbooks using optical character recognition (OCR), by manually scanning each page and converting it to PDF. This produced an initial digital Tagin lexicon with grammatical categories, which was used to manually translate sentences from the [Tatoeba](https://tatoeba.org/en/downloads) English monolingual corpus into Tagin, generating 15K Tagin-English parallel sentences.

The sentences were cleaned and pre-processed in several stages: unwanted OCR characters were removed, and sentence delimiters such as `.` and `?` were used so each sentence could be identified. Because different sources spell the same word differently, a manual spelling normalisation step was applied, following the Modified Roman Script (MRS) released by the apex community organisation of the Tagin community.

### Tagin Digital Lexicon
An old Tagin-English dictionary was scanned with OCR to build a digital lexicon of about 3,000 terms. The lexicon is in CSV format, with each word annotated with basic morphological categories such as case, aspect, tense and person. It served as the lookup table for building the silver-standard POS-tagged corpus through lexicon-based annotation of words.

### Corpus Statistics
| Statistic | Value |
| :--- | :--- |
| Total Sentences | 5,000 |
| Total Tokens | 23,136 |
| Vocabulary Size | 4,139 |
| Type-Token Ratio | 0.1789 |
| Average Sentence Length | 4.63 words |

## Dataset Structure

The dataset hosted at [`repleeka/Tagin-POS-Corpus-v1.0`](https://huggingface.co/datasets/repleeka/Tagin-POS-Corpus-v1.0) is organized into two splits:

| Split | Sentences |
| :--- | :--- |
| `train` | 4,000 |
| `test` | 1,000 |

### Data Fields
- `Sentence` (`string`): The raw Tagin sentence.
- `Tagged_Sentence` (`string`): The corresponding POS-tagged token sequence.

### Data Examples
| Sentence | Tagged_Sentence |
| :--- | :--- |
| tapa so aaba. | tapa/PROPN so/ADV aaba/VERB |
| aaba bv aato. | aaba/VERB bv/AUX aato/VERB |
| no aacho to. | no/PRON aacho/VERB to/PART |
| aadak lo jilaka. | aadak/VERB lo/ADP jilaka/VERB |
| aadak lvri bv aayo ke. | aadak/VERB lvri/NOUN bv/AUX aayo/VERB ke/PART |
| no so aadv aadv mabv ka. | no/PRON so/ADV aadv/VERB aadv/VERB mabv/AUX ka/PART |
| no aakor laku ka. | no/PRON aakor/VERB laku/AUX ka/PART |

### Annotation Format
Each token is followed by a forward slash (`/`) and its POS tag. This format is used throughout all **5,000 sentences** of the GinLish MT project research.

## Part-of-Speech Tagset
The corpus uses **21 distinct POS tags**, designed to be largely compatible with the Universal Dependencies (UD) v2 framework while incorporating targeted adaptations for the morphosyntactic characteristics of Tagin.

- **Core UD categories**, directly adopted: `NOUN`, `VERB`, `ADJ`, `ADV`, `PRON`, `PROPN`, `DET`, `NUM`, `ADP`, `AUX`, `CCONJ`, `INTJ`, and `COP`.
- **Language-specific distinctions** not explicitly encoded in UD v2: `CLF` for classifiers, `NEG` for explicit negation markers, and `PART-INT` for interrogative particles. The `PHRASE` tag annotates multiword expressions that function as a single word unit.
- **Legacy tags:** `PREP` and `CONJ` are retained to maintain continuity with legacy annotations and annotator intuition, despite their partial functional overlap with `ADP` and `CCONJ` in UD v2.

**Comprehensive list of hybrid POS tags for Tagin (Table 2 of the paper):**

| Tag | Category |
| :--- | :--- |
| `PREP` | Preposition |
| `PART` | Particle |
| `NUM` | Numeral |
| `ADJ` | Adjective |
| `NOUN` | Noun |
| `CCONJ` | Coordinating Conjunction |
| `PUNCT` | Punctuation |
| `INTJ` | Interjection |
| `PROPN` | Proper Noun |
| `PART-INT` | Particle / Interjection |
| `PRON` | Pronoun |
| `PHRASE` | Phrase-level construct |
| `CONJ` | Conjunction (general) |
| `DET` | Determiner |
| `CLF` | Classifier |
| `COP` | Copula Verb |
| `ADP` | Adposition (preposition/postposition) |
| `VERB` | Verb |
| `ADV` | Adverb |
| `NEG` | Negation |
| `AUX` | Auxiliary Verb |

**Top 10 most frequent POS tags in the corpus (Table 4 of the paper):**

| Tag | Frequency | Percentage (%) |
| :--- | :--- | :--- |
| `VERB` | 3,635 | 15.71 |
| `NOUN` | 3,589 | 15.51 |
| `PRON` | 3,271 | 14.14 |
| `ADV` | 1,876 | 8.11 |
| `AUX` | 1,833 | 7.92 |
| `ADJ` | 1,615 | 6.98 |
| `PART` | 1,489 | 6.44 |
| `DET` | 1,426 | 6.16 |
| `COP` | 1,241 | 5.36 |
| `PROPN` | 1,044 | 4.51 |

## Models and Experimental Setup
Four classical sequence-labeling models were compared. They use high-dimensional sparse feature vectors, which avoids the cold-start problem of training embeddings on limited data. The 5K POS tagged sentences were split into training and testing sets in the ratio 80:20 with a random state of 42.

- **Hidden Markov Model (HMM):** a second-order HMM with the Viterbi algorithm. Lidstone smoothing (additive smoothing) with γ = 0.1 addresses the zero-frequency problem for OOV words and unseen tag transitions.
- **Structured Averaged Perceptron (AvgPercep):** a discriminative linear classifier with features for morphological cues (suffixes of the last 3 characters and the first-character prefix), contextual windows (w<sub>i−1</sub>, w<sub>i</sub>, w<sub>i+1</sub>), and syntactic context (the predicted labels of the two previous tokens, t<sub>i−1</sub>, t<sub>i−2</sub>). It was trained for 15 iterations with an averaging weight update rule and a uniform random seed in each epoch.
- **Maximum Entropy (MaxEnt):** multinomial logistic regression with a log-linear framework, using a `DictVectorizer` sparse feature space and L-BFGS optimisation. Its features are character-level prefixes (length 1–3) and suffixes (length 2–3), e.g. *-nam*, *-vng*; orthographic identifiers (title case, digits, capitalisation); lowercase forms of the current, preceding and succeeding tokens; and BOS/EOS markers.
- **Conditional Random Fields (CRF):** trained with L-BFGS and Elastic Net regularisation (C1 = 0.1 for L1, C2 = 0.1 for L2). Its features are character-level suffixes (length 2 and 3) and prefixes (length 3); orthographic identifiers; a ±1 word context window with lowercase form and capitalisation status; and BOS/EOS markers.

## Results
The models were evaluated on word-level accuracy, sentence-level accuracy, OOV accuracy, Macro-F1 score and cross-validation stability.

**Performance of different POS tagging models (Table 5 of the paper):**

| Model Architecture | Word Acc (%) | Sent. Acc (%) | OOV Acc (%) | Macro-F1 (%) |
| :--- | :--- | :--- | :--- | :--- |
| **CRF** | **81.80** | **53.00** | **56.76** | **71.41** |
| Averaged Perceptron | 80.77 | 48.15 | 51.24 | 68.20 |
| MaxEnt | 80.05 | 47.90 | 50.11 | 67.54 |
| HMM | 77.18 | 40.80 | 39.62 | 63.12 |

- **CRF** achieved the highest word-level accuracy, sentence-level accuracy, OOV accuracy and Macro-F1 score.
- **AvgPercep and MaxEnt** showed comparable local accuracy, but lacked the global normalisation of CRF, which shows in their sentence-level accuracy and Macro-F1.
- **HMM** performed worst, which highlights the limitation of generative sequence models in low-resource settings, where OOV tokens are frequent and emission probabilities cannot be reliably estimated.
- **Cross-validation (k = 10):** all models showed a very low standard deviation (approximately 0.007–0.008).

### Metric-Specific Evaluations
- **OOV accuracy:** CRF reached 56.76%, well ahead of the Perceptron (51.24%) and HMM (39.62%), mainly due to its character-level prefix and suffix features.
- **Macro-F1 vs. word accuracy:** the lower Macro-F1 scores reflect a skewed class distribution. Dominant categories (`NOUN`, `VERB`) are handled well, while infrequent categories (`ADP`, `PART`) have higher error rates.
- **Error propagation:** HMM's low sentence accuracy (40.8%) shows how a single incorrect state transition renders the entire sentence incorrect.

### Qualitative Error Analysis
- **Nominal-modifier ambiguity:** in structures like *subu ador gu jito*, models frequently misclassified the `DET` (*ador*) as a `NOUN`, favouring a `NOUN-NOUN` compound over a `NOUN-DET` sequence.
- **Adverb vs. verb/adjective ambiguity:** for *nyorsi*, the silver standard is `VERB`, CRF predicted `ADJ`, and MaxEnt/Perceptron predicted `ADV`.
- **Complex predicate structures:** for *amin pusuma pasik ro* (`NOUN ADP VERB AUX`), MaxEnt predicted `NOUN VERB VERB AUX`, while CRF and AvgPercep predicted `ADJ` or `PRON` for the verbal elements.

### Comparison with CRF Taggers for Other Low-Resource Languages
Table 1 of the paper:

| Language | CRF Accuracy | Feature Engineering Detail |
| :--- | :--- | :--- |
| Bodo | 75.2% | Linear-chain structure |
| Odia | ~82% | Universal POS tag set |
| Uzbek | 88.0% | L-BFGS optimized, suffix-aware |
| Yoruba | 84.66% | Linear-chain, CRF++ tool |
| Khasi | 92.12% | Lexical and orthographic features |

### Future Improvements
Enhanced feature engineering could improve OOV handling, and the persistent noun/determiner confusion suggests re-examining annotation consistency in the corpus. Given the upward trend of the learning curve, modest data augmentation could push CRF performance beyond 85% word-level accuracy.

## Conclusion
Despite the constraints of an informal written script and the lack of a uniform lexicon, this work created the **first** silver-standard Tagin POS corpus of 5K sentences and 21 unique POS tags, a hybrid of the UD v2 scheme and Tagin-specific tags. CRFs outperformed the other classical models in all experimental settings. This baseline and the corpus—publicly hosted on Hugging Face at [`repleeka/Tagin-POS-Corpus-v1.0`](https://huggingface.co/datasets/repleeka/Tagin-POS-Corpus-v1.0)—can guide future Tagin POS research, including deep neural network models, and support the digital preservation and computational inclusion of the Tagin language.

## Authors
- **Tungon Dugi** (corresponding author, <tungondugi@gmail.com>) and **Koj Sambyo**, Department of Computer Science and Engineering, National Institute of Technology Arunachal Pradesh, India.
- **Project Name:** GinLish MT.

## License
This dataset is released under the [Creative Commons Attribution-NonCommercial-NoDerivatives 3.0 Unported (CC BY-NC-ND 3.0)](https://creativecommons.org/licenses/by-nc-nd/3.0/) license.

## Citation
If you use this dataset in your research, please cite:
```bibtex
@article{DBLP:journals/cys/DugiS26,
  author       = {Tungon Dugi and
                  Koj Sambyo},
  title        = {A Silver-Standard {POS} Corpus and Baseline Models for Tagin, a Low-Resource
                  Language},
  journal      = {Computaci{\'{o}}n y Sistemas (CyS)},
  volume       = {30},
  number       = {3},
  pages        = {2009--2026},
  year         = {2026},
  doi          = {10.13053/CyS-30-3-6642},
  url          = {https://www.cys.cic.ipn.mx/index.php/CyS/article/view/6642}
}
```
