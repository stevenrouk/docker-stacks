# Jupyter Docker Stacks - With Auto-Sklearn Stack

Identical to [jupyter/docker-stacks](https://github.com/jupyter/docker-stacks), with the addition of a new "auto-sklearn-notebook" folder that has a Dockerfile for building an image that installs auto-sklearn.

If you want a Docker image that is already pre-built, and has a much simpler Dockerfile, see here: [stevenrouk/autosklearn](https://hub.docker.com/r/stevenrouk/autosklearn). This is built from a Docker image originally created by Matthias Feurer.

To run the Docker image in a new container with a name of "autosklearn" and a volume mounted to the current working directory:

```bash
docker run -it --name autosklearn -v $PWD:/opt/nb -p 8888:8888 stevenrouk/autosklearn \
/bin/bash -c "mkdir -p /opt/nb && jupyter notebook --notebook-dir=/opt/nb --ip='0.0.0.0' --port=8888 --no-browser --allow-root"
```