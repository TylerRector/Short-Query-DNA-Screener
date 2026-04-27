# Short-Query-DNA-Screener

AIxBio Hackathon Project: A gradient-boosting classifier for fast, short-read DNA threat detection. Uses a hybrid DNA/protein k-mer approach and reverse-screening post-filters to accurately identify hazardous sequences while generalizing to novel organisms.

## Core Features
* **Hybrid Model:** Evaluates both DNA and translated protein k-mer frequencies using XGBoost.
* **Short-Read Optimized:** Uses multi-length window augmentation to maintain accuracy on fragmented reads.
* **Low False-Positive Rate:** Implements a reverse-screening post-filter and GC-matching/low-complexity masking to reduce noise.
* **Portable Export:** Compresses the trained mathematical model and pure Python inference logic into a standalone `.tar.gz` bundle.

## Pipeline Overview
The Jupyter Notebook executes the following pipeline:
1. **Setup & Database Initialization:** Configure SQLite databases for sequence management.
2. **Training Data:** Download and load disk-based training data.
3. **Training & Evaluation:** Train the XGBoost model with A/B/AB intervention comparison and multi-length window augmentation.
4. **Post-Processing:** Apply GC-matching and low-complexity masking.
5. **Export:** Generate the portable `.tar.gz` inference bundle.

## Usage (Inference)
The final output is a standalone `.tar.gz` bundle. Extract this bundle on your target machine to run pure Python inference without needing the training environment or heavy dependencies.
