# projector-docker
Some scripts to create and run a Docker container with projector and IDEA.

## TL;DR
If you've just cloned the `projector-docker` repo, you probably should make the following actions:
1. `clone-projector-core.sh`.
1. `build-container.sh`.
1. `run-container.sh`.

If you've received a `tar.gz` Docker image, you probably should run the following ones:
1. `load-image.sh`.
1. `run-container.sh`.

Both instructions will run **nginx** and **projector with IDEA** locally.

To access projector with IDEA, use <http://localhost:8080/projector/>.

## Accessing IDEA run on another machine

If you want to access IDEA run on another host, you can change page parameters: <http://localhost:8080/projector/?host=localhost&port=8887> (these are default ones).

You need to run docker on different machines: change the `run-container.sh` script to launch nginx on the first one and projector on the second one.

## Script list
### `clone-projector-core.sh`
Clones projector from Git.

**Note**: you can omit this cloning by creating a symlink to your existing `projector-core`:
```shell script
ln -s YOUR_REAL_PATH_TO_PROJECTOR_CORE PATH_TO_PROJECTOR_DOCKER/projector-core
```

### `build-container.sh`
Compiles projector and builds a Docker container locally.

### `create-image.sh`
Creates a Docker image from a built container and saves it as a `tar.gz` archive.

### `load-image.sh`
Loads the Docker image locally.

### `run-container.sh`
Runs the Docker container.

Starts the server on 8887.