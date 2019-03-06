# Dlcontainer

## How to run

'''
docker run --runtime=nvidia --rm -d -p 8888:8888 -p 6006:6006  -v yourpath:/notebook <image-name:tags>

'''

## Bugs
Jupyter notebook may fail to start due to the version of tornad

'''
pip install --upgrade tornado==5.1.1
'''
