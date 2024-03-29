---
title: "Intelligent Painter: Picture Composition With Resampling Diffusion Model"
excerpt: "We present an intelligent painter that generate a person's imaginary scene in one go, given explicit hints. We propose a resampling strategy for Denoising Diffusion Probabilistic Model (DDPM) to intelligently compose harmonized scenery images by injecting explicit landmark inputs at specific locations. Preprint available on Arxiv. <br/><img src='https://user-images.githubusercontent.com/34955859/200509579-4cf1b90f-ce88-459a-b3a9-1341ff0ec233.png' width='500'> <br/><img src='https://user-images.githubusercontent.com/34955859/200741607-3ccf4d48-7e97-4c9c-9d3c-2821c7a360a4.png' width='500'>"
collection: portfolio
description: "Have you ever thought that you can be an intelligent painter? This means that you can paint a picture with a few expected objects in mind, or with a desirable scene. We present an intelligent painter that generate a person's imaginary scene in one go, given explicit hints. We propose a resampling strategy for Denoising Diffusion Probabilistic Model (DDPM) to intelligently compose harmonized scenery images by injecting explicit landmark inputs at specific locations. By exploiting the diffusion property, we resample efficiently to produce realistic images. Experimental results show that our resampling method favors the semantic meaning of the generated output efficiently and generate less blurry output. Preprint available on Arxiv."
---

# Intelligent Painter with Resampling Diffusion Models
[![arXiv](https://img.shields.io/badge/arXiv-2210.17106-b31b1b.svg)](https://arxiv.org/abs/2210.17106)
[Code](https://github.com/vinesmsuic/ipainter-diffusion)

![](https://user-images.githubusercontent.com/34955859/200509260-4c56d4f8-0cd6-4e7d-b32d-efe398629cbf.png)

> **Intelligent Painter: Picture Composition With Resampling Diffusion Model**<br>
> [Wing-Fung Ku](https://kuwingfung.github.io/), [Wan-Chi Siu](https://scholar.google.com/citations?user=ouQRncoAAAAJ), [Xi Cheng](https://scholar.google.com/citations?user=kpcwnZkAAAAJ), H. Anthony Chan<br>
> https://arxiv.org/abs/2210.17106
> 
> **Abstract:** *Have you ever thought that you can be an intelligent painter? This means that you can paint a picture with a few expected objects in mind, or with a desirable scene. This is different from normal inpainting approaches for which the location of specific objects cannot be determined. In this paper, we present an intelligent painter that generate a person's imaginary scene in one go, given explicit hints. We propose a resampling strategy for Denoising Diffusion Probabilistic Model (DDPM) to intelligently compose harmonized scenery images by injecting explicit landmark inputs at specific locations. By exploiting the diffusion property, we resample efficiently to produce realistic images. Experimental results show that our resampling method favors the semantic meaning of the generated output efficiently and generate less blurry output. Quantitative analysis of image quality assessment shows that our method produces higher perceptual quality images compared with the state-of-the-art methods.*


## Paint Clearly with Resampling Diffusion models

![](https://user-images.githubusercontent.com/34955859/200509579-4cf1b90f-ce88-459a-b3a9-1341ff0ec233.png)

We proposed a simple yet efficient resampling method to produce clear result in uncondtional image. Our method is 50% faster than RePaint while achieving less blurry results.

> One serious downside is that resampling increases the inference time significantly, as it increases the operations. Moreover, the resampling approach proposed by RePaint often produces image with unclear details. To mitigate this issue, we stop the resampling at timestep t = 100.
>
> We perform Fourier analysis on the forward process and found that the high-frequency components of the image such as fine details are corrupted at lower timesteps, while at larger timesteps the low-frequency components of the image such as coarse structures are corrupted. Therefore, we can assume that the learned reverse process first generates the coarse structure at higher timesteps and then makes fine details at lower timesteps. 
>
> ![](https://user-images.githubusercontent.com/34955859/200742081-4148f124-6a43-4dde-970f-d2391f5d8bbf.png)
>
> The resampling at lower timesteps could potentially blur the details because the preserved low-level information in the forward steps has intervened the denoising process at lower timestep. Since the coarse structure harmonized at bigger timesteps has provided enough information to generate the fine details, we can exploit this property to stop resampling at a smaller timestep, therefore improving the image perceptual quality and the inference time.

![](https://user-images.githubusercontent.com/34955859/200742117-fd56bc8d-4b1d-4b2c-9321-a09dbb73f16b.png)

* While No Resampling inference fastest and produce least blurry image, it failed to harmonize the picture
* Full Resampling approach (RePaint) in unconditional state often produce blurry artifacts, and it is due to the resampling at lower timesteps.
* Our approach of Resampling stops at t=100 solves both problem, providing fast inference and produce less blurry image.



## State-of-the-Art Comparison

![](https://user-images.githubusercontent.com/34955859/200741607-3ccf4d48-7e97-4c9c-9d3c-2821c7a360a4.png)

|  Method  | NIQE Score (⬇️) |
| :------: | :------------: |
| AOT-GAN  |     5.9629     |
| CoModGAN |     5.3083     |
| Big-LaMa |     4.9511     |
|   MAT    |     5.6552     |
| RePaint  |     5.5635     |
|   Ours   |   **4.8653**   |



## Citation

If you found IntelligentPainter useful in your research, please consider starring us on GitHub and citing us in your research.
```bibtex
@misc{ku2022painter,
Author = {Wing-Fung Ku and Wan-Chi Siu and Xi Cheng and H. Anthony Chan},
Title = {Intelligent Painter: Picture Composition With Resampling Diffusion Model},
Year = {2022},
Eprint = {arXiv:2210.17106},
```

