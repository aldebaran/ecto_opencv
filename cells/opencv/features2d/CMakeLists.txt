ectomodule(features2d DESTINATION ecto_opencv INSTALL
  module.cpp
  # DescriptorExtractor.cpp # depends on opencv contrib
  DrawKeypoints.cpp
  # FeatureDetector.cpp
  KeypointsToMat.cpp
  LshMatcher.cpp
  MatchesToMat.cpp
  match_draw.cpp
  matcher.cpp
  ORB.cpp
  ransac_est.cpp
  )

link_ecto(features2d
    OPENCV3_CALIB3D
    OPENCV3_FEATURES2D
    OPENCV3_IMGPROC
)
