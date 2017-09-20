
list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR})
find_package(numpy)

if(${PYTHON_NUMPY_NOT_FOUND})
    message(WARNING "Numpy could not be found. Do not compile bp_cv")
    return()
endif()

include_directories(${PYTHON_NUMPY_INCLUDE_DIR})

qi_create_lib(opencv_boost_python SHARED
  opencv.cpp
  cv_core.cpp
  cv_mat.cpp
  cv_points.cpp
  cv_highgui.cpp
  highgui_defines.cpp
)

set_target_properties(opencv_boost_python
  PROPERTIES
  OUTPUT_NAME cv_bp
  PREFIX ""
)

qi_use_lib(opencv_boost_python
  BOOST_PYTHON
  PYTHON
  OPENCV3_CORE
  OPENCV3_HIGHGUI
  OPENCV3_VIDEOIO
)

qi_install_target(opencv_boost_python
  SUBFOLDER python2.7/dist-packages/ecto_opencv
)
