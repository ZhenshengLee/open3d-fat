# open3d

open3d-0.11.2+ml-0.12.1

## 环境

### 依赖

```
sudo apt install libfmt-dev pybind11-dev libqhull-dev
```

### 升级组件

### 修改代码

```
Open3D/cpp/open3d/core/linalg/BlasWrapper.h

#include "cblas-netlib.h" <-- add this
#include "open3d/core/linalg/LinalgHeadersCPU.h"
```

### jetson

```sh
sudo apt remove --purge libfmt-dev ros-melodic-rosfmt
```

### 构建

```sh
# 适用1804
cmake .. -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/opt/open3d/open3d -DBUILD_CUDA_MODULE=ON -DBUILD_PYTHON_MODULE=OFF -DBUILD_GUI=OFF -DBUILD_JUPYTER_EXTENSION=OFF -DUSE_BLAS=ON -DUSE_SYSTEM_EIGEN3=OFF -DUSE_SYSTEM_FLANN=ON -DUSE_SYSTEM_FMT=OFF -DUSE_SYSTEM_GLEW=ON -DUSE_SYSTEM_GLFW=ON -DUSE_SYSTEM_GOOGLETEST=ON -DUSE_SYSTEM_JPEG=ON -DUSE_SYSTEM_PNG=ON -DUSE_SYSTEM_PYBIND11=ON -DWITH_FAISS=ON -DGLIBCXX_USE_CXX11_ABI=ON

# 全部用源编译
cmake .. -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/opt/open3d/open3d -DBUILD_CUDA_MODULE=OFF -DBUILD_PYTHON_MODULE=OFF -DBUILD_GUI=OFF -DBUILD_JUPYTER_EXTENSION=OFF -DUSE_BLAS=ON -DWITH_FAISS=ON -DGLIBCXX_USE_CXX11_ABI=ON
```
