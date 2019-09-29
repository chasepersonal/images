# Images

This repository will contain dockerfiles for commonly used images for developement or cloud related infrastructure building.

This repository will have the following functions:

1.) Provide a backup of commonly used images

2.) Provide a common standard for containerized development within VS Code

With VS Code allowing development within containers that also virtualizes the text editor, this repository will take advantage of that and provide common `.devcontainer.json` files and `Dockerfiles` that allow for containerized development based on the language being used.

The `Dockerfiles` themselves will also be constructed in a way that will create a non-root user in a virtual VS Code environment and allow Docker within a Docker container. This will ensure root access is limited, reduce local Git branch conflicts/confustion, and allow the building and pushing of docker containers with the development container. 

As such, this will provide a way to isolate one's development environment from their host environment.

Instructions on how to develop inside a container using VS Code can be found at Microsoft's website: 

https://code.visualstudio.com/docs/remote/containers