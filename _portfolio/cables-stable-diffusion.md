---
title: "Cables.gl for Stable Diffusion"
excerpt: "A PoC for generating ControlNet depth maps in Cables.gl"
header:
  teaser: /assets/images/cables-stable-diffusion-preview.png
---

The models that power generative AI are a herculean effort by a large number of researchers. But an interface for those models was not really designed in parallel. Now that the audience for these models is broader, we're obligated to create new intuitive interfaces for these models.

Cables.gl is a visual programming environment for webGL. It is similar in philosophy to TouchDesigner, except that it runs in the browser. I have been learning this tool, and decided to use it to send your 3D environment from Cables into Stable Diffusion. Also uses ControlNet and Automatic1111.

Here is a walkthrough of my proof of concept.

{% include video id="n4UPiZhbcRU" provider="youtube" %}

Check out [some of my other experiments](https://cables.gl/user/neight/) on Cables.gl