# Efficient-AoADet
Official PyTorch implementation of "Efficient-AoADet". A lightweight, physics-guided framework for radar object detection, tailored for the RADDet and RADIal datasets.

## Title: Physics-Guided and Jointly Optimized AoA Learning for Lightweight Radar Object Detection
## Abstract
Millimeter-wave radar offers robust perception under visually degraded conditions, yet its deployment in real-world systems is often hindered by computational inefficiencies and insufficient task adaptivity. Existing pipelines rely on dense range-azimuth-Doppler (RAD) tensors with fixed angle-FFT preprocess, limiting both efficiency and performance. We propose a lightweight radar detection framework that jointly performs task-adaptive optimization with Angle of Arrival (AoA) estimation, integrating physics-guided priors. Our method leverages the more compact complex-valued range-Doppler spectrum as input and replaces angle-FFT with a learnable angular estimation module, enabling task-driven refinement while reducing overhead. To enhance accuracy, we introduce an Inter-Dimensional Attention module that explicitly models interactions across the anisotropic dimensions of radar data. For high-definition radars with Doppler Division Multiple Access, we further design a physically grounded virtual channel decoupling scheme based on empty-band masking. Extensive experiments on both low-definition and high-definition radar datasets show that our method significantly reduces computational overhead (up to 48.9\% fewer parameters and 52.8\% lower FLOPs, and 7.6-fold faster inference) while maintaining an average of 18.6\% improvement in detection accuracy over advanced RAD-based approaches, highlighting its promise for efficient and adaptive radar perception in autonomous applications.

## Method framework

## Main contribution
We introduce Efficient-AoADet, a lightweight radar object detection framework that integrates physics-guided signal modeling with multi-task joint optimization. This approach significantly enhances detection efficiency while maintaining robust performance. The main contribution of this paper is threefold:
  * A physics-guided, task-adaptive AoA estimation module. Initialized from the FFT basis that replaces traditional angle-FFT with a learnable linear transform. This design enhances angular feature learning under end-to-end supervision while reducing computational and storage overhead.
  
  * A physics-informed empty-Band Masked virtual channel decoupling strategy for DDMA-based HD radars. By embedding waveform-specific physical priors into the network, this module enables the accurate separation of signal contributions from individual TX antennas in the received data, leading to reliable and enhanced AoA estimation.
  
  * An InterDim-Attn module that is explicitly designed to capture the dependencies among radar's physically distinct dimensions (range, Doppler, and angle), consistently enhancing detection precision and localization quality with minimal computational cost.

## Code

Our proposed framework was initially validated on LD radar data, and subsequently extended to HD radar configurations to demonstrate its superior performance across different radar systems. We conduct experiments on two public datasets: the LD radar dataset RADDet and the HD radar dataset RADIal. 

This project includes separate implementations tailored for the RADDet and RADIal datasets. 

*   **[Code to be released upon acceptance][Code for RADDet Dataset](https://github.com/pangyangyang1122/Efficient-AoADet-RADDet.git)**: Implementation and instructions for the low-definition RADDet dataset. 

*   **[Code to be released upon acceptance][Code for RADIal Dataset](https://github.com/pangyangyang1122/Efficient-AoADet-RADIal.git)**: Implementation and instructions for the high-definition RADIal dataset.
