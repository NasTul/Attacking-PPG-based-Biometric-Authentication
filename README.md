# [Video-is-All-You-Need-Attacking-PPG-based-Biometric-Authentication [AISec]](https://dl.acm.org/doi/10.1145/3560830.3563722) 

Published: AISec 2022

***

## Table of Contents
* [Methodology](#methodology)
* [Data Prepare](#data-prepare)
* [Restore Model](#restoreModel)
* [Experiment](#experiment)
* [Citation](#citation)


----
## Methodology
We aim to design a spoofing attack on PPG-based biometric authentication only by video clips. Fig.3 presents the workflow of our attack. Initially, we obtain the region of interest in a video clip through face detection. To acquire a suitable rPPG signal, we adopt CHROM. Finally, we elaborate on how to restore an rPPG signal to the PPG signal. 

<div align=center>
<img width="853" alt="methodology" src="https://raw.githubusercontent.com/NasTul/Attacking-PPG-based-Biometric-Authentication/main/Figure/workflow.png">
</div>


## Data Prepare
We conduct a series of experiments on the [UBFC-PHYS](https://ieee-dataport.org/open-access/ubfc-phys-2). The detailed processing of the data can be found in code **ExtractPPG.ipynb**.


## Restore Model
We propose a signal restoration model SigR. It aims to learn the distribution of differences between signals from a small amount of data. It adapts GAN's network structure for signal processing. Specifically, our generator takes the rPPG signal as the input to learn the latent space, approximating the generated signal close to the victim's PPG signal that spoofs the discriminator. While SigR is proposed for signal restoration using GAN, the component of signal restoration in the new spoofing attack can be implemented by other machine learning/deep learning models. As a comparison, we use the Gaussian process (GP) and Gaussian mixture model (GMM) as baseline models. More details can be found in code **RestoreModel.ipynb**.


## Experiment
In our attacking process, the more similar the restored signal is to the PPG signal, the higher the signal quality is. As shown in Fig.7, we compare the PPG, rPPG and SigR signals. The signal after SigR recovery is more similar to the original signal. 

<div align=center>
<img width="353" alt="wave" src="https://raw.githubusercontent.com/NasTul/Attacking-PPG-based-Biometric-Authentication/main/Figure/wave.png">
</div>

Herein, we compare the correlation between the signals. 
As shown in Fig.8, blue squares show the Pearson correlation coefficient between the PPG signal restored by SigR and the reference PPG signal. 
Red dots show the Pearson correlation coefficient between the original rPPG signal harvested from the video and the reference PPG signal. We find that the coefficient between the rPPG signal harvested from the video and the reference PPG signal is drastically unstable. Conversely, the coefficient of the PPG signal restored by SigR and the reference PPG signal is steady between 0.96 and 1.00. Most of the signals restored by SigR have higher coefficients than directly harvested rPPG signals, indicating that the PPG signals restored by SigR are positively correlated with the reference PPG signal. 

<div align=center>
<img width="353" alt="wave" src="https://raw.githubusercontent.com/NasTul/Attacking-PPG-based-Biometric-Authentication/main/Figure/pearson.png">
</div>

More details can be found in code **Experiment.ipynb**.

## Citation

If you use this repository please cite the paper as follows:

```
@inproceedings{10.1145/3560830.3563722,
  author = {Li, Lin and Chen, Chao and Pan, Lei and Zhang, Jun and Xiang, Yang},
  title = {Video is All You Need: Attacking PPG-Based Biometric Authentication},
  year = {2022},
  isbn = {9781450398800},
  publisher = {Association for Computing Machinery},
  address = {New York, NY, USA},
  url = {https://doi.org/10.1145/3560830.3563722},
  doi = {10.1145/3560830.3563722},
  booktitle = {Proceedings of the 15th ACM Workshop on Artificial Intelligence and Security},
  pages = {57–66},
  numpages = {10},
  location = {Los Angeles, CA, USA},
  series = {AISec'22}
}
```



