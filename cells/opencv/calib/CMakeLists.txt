
ectomodule(calib DESTINATION ecto/opencv INSTALL
  module.cpp
  calib.cpp
  CameraIntrinsics.cpp
  PatternDrawer.cpp
  PatternDetector.cpp
  CircleDrawer.cpp
  SubrectRectifier.cpp
  # DepthTo3d.cpp # needs opencv2/rgbd.hpp
  pose_drawing.cpp
  KConverter.cpp
  Latch.cpp
  TransformCompose.cpp
  FiducialPoseEst.cpp
  CameraCalibrator.cpp
  GatherPoints.cpp
  DepthMask.cpp
  PointsTo3d.cpp
  CropBox.cpp
  )

link_ecto(calib
  OPENCV3_CALIB3D
)
