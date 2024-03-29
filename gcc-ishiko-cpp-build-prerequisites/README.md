# Docker Images with GCC and the build prerequisites for Ishiko/C++

Configuration files for [Docker](https://www.docker.com/) images that contain [GCC](https://gcc.gnu.org/), CMake and
the [Boost](https://www.boost.org/) libraries.

The images are available from [Docker Hub](https://hub.docker.com/r/ishikocpp/gcc-boost).

# Image Contents

The images are based on the [the official GCC Docker image](https://hub.docker.com/_/gcc) with the addition of CMake
and the Boost libraries, which are installed in /usr/local/include and /usr/local/lib.

The image uses a [multi-stage build](https://docs.docker.com/develop/develop-images/multistage-build/) to remove
the files generated during the build process from the final image.

The first stage is based on the GCC Docker image. The Boost source code is downloaded from the Boost website and
then built using the Boost build scripts. The python-dev package is also installed as it is required to build
Boost.Python.

The second stage is also based on the GCC Docker image but in this stage we simply copy CMake and the Boost libraries
from the first stage to the /usr/local/include and /usr/local/lib directories of the final image.

# Upload Instructions

```
docker build --no-cache .
docker tag <id> ishiko/gcc-ishiko-cpp-build-prerequisites:latest
docker tag <id> ishiko/gcc-ishiko-cpp-build-prerequisites:<version>
docker login
docker push ishiko/gcc-ishiko-cpp-build-prerequisites:latest
docker push ishiko/gcc-ishiko-cpp-build-prerequisites:<version>
```
