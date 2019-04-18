# Dlcontainer

##
This docker image is designed for GPU supported(only) deep learning for common usage and fMRI analysis. The settings of jupyter notebook was guided from my friend @lizequn.
If you want to apply it as a remote python interpreter in pycharm, try to modify the docker daemon.json file add the following lines:
```
{
"default-runtime" = nvidia,
"runtimes": {
        "nvidia": {
            "path": "/usr/bin/nvidia-container-runtime",
            "runtimeArgs": []
        }
    }
}
```
Then set the python interpreter in pycharm to the specific docker image.
More fMRI tools would be added to this image in the future.
## How to run
```
docker run --runtime=nvidia --rm -d -p 8888:8888 -p 6006:6006 -e PASSWORD=yourPasswd -v yourpath:/notebook <image-name:tags>

```
## Bugs
Jupyter notebook may fail to start due to the version of tornad

```
pip install --upgrade tornado==5.1.1
```
## Notice
The latest tensorflow requires cuda10.0 and the latest nvidia driver.
The latest version contains pymc3 and nibabel for fMRI analysis
