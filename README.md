Video App in C++
================

I'm building a visualisation tool for live music performances. The app generates video
grids containing one video for every element in the song. For elements that are pre-recorded
the videos will be pre-recorded. For elements that are played live, the videos will be taken
from webcams/capture cards/live streams.


## Installation

### 1. Prerequisites

This app has 4 external dependencies:

- **CMake** to build the project,
- **pkg-config** to locate shared libraries,
- **FFmpeg** to read and write video files.

On MacOS using Homebrew, run:

```sh
brew install cmake ffmpeg pkg-config
```

### 2. Clone

```sh
git clone https://github.com/bartjoyce/video-app --recursive
```

The repository includes a submodule for GLFW, so make sure to *recursively* clone the repo. If CMake complains and says it can't find GLFW, it might be because you did not clone it properly. In that case, try:

```sh
git submodule update --init
```

### 3. Build

Inside the repo, create a build directory and run CMake within it:

```sh
mkdir build
cd build
cmake ..
make
```

### 4. Run

```sh
./video-app
```

## Bonus: Webcam capture with AVFoundation

For webcam capture:

```sh
git checkout test/webcam
cd build
cmake ..
make
./video-app
```

This will use AVFoundation to display your webcam on the OpenGL surface.
