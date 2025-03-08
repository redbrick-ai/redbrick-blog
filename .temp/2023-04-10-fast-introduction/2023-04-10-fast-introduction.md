---
title: "Introducing F.A.S.T: RedBrick AI's Fast Automated Segmentation Tool"
date: "2023-04-10"
category: "Product"
excerpt: "We're excited to release our Fast Automated Segmentation Tool, powered by Meta AI's SAM, for medical imaging. Segment your DICOM & NIfTI data 10x faster with state-of-the-art AI segmentation integrated into RedBrick AI's web-based annotation platform."
author: "Shivam Sharma"
thumbnail: "./thumbnail.png"
---

We're excited to release our Fast Automated Segmentation Tool, powered by [Meta AI's SAM](https://ai.facebook.com/blog/segment-anything-foundation-model-image-segmentation/), for medical imaging. Combining the state-of-the-art AI segmentation model SAM, and RedBrick AI's leading web-based annotation platform for radiology, you can now **segment your DICOM & NIfTI data 10x faster!**

F.A.S.T. works with all radiology modalities and is a general-purpose automatic segmentation tool that can be used for any application. Fill out the form above to request access!

**Meta's Segment Anything Model**

Last week, Meta AI Research released the Segment Anything Model (SAM), which is a **first attempt at creating a foundational model for image segmentation**. Traditionally, AI systems were created from scratch for narrow use cases. For each application, a model had to be trained on a large task-specific dataset to enable it to automatically label similar data points in the future.

Recently, task-specific AI systems have been replaced by large general-purpose models called foundational models for several use cases. Foundational models are trained on a diverse data set once and are fine-tuned with small datasets for each application. For example, GPT-3 is the foundational model behind [ChatGPT](https://openai.com/blog/chatgpt).

The Segment Anything Model has been trained on the largest-ever segmentation dataset --- the [**Segment Anything 1-Billion mask dataset** (SA-1B)](https://ai.facebook.com/datasets/segment-anything/). SAM has a general understanding of objects in images, with the ability to generate a mask for any object in any image. The incredibly **impressive part of SAM is its zero-shot capabilities** --- its ability to generalize to new domains without the need for additional training data.

**How does SAM work?**

Large Language Models (LLM) like GPT-3 are incredible in generalizing to new domains, partly because of the ability to **prompt** the models to illicit a relevant response. The Meta team took inspiration from LLMs and has designed SAM to have a **promotable** interface with the ability to adapt to new domains and tasks.

SAM is trained to return a **_valid_** segmentation mask for any **prompt.** In this context, a prompt is some information about a region of interest; for example, a key point, bounding box, or text identifying objects in an image.

Prompting is a very interactive way of using an AI model. This workflow constrains the model design to support running in real-time (or close to it) on CPUs and browsers. To achieve this, SAM has an encoder-decoder architecture --- the compute-intensive process of calculating image embeddings happens once, after which different segmentation masks can be produced with different prompts in real-time (< 50 milliseconds!).

**What's encoding-decoding?**

Encoding involves converting image data, i.e. pixel/voxel data, into a vector format suitable for machine learning. This vector of embeddings are **features** of the image that the model can learn. Decoding is the process of converting the vector output of a machine-learning model back into a visual representation of pixels/voxels. In the context of SAM, the image-encoding process is compute-intensive but only needs to happen once. With the image embeddings, you can interactively generate segmentation masks in real time through prompts.

This architecture also opens up **interesting workflows in medical
imaging** where the embeddings can be pre-computed, and then SAM can run
in the browser on the client side, **preserving privacy.**

**SAM in medical imaging**

Even though SAM has not been trained on radiology data, it performs
remarkably well on a diverse set of use cases. Through our
experimentation, it seems that SAM can perfectly segment any
object/feature that you can see with the naked eye. For example, SAM is
incredibly effective in large organ segmentation in CT and MRI scans
(even when contrast isn't very high).

![chest.gif](./image1.gif)

The interactive nature of the segmentation makes it extremely ergonomic.
You can see the mask compute in real-time as you prompt the model (draw
the bounding box), making accurate segmentation quick and simple. You
can prompt SAM with any information about the region of interest in the
image; for example, a key point.

![spine.gif](./image2.gif)

The Meta team's objective with SAM is to **democratize**
segmentation which is incredibly promising for radiology applications.
Most modern radiology AI systems rely on segmentations to perform
diagnosis, quantification, or other analysis. With F.A.S.T., teams can
automate a large part of the manual segmentation process by simply
classifying the automatically generated segmentations.

**F.A.S.T. & RedBrick AI**

RedBrick AI is a SaaS platform for annotating medical image data. The
Fast Automated Segmentation Tool is our application of SAM in the
radiology domain. If you're interested in using F.A.S.T. on
your own datasets, please reach out to us or fill out the form above!

Thanks!
