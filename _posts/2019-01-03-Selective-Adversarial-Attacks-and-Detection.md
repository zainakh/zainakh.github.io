---
layout: post
title: "Selective Adversarial Attacks and Detection"
excerpt: "My research project background and current progress as an ICRU Research Fellow for 2020. Link to code and further information can be found inside."
categories: [research]
tags: [security, deep learning]
comments: true
---

<!--more-->

Deep learning is a subset of machine learning that utilizes more layers in its network architecture so that it can make complex decision boundaries. These attacks take this complexity into account and leverage it maliciously. Adversarial attacks add a small amount of selective noise to the input image of a deep learning model in a way that it is unrecognizably different from the original image from a human perspective, yet will cause the network to behave terribly. They optimize the amount of error that can be induced in the network by targeting areas where specific pixel values lie far on the incorrect side of the decision boundary. 

This project has taken two directions: creating an adversarial attack that can fool multiple networks except for a certain one and detecting corrupt Fourier coefficient image information used in MRI image reconstruction.

The existence of these attacks mean that machines take different image features into importance than humans do. Building an attack that can fool multiple networks with the exception of one can shed light as to why machines are susceptible to these attacks and how they can be improved. The MRI image reconstruction also investigates this. Storing MRI images as a series of Fourier coefficients and reconstructing them with deep learning networks into detailed MRI images is common practice, although is susceptible to adversarial attacks as well. Mildly changing the input Fourier coefficients can render the reconstruction useless, with the resultant image being unusable in a medical setting. Understanding why these networks are susceptible to attacks can provide insight to larger questions as to if machines will be able to think like humans, which would undoubtedly be a revolution in science. 

I am excited to work in a novel direction relative to existing efforts in adversarial attacks and see great promise to making deep learning models secure. As machine learning popularizes, the number of safety-critical applications that use it increases as well. Reliance should parallel security in applications, especially in deep learning where machine’s decision making criteria is not (currently) humanly interpretable. 

Currently, creating an adversarial image that selectively targets models is working! Simply adding a loss function component that makes one model stay close to the true label is enough for the attack to work on model but not the other. As paper writing wraps up, I will include the results of the experiments here as well. 

As for the detection of corrupt Fourier image information, that will be fleshed out after the paper submission for the selective adversarial attack problem. 

View my progress in this project [here](https://github.com/zainakh/ICRU_2020/).
