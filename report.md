
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

3, Offline Validation (Neuropixels): Decoding position from striatal sorted spikes using high-density probes.
(Source: https://bonsai-rx.org/machinelearning/examples/examples/PointProcessDecoder/DecodePositionFromStriatumSortedUnits/README.html)

4 Offline Validation (Tetrodes): Simultaneous position decoding and classification of neural states from hippocampal sorted units.
(Source: https://bonsai-rx.org/machinelearning/examples/examples/PointProcessDecoder/ClassifyPositionFromHippocampusSortedUnits/README.html)

### Scientific and Technical Impact

The ability to estimate models online facilitates closed-loop neuroscience, such as the immediate detection and disruption of hippocampal replay events to investigate their causal role in behavior. To ensure the high performance required for these low-latency applications, the decoder was natively implemented in C# using the Bonsai.ML.Torch package, leveraging GPU acceleration for efficient computation. Detailed technical overviews can be found at: https://bonsai-rx.org/machinelearning/articles/Torch/torch-overview.html

## Published Decoder package in Bonsai.ML

Neural decoding is a fundamental tool for extracting information about external world features from brain activity. While decoding is traditionally performed offline during post-hoc analysis, we have developed a real-time decoder package for the Bonsai.ML ecosystem. This allows researchers to estimate and apply decoding models online, enabling a transition from observational study to active, closed-loop intervention.

We tested the decoder on several setups:

1. Offline decoding of position from hippocampal sorted spikes recorded with tetrodes https://bonsai-rx.org/machinelearning/examples/examples/PointProcessDecoder/DecodePositionFromHippocampusSortedUnits/README.html
2. Online decoding of position from clusterless marks and tetrode recordings https://bonsai-rx.org/machinelearning/examples/examples/PointProcessDecoder/DecodePositionFromStriatumSortedUnits/README.html
3. Offline decoding of position from striatal sorted spikes recorded with Neuropixels probes https://bonsai-rx.org/machinelearning/examples/examples/PointProcessDecoder/DecodePositionFromStriatumSortedUnits/README.html
4. Offline decoding of position and classification of neural activity from hippocampal sorted units recorded with tetrodes https://bonsai-rx.org/machinelearning/examples/examples/PointProcessDecoder/ClassifyPositionFromHippocampusSortedUnits/README.html

This package is still under development, but the current functionality represents a large improvement with respect to the state of the art in neural decoding.

The online decoder model open a wide range of possibilities in neuroscience, like disrupting replay as soon as it is detected, to investigate the causal effect of replay on behavior.

The decoder was natively and efficiently implemented in C# using the Bonsai.ML.Torch package.

## Adaptation of decoder to work with Neuropixels probes (Nick can you send me an URL pointing to a preliminary version of this)

## Real-time LDS package for neural latents operating on multi-unit activity

## CICD pipeline

---

# Collaborations

## Collaboration with Garrett producing the first externally contributed Bonsai.ML package

---

# Funding

## 2024 BBSRC-NSF/BIO

## 2025 RSMF round 1

## 2026 RSMF round 2

