# README for HKUST Lidar-IMU Indoor Dataset

| Topics                        | Description                                                  | Type                        |
| :---------------------------- | :----------------------------------------------------------- | :-------------------------- |
| /Robot_7/pose                 | Ground-truth pose from the motion capture system (Twgt)      | geometry_msgs/PoseStamped   |
| /imu/data                     | raw Xsens MTi-100 IMU data, acceleration and angular velocity, 400Hz | sensor_msgs/Imu             |
| /velodyne_points              | Velodyne VLP16 data, 10Hz                                    | sensor_msgs/PointCloud2     |
| /usb_cam/image_raw/compressed | Front-view camera, for visualization only                        | sensor_msgs/CompressedImage |

Rough estrinsic parameters (from the IMU frame to the lidar frame $\mathbf{T}^L_B$):
- Rotation Matrix: [1 0 0; 0 1 0; 0 0 1]
- Translation: [0, 0, -0.08]

Ground-truth lidar pose correction ($\mathbf{T}^W_L = \mathbf{T}^W_R \cdot \mathbf{T}^R_L$), i.e. Twgt_corrected = Twgt * Tg:
- Correction Matrix Tg: [0.999877177965312 -0.00313481972900284 0.0153558421908658 0 0.00339959550486683 0.999845479466994 -0.0172470269849422 0 -0.0152994030774867 0.0172971123220811 0.999733333529892 0 0 0 0 1]
