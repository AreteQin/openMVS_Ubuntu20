```
sudo apt-get -y install git cmake libpng-dev libjpeg-dev libtiff-dev libglu1-mesa-dev freeglut3-dev libglew-dev libglfw3-dev libcgal-dev libcgal-qt5-dev
cd ~/Downloads
mkdir openMVS && cd openMVS
git clone https://github.com/cdcseacave/VCG.git vcglib
git clone https://gitlab.com/libeigen/eigen.git --branch 3.4
cd eigen/
mkdir build && cd build
cmake .. -DCMAKE_INSTALL_PREFIX=../install
make install
cd ../..
git clone https://github.com/AreteQin/openMVS_Ubuntu20.git
cd openMVS_Ubuntu20
mkdir openMVS_build && cd openMVS_build
cmake .. -DCMAKE_BUILD_TYPE=Release -DVCG_ROOT="../../vcglib"
make -j8
```

# OpenMVS: open Multi-View Stereo reconstruction library

[![Watch reconstruction](https://i.imgur.com/S4L0E6r.jpeg)](https://sketchfab.com/models/3aedcdd22c31447199c18dd9aec5d952/embed)

## Introduction

[OpenMVS (Multi-View Stereo)](http://cdcseacave.github.io/openMVS) is a library for computer-vision scientists and especially targeted to the Multi-View Stereo reconstruction community. While there are mature and complete open-source projects targeting Structure-from-Motion pipelines (like [OpenMVG](https://github.com/openMVG/openMVG)) which recover camera poses and a sparse 3D point-cloud from an input set of images, there are none addressing the last part of the photogrammetry chain-flow. *OpenMVS* aims at filling that gap by providing a complete set of algorithms to recover the full surface of the scene to be reconstructed. The input is a set of camera poses plus the sparse point-cloud and the output is a textured mesh. The main topics covered by this project are:

- **dense point-cloud reconstruction** for obtaining a complete and accurate as possible point-cloud
- **mesh reconstruction** for estimating a mesh surface that explains the best the input point-cloud
- **mesh refinement** for recovering all fine details
- **mesh texturing** for computing a sharp and accurate texture to color the mesh

See the complete [documentation](https://github.com/cdcseacave/openMVS/wiki) on wiki.

## Build

See the [building](https://github.com/cdcseacave/openMVS/wiki/Building) wiki page. Windows and Ubuntu x64 continuous integration status [![Build Status](https://ci.appveyor.com/api/projects/status/github/cdcseacave/openmvs?branch=master&svg=true)](https://ci.appveyor.com/project/cdcseacave/openmvs)
Automatic Windows x64 binary builds can be found for each commit on its Appveyor Artifacts page.

## Example

See the usage [example](https://github.com/cdcseacave/openMVS/wiki/Usage) wiki page.

## License

See the [copyright](https://github.com/cdcseacave/openMVS/blob/master/COPYRIGHT.md) file.

## Contact

openmvs[AT]googlegroups.com
