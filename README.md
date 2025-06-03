# ViewGauss-DataSet
# ViewGauss: A Head Movement Dataset for 6DoF 4D Gaussian Video Viewing

This repository contains the official implementation, data files, and usage instructions for **ViewGauss**, a high-precision 6DoF head movement dataset collected during the free viewing of 4D Gaussian splatting videos.

ViewGauss is designed to support research in immersive behavior modeling, neural rendering optimization, and viewpoint prediction in next-generation virtual reality environments. All data were recorded from 35 participants using the Vive Focus Vision HMD.

## Introduction
**ViewGauss** is the first publicly released dataset designed to capture **6-degree-of-freedom (6DoF) head movement** during free-viewing of **4D Gaussian splatting videos**. It serves as a critical resource for immersive behavior modeling, viewpoint prediction, and adaptive rendering in next-generation VR environments.

While 4D Gaussian splatting has become a promising technique for photorealistic and efficient rendering, the lack of behavior datasets specific to this format has hindered research progress. ViewGauss addresses this gap with synchronized 6DoF recordings of 35 participants watching Gaussian splatting video sequences derived from high-fidelity human performance data.

## Dataset Overview

| Property               | Description                                |
|------------------------|--------------------------------------------|
| Participants           | 35 (Age 23–42, diverse backgrounds)        |
| Hardware               | [HTC Vive Focus Vision](https://www.vive.com/cn/) + [Unity Vive OpenXR](https://developer.vive.com/resources/openxr/)       |
| Video Content          | 4 sequences from the [HiFi4G dataset](https://github.com/moqiyinlun/HiFi4G_Dataset)         |
| Sampling Rate          | 10Hz synchronized                          |
| Data Format            | CSV (Frame, Position, Quaternion)      |
| Head Pose Dimensions   | PosX, PosY, PosZ + RotX–RotW              |
| Duration               | ~1 min per sequence per participant        |

Videos were reconstructed using HiFi4G recordings featuring dynamic human actions (e.g., dancing, walking) and diverse attire. Each session was conducted in a controlled environment with calibrated devices to ensure signal stability and fidelity.

## Technical Details

- High-resolution tracking with millimeter precision  
- Quaternion-based rotation (numerical stability, no gimbal lock)  
- Unified timestamping aligned with video playback  
- Free-viewing design (natural behavior, no assigned tasks)  
- Post-processed for filtering and anomaly removal

## Analysis and Visualization

To illustrate the spatial characteristics of user behavior during 4D Gaussian splatting video viewing, we provide several example visualizations derived from the dataset.

### Head Position Distribution

The figure below shows the spatial distribution of head positions in the viewing space. Most users remain within a tightly bounded region around the origin (±0.3 meters), indicating that they tend to adjust their view through small corrective motions rather than large spatial movements.

![3D Head Position Distribution](figures/head_position_distribution.png)

*Figure 1: 3D distribution of head positions for all participants. Each blue dot represents a sampled head location. Spatial dispersion results from natural variation in height and initial stance.*

### Viewing Direction Distribution

We also visualize the distribution of viewing directions using unit quaternion data converted into direction vectors. The majority of gaze vectors are concentrated within a ±30° cone, suggesting a strong forward-facing attention bias in Gaussian splatting environments.

![View Direction Polar Plot](figures/viewing_angle_distribution.png)

*Figure 2: Polar plot of head orientation. Most view directions lie within the user’s primary field of view, forming a narrow cone.*

## Benchmark: Viewpoint Prediction

To evaluate the predictive power of the dataset, we conduct an initial viewpoint forecasting task using the [iTransformer](https://arxiv.org/abs/2310.06625) architecture.

- **Input**: 5 seconds of head pose history  
- **Output**: Next-frame orientation  
- **Accuracy**: 92.02% – 95.88% across sequences  

| Sequence | Accuracy |
|----------|----------|
| Seq 1    | 93.92%   |
| Seq 2    | 92.02%   |
| Seq 4    | 92.15%   |

These results confirm the temporal coherence and learnability of head movement behaviors in 4D Gaussian environments.


## Use Cases

This dataset can be used for:

- Head movement modeling in immersive 6DoF environments
- Viewpoint prediction and behavior forecasting
- Gaussian Splatting video performance evaluation
- Bandwidth allocation and attention region optimization

## License

This dataset is released under the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/).


