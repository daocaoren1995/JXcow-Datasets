# JXcow-Datasets
JXCow Dataset: RGB–Depth–Point Cloud Cattle Weight Estimation Dataset<img width="784" height="116" alt="54b590e7-82fd-48a8-8540-0fc2056c4c75" src="https://github.com/user-attachments/assets/894efccd-9b73-4488-8bf1-3aba01fa438c" />

# 1. Dataset Overview

JXCow dataset link: 

JXCow is a multimodal beef cattle weight estimation dataset collected in a real farm environment. It includes RGB images, 16-bit depth maps, point clouds, and body-weight labels. The dataset provides pixel-level cross-modal consistency through a pipeline consisting of resolution-adaptive calibration scaling, cross-modal alignment, semantic segmentation, and point cloud pose normalization, enabling research on contactless cattle weight estimation.

# 2. Data Collection Setup and Devices

Collection site: Jixing Meat Co. feedlot, Changchun, Jilin Province, China.
Acquisition system: A dual-camera (overhead + side-view) multimodal setup installed on a weighing corridor/channel structure:
Overhead camera is approximately 2.8 m above the ground,Side-view camera is approximately 2.5 m from the corridor center
Sensors: Two Intel RealSense D455 devices, synchronously capturing:RGB and 16-bit depth;Resolution 640×480 at 30 fps;
Weight labels: When cattle step onto the weighing platform, an electronic scale records body weight in real time, synchronized with the captured data streams (including camera intrinsics).
![拍摄设备图_1](https://github.com/user-attachments/assets/648bd417-3842-418d-9389-a4475d7bb06a)

# 3. Dataset Scale and Statistics

Number of animals: 112 cattle
Weight range: 400–800 kg (mainly concentrated in 500–700 kg)
Raw recordings: Each animal has a synchronized sequence of 35–60 s stored as raw .bag files.
Frame sampling strategy: One frame is kept every 30 frames, and motion blur/occlusion detection is applied to select high-quality RGB–Depth–PointCloud triplets, forming the raw dataset JX-raw.

# 4.JXcow-Datasets4. Preprocessing and Cross-Modal Alignment
![预处理_1](https://github.com/user-attachments/assets/cbf6687b-25f7-4b70-9372-b293bfae719d)

The processed dataset JX-preprocess is obtained from JX-raw via:
Resolution-adaptive intrinsic scaling and pixel-level alignment;Semantic segmentation and background removal;Point cloud reconstruction and pose normalization.This preprocessing improves cross-modal correspondence and standardizes point cloud pose for downstream learning tasks.
