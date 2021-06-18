
- [代码运行及解读](#代码运行及解读)
  - [run demo](#run-demo)
  - [代码解读](#代码解读)


## 代码运行及解读

### run demo
```bash
roslaunch loam_livox rosbag.launch
rosbag play /home/ipsg/下载/CYT_02.bag
```

### 代码解读
原始数据  
提取特征，剔除坏点(主要是laser_feature_extractor.cpp/hpp，它引用了livox_feature_extractor.hpp)  
点云配准，位姿估计（主要是point_cloud_registration.hpp，也有scene_alignment.hpp）  
程序中转核心（laser_mapping.hpp/cpp），同时构建场景地图  
优化（ceres_icp.hpp，ceres_pose_graph_3d.hpp）  
程序中转核心（laser_mapping.hpp/cpp），取回优化值，更新位姿和地图  


