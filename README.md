### WARNING: This is not an API. If you want to do something with the Python libraries installed in the docker image, you need to code it yourself.

## Main Libraries
#### Not Python

```
tesseract-ocr (english support pre-installed)
tesseract-ocr-por (portuguese support)
```

#### Python
```
pytesseract
tesserocr
pdf2image

Pillow
opencv-contrib-python

numpy
pandas
pyarrow
```

## How to install the docker image

Option 1: pull the image from DockerHub. Before pulling ("downloading") the image, if you wish, you may check it at https://hub.docker.com/r/leommiranda/tesserocr. Then, pull the image from DockerHub with the following command. 
```
docker pull leommiranda/tesserocr
```

Option 2: build the docker image by yourself. 
```
# clone the repository
git clone https://github.com/leomichalski/tesserocr

# change the current directory to the root folder of this repo
cd tesserocr

# build the docker image
docker build . -t leommiranda/tesserocr -f docker/Dockerfile
```

## How to run Jupyter Lab

```
docker run --rm -p 8888:8888 -e JUPYTER_ENABLE_LAB=yes -v ${PWD}:/current_dir -w /current_dir leommiranda/tesserocr
# Open one of the 3 server links that will appear in the terminal. I usually go with the last one.
```

## How to run a Python script

```
docker run --rm -v ${PWD}:/current_dir -w /current_dir leommiranda/tesserocr python [SCRIPT_NAME].py
```

## How to run multiple Python scripts

```
docker run -it --rm -v ${PWD}:/current_dir -w /current_dir leommiranda/tesserocr bash
python [SCRIPT_NAME_1].py
python [SCRIPT_NAME_2].py
(...)
```

### (☞ﾟヮﾟ)☞
