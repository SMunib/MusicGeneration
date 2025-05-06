🎵 Music Generation using GANs and Transformers
This project explores deep learning techniques for symbolic music generation using the MAESTRO dataset. Specifically, it implements Generative Adversarial Networks (GANs) and Transformers to generate expressive and coherent piano music sequences in MIDI format.

🚀 Project Overview
Dataset: MAESTRO v3.0.0

GAN Architecture: Deep convolutional Generator and Discriminator

Transformer Model: (coming soon)

Framework: PyTorch

Goal: Generate high-quality symbolic music resembling real human piano performances

🧠 GAN Model Details
Generator
Latent input: torch.randn(batch_size, 256)

Linear projection + ConvTranspose1D layers

Output: (batch_size, 131, 480) — MIDI features over time

Activation: Sigmoid to produce values in range [0,1]

Discriminator
Conv1D layers with Spectral Normalization

LeakyReLU activations and Dropout for regularization

Mean-pooling across time dimension

Output: Binary classification (real vs. fake)

Training Highlights
Optimizer: Adam with (β1=0.5, β2=0.999)

Label Smoothing: Real = 0.9, Fake = 0.1

Loss Function: Binary Cross-Entropy

Balanced Generator/Discriminator training per epoch

Spectral norm and dropout improved stability and realism

🤖 Transformer Model (Coming Soon)
The Transformer-based approach is currently under development and will be added in a future update. It aims to address long-term dependencies and improve musical structure.

📊 Results
GANs successfully generated plausible rhythmic and melodic patterns after training. However, long-term structure remains a challenge — expected to be better handled by the Transformer model.

Generated samples and logs are available in the samples/ directory.
