# [Video-is-All-You-Need-Attacking-PPG-based-Biometric-Authentication [AISec]](https://arxiv.org/abs/2203.00928) 
Paper: 

Published: AISec 2022

***

## Table of Contents
* [Methodology](#methodology)
* [Data Prepare](#data-prepare)
* [Restore Model](#restoreModel)


----
## Methodology
We aim to design a spoofing attack on PPG-based biometric authentication only by video clips. Fig.3 presents the workflow of our attack. Initially, we obtain the region of interest in a video clip through face detection. To acquire a suitable rPPG signal, we adopt CHROM. Finally, we elaborate on how to restore an rPPG signal to the PPG signal. 


We propose a signal restoration model SigR. It aims to learn the distribution of differences between signals from a small amount of data. It adapts GAN's network structure for signal processing. Specifically, our generator takes the rPPG signal as the input to learn the latent space, approximating the generated signal close to the victim's PPG signal that spoofs the discriminator. 

<img width="853" alt="methodology" src="https://raw.githubusercontent.com/NasTul/Attacking-PPG-based-Biometric-Authentication/main/Figure/workflow.png">


----
## Data Prepare
We conduct a series of experiments on the [UBFC-PHYS](https://ieee-dataport.org/open-access/ubfc-phys-2). The detailed processing of the data can be found in code **ExtractPPG.ipynb**.







