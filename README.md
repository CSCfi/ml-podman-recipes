# Podman recipes for machine learning environments on Roihu

This repository contains the [Podman][] recipes for the machine
learning environments on the [Roihu][] supercomputer. If you just wish
to use them, it's easiest to load one of the [pre-installed
modules][roihu-modules].

**Note:** pre-built images can be found from the
[`r_installation_aida` project in CSC's container repository
Satama][satama-aida]. Normally you don't need to build them yourself
but you can for example extend one of the images.

- See [an example of how to extend our pre-built images](https://docs.csc.fi/support/tutorials/roihu/#roihu-mlai-gpu-base-containers)
- See [a tutorial on how to extend our pre-built images in a Sandbox on  Roihu](https://docs.csc.fi/support/tutorials/ml-container-extend/)


The recipes are split into directories:

- `ml-base` - basic Rocky Linux images with Python 3, MPI and CUDA.
- `pytorch` - basic PyTorch images (`PyTorch*_base*`) and with extra packages (`PyTorch*_extras*`)
- `tensorflow` - TensorFlow
- `jax` - JAX

Example:

```bash
podman build -t ml-base:rocky9.7_gcc12_py3.12_cuda13 -f ml-base/Rocky9.7_gcc12_py3.12_cuda13
podman build -t pytorch-base:2.13_cuda13_roihu -f pytorch/PyTorch2.13_base_cuda13_roihu
podman build -t pytorch:2.13_cuda13_roihu -f pytorch/PyTorch2.13_extras_cuda13_roihu
```


[roihu-modules]: https://docs.csc.fi/apps/by_discipline/#data-analytics-and-machine-learning
[Podman]: https://podman.io/
[Roihu]: https://docs.csc.fi/computing/systems-roihu/
[satama-aida]: https://satama.csc.fi/harbor/projects/144/repositories
