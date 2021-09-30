---
title:  "Georgia Tech Projects"
layout: default
---

# Georgia Tech Projects

I completed a Masters of Science degree in CS from Georgia Tech in August 2021. Because many of the projects I worked on for classes are used every term, plagiarism rules prevent me from sharing the details of all of what I worked on in the program. But I can give broad descriptions some particular projects and classes!

## CS 7643, Deep Learning

The fourth assignment for this class, written in Python using PyTorch, had two components. First, I implemented several basic units used in the [Seq2Seq](https://google.github.io/seq2seq/) framework, including RNN and LSTM units and a single-layer Transformer encoder. Second, I trained a network built using these units and the Seq2Seq framework to translate German sentences to English.

## CS 7642, Reinforcement Learning

The second assignment for this class, written in Python using Keras, focused on implementing and training a reinforcement learning agent to perform well on the ["Lunar Lander"](https://gym.openai.com/envs/LunarLander-v2/) problem from OpenAI gym. I built an agent using the Deep-Q Learning approach, which trains an agent to estimate the Q function evaluating a state for continuous states where just using the normal update rule fails. I then experimented with parameterization to evaluate the impact of hyperparameters on training and overall performance.

## CS 6200, Graduate Intro to Operating Systems

I learned C to write projects for this class, and felt like I'd jumped was into the deep end! For the second project I built a multi-threaded file server using a libcurl-based file handler and a caching system. The project focused on interprocess communication and managing multithreaded applications. Because I was learning the language alongside the assignment, this might have been the most stressful project I worked on - but also one of the most satistfying to see work!

## CS 6476, Computer Vision

For the final project, I trained two neural net architectures to classify digits from the Stanford "Street View House Numbers" dataset and built a preprocessing pipeline to apply these models to classify digits in larger images. The first network leveraged a VGG-16 network pre-trained on the ImageNet dataset and swapped out the final two layers, the second was a small "homebrew" CNN. The pipeline used filters to increase contrast, then evaluated each maximally stable extremal region using one of the models to predict strings of digits in large images.

## CS 6475, Computational Photography

For the final project of this class, I worked on estimating vanishing points in urban settings, which have neat boxy structures. I used a k-means algorithm to select from candidate intersections of edges found through the Hough Lines algorithm. Using these vanishing points, I simulated the blur seen in tilt-shift photography. In theory, this can create an "auto-tilt shift" algorithm for any urban photo.

