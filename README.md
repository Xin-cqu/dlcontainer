# Dlcontainer

##
This docker image is designed for GPU supported(only) deep learning for common usage and fMRI and EEG analysis. The former settings of jupyter notebook was guided from my friend @lizequn. Now it is more convenient.
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

Such settings are not recommended.
## How to build
Just clone this project and run the cli:
```
docker build -t <image-name:tags> .
```
## How to run
```
docker run --rm -d --gpus all -p 8888:8888 -p 6006:6006 -e PASSWORD=yourPasswd -v yourpath:/notebook <image-name:tags>

```

## Notice
Expample cli commend is:
```
docker run --rm -d --gpus all -p 8888:8888 -p 6006:6006 -e PASSWORD=yourPasswd -v yourpath:/notebook xin0214/dlcontianer:latest
```
