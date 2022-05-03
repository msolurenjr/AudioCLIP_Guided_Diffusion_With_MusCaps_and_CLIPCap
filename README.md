### AudioCLIP_Guided_Diffusion_With_MusCaps_and_CLIPCap [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1QPGeBJEoIKY3nY_iZF3lz4I1vM7QFytJ?usp=sharing)

This project is a modification of the original Clip Guided Diffusion notebook by Katherine Crowson (https://github.com/crowsonkb, https://twitter.com/RiversHaveWings). It uses OpenAI's 256x256 unconditional ImageNet diffusion model (https://github.com/openai/guided-diffusion) together with AudioCLIP (https://github.com/AndreyGuzhov/AudioCLIP) to generate images from text prompts and audio prompts.

The AudioCLIP model used is the pretrained version which keeps the default image head and text head weights from the ResNET version of CLIP (RN50). This allows vanilla CLIP to be loaded into cuda and used at generation time to create image embeddings as opposed to AudioCLIP which requires twice the amount of memory.

It also features the following:

1. A form of automatic text prompt engineering by incorporating two types of audio description mechanisms:

- Description via an audioCLIP-based querying of keywords.
- Description via a manually-trained music captioning model (MusCaps model trained on the Clotho dataset).
  These can be ran on the uploaded audio file to generate descriptions that can be used to enrich the audio prompts during generation time.

2. An image captioning mechanism in the form of ClipCap, a lightweight prefix-based model that binds GPT2 and the vision transformer (ViT) version of clip to produce a caption for each generated image.

Access the notebook by clicking the Google Colab sticker: [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1QPGeBJEoIKY3nY_iZF3lz4I1vM7QFytJ?usp=sharing)


Some example images are shown below:

![alt text](https://github.com/msolurenjr/AudioCLIP_Guided_Diffusion_With_MusCaps_and_CLIPCap/blob/main/Samples/Alarm%20Clock%20Generations.jpg)
