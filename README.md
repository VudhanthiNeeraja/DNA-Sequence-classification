# DNA Sequencing using Machine learning

## Overview
This project uses a **Multinomial Naive Bayes classifier** to classify DNA sequences into gene families. It processes sequences from humans, chimpanzees, and dogs to analyze cross-species genomic patterns. The pipeline includes k-mer tokenization, Bag-of-Words feature extraction, and model evaluation.

## Dataset
### Input Format
DNA sequences are provided in tab-separated files (`human_data.txt`, `chimp_data.txt`, `dog_data.txt`) with two columns:
- `class`: Gene family label (integer)
- `sequence`: Raw DNA sequence (e.g., `AAGGTGAGTGAAATCTCAAC...`)

### Example structure:
class    sequence
0        ATGGTGCTAG...
1        TGCGATACGT...


## Model Architecture
Pipeline
Preprocessing:

Convert sequences into 6-mers (overlapping substrings of length 6).

Example: ATGGTG → ['atggtg', 'tggtgc', ...].

Feature Extraction:

Use CountVectorizer with 4-grams to create a Bag-of-Words representation.

Generates 4,380 features for human sequences.

Classifier:

Multinomial Naive Bayes with Laplace smoothing (alpha=0.1).

Evaluation:

Tested on held-out human data (20% split), chimpanzee, and dog sequences.

Metrics: Accuracy, Precision, Recall, F1-Score (weighted averages).



## Key insights:

High accuracy on human and chimpanzee sequences due to evolutionary similarity.

Lower performance on dog sequences highlights species divergence.
