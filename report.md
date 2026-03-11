# Dissemination:

## SfN 2025

We showcased Bonsai and Bonsai.ML at the 2025 Society for Neuroscience (SfN) Conference in San Diego, CA (Booth #3726). The exhibit featured interactive rollups and live, real-time software demonstrations. Engagement spanned a diverse user base, ranging from researchers new to the ecosystem to expert users seeking updates on recent developments. A key outcome included a technical consultation with PopNeuron, who expressed interest in integrating Bonsai.ML into their real-time spike-sorting algorithms for Neuropixels probes https://popneuron.com/spike-sorting/ This consultation highlights the platform's growing utility in high-density electrophysiology workflows.

## External Seminar and Strategic Consultation: Prof. Bert de Vries

Activity Description and Purpose:

We hosted Prof. Bert de Vries (Eindhoven University of Technology), a global leader in reactive inference and the developer of the RxInfer.jl Julia package, for a seminar and strategic consultation at the Gatsby Computational Neuroscience Unit. The primary purpose was to explore the integration of reactive inference methodologies into the Bonsai.ML framework for real-time experimental control.

Outcomes and Impact:

Technical Knowledge Exchange: We conducted live demonstrations of Bonsai.ML’s real-time inference capabilities, leading to a strategic technical consultation on the feasibility of adapting Prof. de Vries’s reactive inference algorithms for low-latency neuroscience applications.

Strategic Network Expansion: This visit established a direct conduit to the Signal Processing Systems community in the Netherlands. Prof. de Vries is actively facilitating the dissemination of Bonsai.ML within his professional network, targeting researchers specifically interested in closed-loop animal experimentation.

Collaborative Roadmap: This engagement has opened a formal dialogue with reactive inference experts, providing our team with high-level theoretical guidance that will inform the future development of the Bonsai.ML codebase, particularly regarding variational inference in real-time streams.

---

# Software

## TorchSharp package released

We developed and released the Bonsai.ML.Torch package (https://bonsai-rx.org/machinelearning/articles/Torch/torch-overview.html), integrating the TorchSharp engine directly into the Bonsai ecosystem. This integration provides users with a high-performance framework for tensor manipulation, complex linear algebra, and the deployment of deep neural networks. By enabling native GPU-accelerated processing within the Bonsai ecosystem, this package significantly lowers the barrier for researchers implementing real-time, AI-driven experimental control.

## Decoder package released

Neural decoding models are used to reconstruct features of the external world from brain activity, providing a quantitative measure of information contained within neural processes. Traditionally, these models are constructed offline after data collection is complete. We developed a real-time decoder package for Bonsai.ML designed to estimate these models online, directly as experimental data is being streamed.

We have validated the decoder across several experimental contexts, transitioning from offline benchmarking to live deployment, using both low- and high-channel-count recording technologies:

1. Offline Validation (Tetrodes): Decoding animal position from hippocampal sorted spikes.
(Source: https://bonsai-rx.org/machinelearning/examples/examples/PointProcessDecoder/DecodePositionFromHippocampusSortedUnits/README.html)

2. Online Implementation (Tetrodes): Real-time decoding of position from clusterless marks.
(Source: https://bonsai-rx.org/machinelearning/examples/examples/PointProcessDecoder/DecodePositionFromStriatumSortedUnits/README.html)

3. Offline Validation (Neuropixels): Decoding position from striatal sorted spikes using high-density probes.
(Source: https://bonsai-rx.org/machinelearning/examples/examples/PointProcessDecoder/DecodePositionFromStriatumSortedUnits/README.html)

4. Offline Validation (Tetrodes): Simultaneous position decoding and classification of neural states from hippocampal sorted units.
(Source: https://bonsai-rx.org/machinelearning/examples/examples/PointProcessDecoder/ClassifyPositionFromHippocampusSortedUnits/README.html)

### Scientific and Technical Impact

The ability to estimate models online facilitates closed-loop neuroscience, such as the immediate detection and disruption of hippocampal replay events to investigate their causal role in behavior. To ensure the high performance required for these low-latency applications, the decoder was natively implemented in C# using the Bonsai.ML.Torch package, leveraging GPU acceleration for efficient computation. Detailed technical overviews can be found at: https://bonsai-rx.org/machinelearning/articles/Torch/torch-overview.html

## Native Implementation of Linear Dynamical Systems (Lds.Torch)

We have successfully developed and released Lds.Torch, a native C# implementation of Linear Dynamical Systems (LDS) built on the TorchSharp engine. This represents a major technical evolution from our previous iteration, which relied on external Python backends. By eliminating the overhead of Python interoperation, the new package allows for high-efficiency parameter estimation and latent variable inference directly within the Bonsai environment.

Validation and Documentation:

The implementation was successfully demonstrated for the estimation of latent variables in neural populations. Technical documentation and example workflows are available at:
https://ncguilbeault.github.io/machinelearning/examples/examples/LinearDynamicalSystems/NeuralLatents/EstimatingParameters/README.html

## Development of a General-Purpose Deep Learning Framework (Torch.NeuralNetworks)

We have developed the Torch.NeuralNetworks package, a comprehensive suite within Bonsai.ML designed for the design, training, and deployment of Artificial Neural Networks (ANNs). By leveraging the TorchSharp engine, this package enables researchers to implement complex deep learning architectures natively within the Bonsai graphical environment.

The versatility of the package was validated across four distinct computational tasks:

- Regression Analysis: Implementation of ordinary least squares for foundational statistical modeling.
(Source: https://ncguilbeault.github.io/machinelearning/examples/examples/NeuralNetworks/LinearRegression/SimpleOrdinaryLeastSquares/README.html)

- High-Dimensional Image Classification: Development of custom models for digit recognition (MNIST), demonstrating the framework's capacity for complex computer vision tasks.
(Source: https://ncguilbeault.github.io/machinelearning/examples/examples/NeuralNetworks/ImageClassification/CustomMnistModel/README.html)

- Depth Perception: Utilizing neural networks to infer spatial depth from 2D images, a critical task for behavioral tracking and environmental mapping.
(Source: https://ncguilbeault.github.io/machinelearning/examples/examples/NeuralNetworks/ImageClassification/CustomMnistModel/README.html)

- Temporal Dynamics (Recurrent Neural Networks): Implementation of RNNs for online parameter estimation and inference. This is particularly relevant for modeling time-varying neural data and sequential behavior.
(Source: https://ncguilbeault.github.io/machinelearning/examples/examples/NeuralNetworks/RecurrentNeuralNetworks/TrainedOnline/README.html)

### Technical impact

The Torch.NeuralNetworks package bridges the gap between high-level machine learning research and live experimental execution. It allows for the integration of pre-trained models or the training of new architectures directly on streaming experimental data, providing a scalable solution for AI-driven neuroscience research.

## Development of the PCA.Torch Package for Dimensionality Reduction

We have developed PCA.Torch, a high-performance Principal Component Analysis (PCA) package built on the TorchSharp engine. This package provides researchers with a robust tool for dimensionality reduction and feature extraction, which are critical for processing high-dimensional neural and behavioral data.

A key innovation of this package is the support for both traditional and real-time processing modes:

- Batch Analysis: Provides high-throughput dimensionality reduction on static datasets. We validated this by performing batch classification of MNIST digits, achieving efficient data compression while maintaining high classification accuracy.
(Source: https://ncguilbeault.github.io/machinelearning/examples/examples/PrincipalComponentAnalysis/BatchFit/README.html)

- Streaming Online Analysis: Enables the estimation of principal components on-the-fly as data is acquired. This functionality is essential for closed-loop experiments where low-latency feature extraction is required to trigger experimental events.
(Source: https://ncguilbeault.github.io/machinelearning/examples/examples/PrincipalComponentAnalysis/StreamingOnline/README.html)

### Technical impact

By implementing PCA natively within the Bonsai.ML.Torch framework, we allow researchers to perform complex data transformations without leaving the Bonsai ecosystem. The online implementation, in particular, overcomes a major bottleneck in systems neuroscience by allowing for the real-time visualization and manipulation of neural manifolds.

## Adaptation of decoder to work with Neuropixels probes (Nick can you send me an URL pointing to a preliminary version of this)

## CI/CD pipeline

We integrated the Bonsai.ML project into the standardized continuous integration GitHub Actions pipeline used by all other Bonsai projects. Since Bonsai.ML relies so much on examples with large datasets, the standard pipeline had to be extended to allow continuous versioning and validation of the external examples repository. The CI/CD pipeline also takes care of continuous automated deployment of all changes, by packing and publishing preview packages to the GitHub package repository, and publishing tagged releases to the NuGet package repository (https://www.nuget.org/packages/Bonsai.ML). This pipeline significantly reduces the infrastructure development and management effort required to deploy new functionality, facilitates onboarding of externals collaborators, reduces the cost to review and integrate contributions, and overall represents a fundamental investment in the sustainability of the Bonsai.ML project going forward.

---

# Collaborations

## Collaboration with Dr. Stanley's group (Georgia Tech) integrating into Bonsai.ML his their estimation package

### Briefly describe the contributions made by you and/or your research team to this collaboration or partnership

Our team provided the technical framework and architectural oversight required to integrate Dr. Stanley’s research tools into the Bonsai.ML ecosystem. Upon identifying Bonsai.ML as the preferred platform for high-impact dissemination, we provided code auditing and software engineering consultancy to the Stanley Lab https://stanley.gatech.edu/ Our primary contribution has been the rigorous review of their implementation to ensure it meets the professional standards for performance, stability, and interoperability required for the official Bonsai.ML repository. This process ensures that the resulting tools are not only functional but also sustainable and maintainable by the wider neuroscience community.

### Briefly describe the contributions made by your partners to this collaboration or partnership.

Dr. Stanley’s group initiated the partnership to transition their real-time control methodologies from legacy systems (RTXI) to a more modern, widely adopted framework. They successfully developed a specialized package for the online inference of neural states from Local Field Potentials (LFP) in rodents. This involved a sophisticated integration of Python-based logic into the C# Bonsai.ML environment. Their ability to independently leverage our existing documentation to build these packages serves as a successful "stress test" of our platform’s extensibility and documentation quality, demonstrating that Bonsai.ML is now accessible to external developers.

### List any outputs or outcomes that have resulted from this collaboration or partnership. Full details of each should be reported under the relevant sections of the form. Indicate whether this collaboration is multi-disciplinary, if so outline each of the disciplines involved.

Outputs:

Software Repository (Core): https://github.com/ndac-bonsai/neurostate-hmm

Software Repository (Examples): https://github.com/ndac-bonsai/neurostate-hmm-examples

Outcomes:

This collaboration marks a major milestone: the first successful external contribution to the Bonsai.ML ecosystem (neurostate-hmm). This validates the project’s goal of creating a community-contributed library for machine learning in neuroscience.

Multi-disciplinary Nature:

This partnership is inherently multi-disciplinary, bridging Experimental Neuroscience (neural recording in rodents), Signal Processing (neural state inference and LFP analysis), and Software Engineering (reactive programming and cross-language integration between Python and C#).

---
