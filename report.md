
# Dissemination:

## SfN 2025

We showcased Bonsai and Bonsai.ML at the 2025 Society for Neuroscience (SfN) Conference in San Diego, CA (Booth #3726). The exhibit featured interactive rollups and live, real-time software demonstrations. Engagement spanned a diverse user base, ranging from researchers new to the ecosystem to expert users seeking updates on recent developments. A key outcome included a technical consultation with PopNeuron, who expressed interest in integrating Bonsai.ML into their real-time spike-sorting algorithms for Neuropixels probes https://popneuron.com/spike-sorting/ This consultation highlights the platform's growing utility in high-density electrophysiology workflows.

## Bert de Vries

Hosted a visit from Prof. Bert de Vries to the Unit and discussed the feasibility of integrating his reactive probabilistic programming language into Bonsai.ML

---

# Software

## Published TorchSharp package in Bonsai.ML

We developed and released the Bonsai.ML.Torch package (https://bonsai-rx.org/machinelearning/articles/Torch/torch-overview.html), integrating the TorchSharp engine directly into the Bonsai ecosystem. This integration provides users with a high-performance framework for tensor manipulation, complex linear algebra, and the deployment of deep neural networks. By enabling native GPU-accelerated processing within the Bonsai ecosystem, this package significantly lowers the barrier for researchers implementing real-time, AI-driven experimental control.

## Published Decoder package in Bonsai.ML

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

## Adaptation of decoder to work with Neuropixels probes (Nick can you send me an URL pointing to a preliminary version of this)

## Real-time LDS package for neural latents operating on multi-unit activity

## CI/CD pipeline

We integrated the Bonsai.ML project into the standardized continuous integration GitHub Actions pipeline used by all other Bonsai projects. Since Bonsai.ML relies so much on examples with large datasets, the standard pipeline had to be extended to allow continuous versioning and validation of the external examples repository. The CI/CD pipeline also takes care of continuous automated deployment of all changes, by packing and publishing preview packages to the GitHub package repository, and publishing tagged releases to the NuGet package repository (https://www.nuget.org/packages/Bonsai.ML). This pipeline significantly reduces the infrastructure development and management effort required to deploy new functionality, facilitates onboarding of externals collaborators, reduces the cost to review and integrate contributions, and overall represents a fundamental investment in the sustainability of the Bonsai.ML project going forward.

---

# Collaborations

## Collaboration with Garrett producing the first externally contributed Bonsai.ML package

---

# Funding

## 2024 BBSRC-NSF/BIO

## 2025 RSMF round 1

## 2026 RSMF round 2

