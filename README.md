>目前只上传了大部分的图片,视频素材,还在整理描述中,剩余部分,可以先通过网页预览或下载来查看了解一下
------
- [2D](#2d)
  - [退化场景中的定位(长直走廊)](#退化场景中的定位长直走廊)
  - [变化场景中的地图自更新](#变化场景中的地图自更新)
  - [变化场景、遮挡下的防定位丢失](#变化场景遮挡下的防定位丢失)
- [3D](#3d)
  - [3D LIO](#3d-lio)
  - [3D SLAM](#3d-slam)
  - [局部场景下高精鲁棒定位](#局部场景下高精鲁棒定位)

# 2D

## 退化场景中的定位(长直走廊)

- **长廊定位效果展示(长廊环境长度约22米,激光量程10米,图中机器人行驶的走廊长度为22米,定位误差肉眼不可见)**

<div align="center">
    <img src="gif/long_corridor_failed.gif" >
</div>

> 如上,平时在退化场景下会出现定位的较大漂移

<div align="center">
    <img src="gif/long_corridor_succeed.gif" >
</div>

> 加入开发的长廊定位算法后的效果。没有肉眼可见的误差

------

- **基于原始激光点云的长廊环境自识别**
<div align="center">
    <img src="gif/long_corridor_detection.gif" >
</div>

## 变化场景中的地图自更新

<div align="center">
    <img src="gif/large_change_online_updatemap.gif" width = 100% >
</div>

> 大量环境变化下的地图更新

<div align="center">
    <img src="gif/small_change_online_updatemap.gif" width = 100% >
</div>

> 局部变化下的地图更新(未消失的黑影是由于采图时人员一直在激光后方)

## 变化场景、遮挡下的防定位丢失

- 室内

<div align="center">
    <img src="gif/old_3号_4号丢失点.gif" width = 100% >
</div>

> 蓝色pose箭头变为半透明表示定位丢失

<div align="center">
    <img src="gif/new_3号_4号丢失点.gif" width = 100% >
</div>

> 全程无丢失,回到无变化场景立即恢复高精定位

- 室外

<div align="center">
    <img src="gif/old_scene.gif" width = 100% >
</div>

<div align="center">
    <img src="gif/new_scene.gif" width = 100% >
</div>

- 激光被遮挡

  <div align="center">
      <img src="gif/完全遮挡下定位.gif" width = 100% >
  </div>

# 3D

## 3D LIO

- 地铁检修站

<div align="center">
    <img src="gif/3D_LIO_Subway_Station.gif" width = 100% >
</div>

> 地铁检修站场景,涉及10度斜坡。
>
> 140m*10m来回两圈,仅前端无回环: **xy误差约2.5cm,z误差约9cm**

- 室外电站

<div align="center">
    <img src="img/3d_lio_xieshi.png" width = 100% >
</div>

- 室内

<div align="center">
    <img src="img/3d_lio_only_front.png" width = 100% >
</div>

## 3D SLAM

- 从室外建筑群到室内地下停车场(稀疏图)

<div align="center">
    <img src="img/optimized_2021_01_20.png" width = 100% >
</div>

<div align="center">
    <img src="img/optimized_xie_2021_01_20.png" width = 100% >
</div>

<div align="center">
    <img src="gif/optimized_3d_mapping.gif" width = 100% >
</div>

> 从室外的移动写字楼环绕一圈后 通过 隧道进入地下停车场 再回到室外建图起点
> 基于32线激光/IMU/WheelOdom融合建图,履带式底盘(激光存在高频振动,点云有错帧)

- 建筑群周围(稠密图)

<div align="center">
    <img src="img/3d_slam_around_building.png" width = 100% >
</div>

## 局部场景下高精鲁棒定位

<div align="center">
    <img src="gif/fg_chargeroom_loc.gif" width = 100% >
</div>

- 多人干扰,新增障碍物下的鲁棒定位

<div align="center">
    <img src="gif/fg_chargeroom_loc_anti_interference.gif" width = 100% >
</div>





