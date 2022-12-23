---
title: "Anime Visual Novel Background Diffusion"
excerpt: "A Stable Diffusion model is fune-tuned to produce visual novel backgrounds with just a few prompts. It is designed to allow creators to quickly and easily generate custom backgrounds for their visual novels. Model available on Hugging Face space. <br/><img src='/images/VNHSD1.png' width='500'><br/><img src='/images/VNHSD-night.png' width='500'>"
collection: portfolio
description: "A prototype project of generating Visual Novel backgrounds for game developers/artists. A Stable Diffusion model is fune-tuned to produce visual novel backgrounds with just a few prompts. It is designed to allow creators to quickly and easily generate custom backgrounds for their visual novels. Model available on Hugging Face space."
---

A prototype project of generating Visual Novel backgrounds for game developers/artists. This model is intended to produce visual novel backgrounds with just a few prompts. Version 3 is based on Anything-V3.

* [Hugging Space Link v3 (Based on Anything-v3)](https://huggingface.co/vinesmsuic/bg-visualnovel-v03)
* [Hugging Space Link v2 (Based on SD1.4)](https://huggingface.co/vinesmsuic/bg-visualnovel-v02)
* [Simple GUI Google Colab Demo here](https://colab.research.google.com/drive/1tR5e_EN9REJh0yr0T-dIyAIwiTMfNSxE?usp=sharing)

![](/images/VNHSD1.png)

## 🧨 Diffusers

This model can be used just like any other Stable Diffusion model. For more information,
please have a look at the [Stable Diffusion](https://huggingface.co/docs/diffusers/api/pipelines/stable_diffusion).

You can also export the model to [ONNX](https://huggingface.co/docs/diffusers/optimization/onnx), [MPS](https://huggingface.co/docs/diffusers/optimization/mps) and/or [FLAX/JAX]().

```python
from diffusers import StableDiffusionPipeline
import torch

model_id = "vinesmsuic/bg-visualnovel-v03"
pipe = StableDiffusionPipeline.from_pretrained(model_id, torch_dtype=torch.float16)
pipe = pipe.to("cuda")

prompt = "a classroom"
image = pipe(prompt, height=512, width=512).images[0]
# ^ alternatively you can use for height=1920, width=1080 if you have enough CUDA memory
# make sure both height and width are divisible by 8
image.save("./classroom.png")

prompt = "a hospital building, two trees"
image = pipe(prompt, height=512, width=512).images[0]

image.save("./hospital.png")

prompt = "a street at night with nobody around"
image = pipe(prompt, height=512, width=512).images[0]

image.save("./nightstreet.png")
```

## Examples

a classroom

![](https://huggingface.co/vinesmsuic/bg-visualnovel-v03/resolve/main/_examples/classroom.png)
![](/images/VNHSD-class.png)

a hospital building, two trees

![](https://huggingface.co/vinesmsuic/bg-visualnovel-v03/resolve/main/_examples/hospital.png)
![](/images/VNHSD-hosp.png)

a street at night with nobody around

![](https://huggingface.co/vinesmsuic/bg-visualnovel-v03/resolve/main/_examples/nightstreet.png)
![](/images/VNHSD-night.png)
