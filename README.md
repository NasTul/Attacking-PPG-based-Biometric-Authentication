# [Video-is-All-You-Need-Attacking-PPG-based-Biometric-Authentication [AISec]](https://arxiv.org/abs/2203.00928) 
Paper: 

Published: AISec 2022

***

## Table of Contents
* [Methodology](#methodology)
* [Data Prepare](#data-prepare)
* [Data Preprocess](#data-preprocess-feature-extraction)
* [User-level Audio Auditor Model](#user-level-audio-auditor-model)
* [Result Analysis](#result-analysis)


----
## Methodology
We aim to design a spoofing attack on PPG-based biometric authentication only by video clips. Fig.1 presents the workflow of our attack. Initially, we obtain the region of interest in a video clip through face detection. To acquire a suitable rPPG signal, we adopt CHROM. Finally, we elaborate on how to restore an rPPG signal to the PPG signal. We propose a signal restoration model SigR. It aims to learn the distribution of differences between signals from a small amount of data. It adapts GAN's network structure for signal processing. Specifically, our generator $G$ takes the rPPG signal as the input to learn the latent space, approximating the generated signal close to the victim's PPG signal that spoofs the discriminator. 










