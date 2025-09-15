# **Semantor: Punctuation-Aware Neural Machine Translation**

Semantor is an experimental **English-to-Hindi translation model** that introduces a novel way of enriching word embeddings.  
Built with **PyTorch** on a **Transformer backbone**, its core innovation is a **punctuation-aware encoder** that fuses a word’s contextual meaning with semantic cues derived from punctuation.  

This allows the model to better capture **intent, tone, and nuance**, producing more human-like translations.

---

## **The Core Intuition**
Punctuation is not just grammar—it is a direct signal of **intent** and **tone**, similar to voice inflection in human speech.  
Standard machine translation models often ignore this.  

Semantor addresses this by concatenating **three signals** into each embedding:
1. **Contextual Meaning** – the word’s standard representation.  
2. **Semantic Value** – a vector encoding attached punctuation (`?`, `!`, `.`, etc.).  
3. **Positional Information** – the word’s position in the sequence.  

This fusion lets the model differentiate between:
- A **question** (`What is your name?`)  
- A **statement** (`Your name is...`)  
- An **exclamation** (`What a name!`)  

---

## **Model Architecture**
- **Encoder**: Custom embedding layer combining semantic, positional, and contextual features with **multi-head self-attention**.  
- **Decoder**: Transformer-inspired with self-attention, cross-attention, and feed-forward layers.  
- **Training Pipeline**: End-to-end training with vocabulary creation, data preparation, evaluation, and greedy decoding.  

---

## **Features**
- **Punctuation-Aware Embeddings**: Directly integrates punctuation semantics into embeddings.  
- **Transformer Backbone**: Encoder–decoder model with attention mechanisms.  
- **End-to-End Pipeline**: Vocabulary building, training, evaluation, and inference in one script.  
- **BLEU Score Evaluation**: Uses `sacrebleu` for both sentence-level and corpus-level metrics.  

---

## **Getting Started**

### Prerequisites
- Python 3.8+  
- [PyTorch](https://pytorch.org/)  
- NumPy  
- SacreBLEU  

### Installation
Clone the repository:
```bash
git clone https://github.com/Devrcb18/Semantor.git
cd Semantor
