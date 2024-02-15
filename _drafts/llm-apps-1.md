---
layout: single
title: "LLM Apps series: Experimenting with masks"

gallery-hamster:
  - url: assets/images/llm_apps/v1_img2img_masking_0-a.png
    image_path: assets/images/llm_apps/v1_img2img_masking_0-a.png
    alt: "Experiment result"
    title: "1st result"
  - url: assets/images/llm_apps/v1_img2img_masking_0-b.png
    image_path: assets/images/llm_apps/v1_img2img_masking_0-b.png
    alt: "Experiment result"
    title: "2nd result"
  - url: assets/images/llm_apps/v1_img2img_masking_0-c.png
    image_path: assets/images/llm_apps/v1_img2img_masking_0-c.png
    alt: "Experiment result"
    title: "3rd result"
  - url: /assets/images/llm_apps/init_image_1024.png
    image_path: /assets/images/llm_apps/init_image_1024.png
    alt: "Initial image before 'inpainting'"
    title: "Initial Image"
  - url: /assets/images/llm_apps/mask_image_black_1024.png
    image_path: /assets/images/llm_apps/mask_image_black_1024.png
    alt: "Mask area"
    title: "White is mask. Black will be generated"
gallery-bear:
  - url: /assets/images/llm_apps/bear-panel.png
    image_path: /assets/images/llm_apps/bear-panel.png
    alt: "Mask area"
    title: "Transparent pixels get generated"
  - url: /assets/images/llm_apps/v1_img2img_masking_0-d.png
    image_path: /assets/images/llm_apps/v1_img2img_masking_0-d.png
    alt: "Experiment result"
    title: "1st result"
  - url: /assets/images/llm_apps/v1_img2img_masking_0-e.png
    image_path: /assets/images/llm_apps/v1_img2img_masking_0-e.png
    alt: "Experiment result"
    title: "2nd result"
  - url: /assets/images/llm_apps/v1_img2img_masking_0-f.png
    image_path: /assets/images/llm_apps/v1_img2img_masking_0-f.png
    alt: "Experiment result"
    title: "3rd result"
  
---

## Image generators suck at text
You want the dialogue and narration to be a part of your image, rather than a caption off to the top or bottom. It helps you tell who is saying what, and it keeps you in the visual space. But image generators are not capable of writing really any text, let alone let you write the text that gets generated. The easy solution is to just put your text over your image after the fact. This is something that could be added to our comic book generator, and may actually be the solution. One thing you'll run into is not really having space for a speech bubble. You don't want to generate an image and then need to cover up another character to get your foreground character to say something.

What if we could go the other way around? What if we could put the speech bubble where we want it, and ask our image generator fill in the layout around it.

## Inpainting with Stable Diffusion
When generating images, some services will allow you to lock in some parts of the image, and then generate inside of, or around those parts. This is referred to as [Inpainting](https://getimg.ai/guides/inpainting-with-stable-diffusion). For the image generator, this is different than just pasting pixels on top of the generated image. The masked off pixels are fed through the image generator as it tries to make a coherent image. So as it slowly generates an image from noise, it sees your pre-defined parts of the image as part of the rest of the image, and builds inside, or around them.

## Let's try it!

### Round 1

For the first test, I just created a basic image and mask in GIMP. Then I used the example code from the stability.ai documentation, and generated some images.

{% include gallery id="gallery-hamster" %}

So, I learned that it will indeed generate an image around your text. I especially like that although my mask was perfectly round, the speech bubble was not, giving it a more organic feel. A couple other things to note are that the generated bubble is not always perfectly white, and the original background stands out. You may have also noticed a double attribution for one of the bubbles.

### Round 2

I wrote some python code to generate these panel images. I also discovered that the API would take a single image, where visible pixels would be "masked" and transparent pixels would be generated.

I found that if there was not sufficient masked space around the text, the generated image would try to add more text in line with mine.

{% include gallery id="gallery-bear" %}

In one test, I didn't include any background at all, and the generator kind of just re-claimed the text. I started to suspect that maybe the API, in an undocumented feature, was blurring the mask in an attempt to create a more natural result. And we got some more of those double speech bubbles.

## Round 3

