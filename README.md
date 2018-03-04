# Supercharged Machine Learning ToolBox for ARM

A [Docker](http://docker.com) image for ARM devices with [Tensorflow 1.4.0](https://www.tensorflow.org/) an open source software library for numerical computation using data flow graphs that will let you play and learn distinct Machine Learning techniques over [Jupyter Notebook](http://jupyter.org/) an open-source web application that allows you to create and share documents that contain live code, equations, visualizations and explanatory text. Computational Narratives as the Engine of Collaborative Data Science.   

> Be aware! You should read carefully the usage documentation of every tool!

## Latest Changes
1.4.0
-----
- Upgraded from Tensorflow 1.3.0 to 1.4.0
- Replaced Tensorflow local binary to [tensorflow-1.4.0-cp27-none-any.whl](http://ci.tensorflow.org/view/Nightly/job/nightly-pi/lastSuccessfulBuild/artifact/output-artifacts/tensorflow-1.4.0-cp27-none-any.whl)

1.3.0
-----
- Upgraded from Tensorflow 1.2.1 to 1.3.0

1.2.1
-----
- Replaced base image by a [Docker Official Image](https://github.com/docker-library/official-images)
- Upgraded from Tensorflow 1.1.0 to 1.2.1

## Details
- [Docker Hub](https://hub.docker.com/r/elswork/rpi-tensorflow/)
- [Deft.Work my personal blog](http://deft.work/tensorflow_for_raspberry)

## Thanks to

- [Romilly Cocking for the idea](https://github.com/romilly/rpi-docker-tensorflow)
- Pi tensorflow whl file that i builded thanks to [Sam Abrahm's Step-By-Step Guide for build Tensorflow for Raspberry Pi](https://github.com/samjabrahams/tensorflow-on-raspberry-pi/blob/master/GUIDE.md)

## My Real Usage Example

In order everyone could take full advantages of the usage of this docker container, I'll describe my own real usage setup.
```sh
$ docker run -d -p 8888:8888 elswork/rpi-tensorflow:latest

```
A more complex sample:
```sh
$ docker run -d -p 8888:8888 \
 -p 0.0.0.0:6006:6006 \
 -v ~/myNotebooks:/notebooks/myNotebooks \
 --restart=unless-stopped \
 elswork/rpi-tensorflow:latest
```
Point your browser to `http://localhost:8888`

First time you open it, you should provide a Token to log on you cand find it with this command:

```sh
$ docker logs container_name
```

With the second example you can run TensorBoard executing this command in the container:

```sh
$ tensorboard --logdir=path/to/log-directory --host=0.0.0.0
```
And pointing your browser to `http://localhost:6006`
