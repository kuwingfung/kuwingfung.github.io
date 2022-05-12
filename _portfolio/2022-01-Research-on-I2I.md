---
title: "Deep Learning Image-to-Image Translation"
excerpt: "My final year project extensively studied the use of GAN-based methods in Image-to-image translation. <br/><img src='/images/i2i-application-demo.png' width='500'><br/><img src='/images/highlight-sketch2anime.png' width='500'>"
collection: portfolio
description: ""
---

Image-to-image translation is a computer vision problem where the goal is to convert an image from one domain
to another domain, for example, from a grayscale image to a colored image. We present three applications
to show the usefulness of image-to-image translation. Total of six deep learning-based approaches based on
convolutional neural network (CNN) and generative adversarial network (GAN) are used to solve the above
problems.

<br/>
<img src='/images/i2i-application-demo.png'>
<br/>

The first application could apply the style of Chinese paintings to a scenery image, and we carried out the
experiment using two different methods. Pre-trained arbitrary image stylization model is used as the first
method, and generative adversarial network with cycle-consistency loss is used as the second method. Our
quantitative comparison shown generative adversarial network with cycle-consistency loss produces better results
than arbitrary image stylization in Chinese painting style transfer application.

<br/>
<img src='/images/highlight-scene2cpaint.png'>
<br/>

The second application could paint the color on black and white sketches, and we carried out the experiment
using two different methods. A conditional generative adversarial network with L1 loss is used as the first
method, and then we proposed a novel approach that uses conditional generative adversarial network with
perceptual loss and spectral normalization as the second method. Our statistical results found our approach
produces better results than conditional generative adversarial network with L1 loss in anime sketch colorization
application.

<br/>
<img src='/images/highlight-sketch2anime.png'>
<br/>

The third application could convert a cat into a tiger inside an image, and we carried out the experiment using
two different methods. Generative adversarial network with cycle-consistency loss is used as the first method,
and generative adversarial network with contrastive loss is used as the second method. Our statistical results
reported that generative adversarial network with cycle-consistency loss produces better results than generative
adversarial network with contrastive loss in animal configuration application.

<br/>
<img src='/images/highlight-cat2tiger.png'>

* [Report](https://drive.google.com/file/d/1kJ9u_YhaC-dA7MnkIa_InELtwd0zfozd/view?usp=sharing)
* [Slides](https://drive.google.com/file/d/1e8k4OYLUKTbeNTlvY8CDumzvH7nOGULP/view?usp=sharing)