# 00 Build Environment

This folder is meant to contain the files required for a Yocto build environment.
The build environment consists of a docker container that downloads all
the dependencies required to build a Yocto image, based on the Yocto docs. To
use the container, the idea is the following:

1. Build the docker image
2. Run an interactive shell incontainer, mounting the specified volumes in the docker file
3. Perform build steps

It is meant to be more of an interactive dev environment, as opposed to something
that would be used in CI/CD.
