
# 🎵 Music Generation using GANs and Transformers

This project explores two deep learning architectures—Generative Adversarial Networks (GANs) and Transformers—for the task of symbolic piano music generation. By training on the MAESTRO dataset, the goal is to generate expressive and coherent musical sequences and compare the performance of both approaches.

## 🚀 Objectives

- Generate stylistically rich and coherent piano music from scratch.
- Compare the generative capabilities of GANs vs. Transformers.
- Analyze model performance based on subjective listening and structural properties.

## 📁 Dataset

We use the [MAESTRO v3.0.0](https://magenta.tensorflow.org/datasets/maestro) dataset, which contains over 200 hours of aligned MIDI and audio recordings of professional piano performances. For this project, we use only the MIDI data, converted into:
- Piano roll format (for GANs)
- REMI token sequences (for Transformers)

## 🧠 Models

### 1. Generative Adversarial Network (GAN)
- **Generator**: Transposes a 256-dim latent vector into a piano roll via 1D transposed convolutions.
- **Discriminator**: Uses Conv1d layers with spectral normalization to classify real vs. fake sequences.
- **Training Enhancements**:
  - Spectral normalization
  - Label smoothing
  - Dropout for regularization

### 2. Music Transformer
- **Architecture**: Encoder-only Transformer with 6 layers and 8 attention heads.
- **Input**: REMI-tokenized sequences
- **Output**: Predicted next-token logits for MIDI reconstruction
- **Training Techniques**:
  - Learnable positional embeddings
  - Top-k sampling for diversity
  - Dropout and layer normalization

## 📊 Results

- **GANs** produced basic rhythmic patterns but struggled with long-term structure.
- **Transformers** generated musically coherent sequences with improved temporal consistency and motif development.
- Listening tests favored Transformer outputs due to better musicality and structure.

