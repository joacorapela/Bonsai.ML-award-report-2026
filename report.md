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

## Torch package for learning and inference in Linear Dynamical System (LinearDynamicalSystems.Torch) created

We have previously developed a Linear Dynamical Systems package in Bonsai that used a backend Python package https://github.com/joacorapela/ssm. We have now created a native C# (TorchSharp) implementation of this package and demonstrated it for the estimation of latent variables underlying high-channel-count electrophysiological recordings https://ncguilbeault.github.io/machinelearning/examples/examples/LinearDynamicalSystems/NeuralLatents/EstimatingParameters/README.html

## Torch package for the estimation of artificial neural network (Torch.NeuralNetworks) created

We created a Torch package for the estimation of artificial neural networks. We demonstrated this package in:

    - linear regression https://ncguilbeault.github.io/machinelearning/examples/examples/NeuralNetworks/LinearRegression/SimpleOrdinaryLeastSquares/README.html
    - image classification https://ncguilbeault.github.io/machinelearning/examples/examples/NeuralNetworks/ImageClassification/CustomMnistModel/README.html
    - inferring depth from images https://ncguilbeault.github.io/machinelearning/examples/examples/NeuralNetworks/ImageClassification/CustomMnistModel/README.html
    - estimating the parameters and doing inference in a recursive neural network https://ncguilbeault.github.io/machinelearning/examples/examples/NeuralNetworks/RecurrentNeuralNetworks/TrainedOnline/README.html

## Torch package for Principal Components Analysis (PCA.Torch) created

We create a Torch package for principal components analysis. We demonstrated this package in the batch and online classification of MNIST digits:

- batch https://ncguilbeault.github.io/machinelearning/examples/examples/PrincipalComponentAnalysis/BatchFit/README.html
- online https://ncguilbeault.github.io/machinelearning/examples/examples/PrincipalComponentAnalysis/StreamingOnline/README.html

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
