# ViewGauss-DataSet
# ViewGauss: A Head Movement Dataset for 6DoF 4D Gaussian Video Viewing

**ViewGauss** is the first publicly available head movement dataset specifically designed for immersive **4D Gaussian Splatting video** scenarios under **6 degrees of freedom (6DoF)** settings. It captures the spatial behavior of users watching dynamic neural-rendered scenes using a head-mounted display.

## 🧠 Dataset Overview

- **Participants**: 35
- **Videos**: 4 reconstructed Gaussian videos (from [HiFi4D](https://github.com/facebookresearch/hifi-4d))
- **Device**: Vive Focus Vision (10Hz sampling)
- **Format**: 6DoF head pose (XYZ positions + Quaternion rotations)
- **Files**: Each user-session stored as a CSV file with timestamps

## 📁 Data Format

Each `.csv` file includes:
`Frame, PosX, PosY, PosZ, RotX, RotY, RotZ, RotW`

## 📌 Use Cases

This dataset can be used for:

- Head movement modeling in immersive 6DoF environments
- Viewpoint prediction and behavior forecasting
- Gaussian Splatting video performance evaluation
- Bandwidth allocation and attention region optimization

## 📢 Release Notice

**🚀 ViewGauss will be made publicly available soon.**  
Stay tuned for updates and licensing details.
