# RetinaNet
An implementation of [RetinaNet](https://arxiv.org/abs/1708.02002).

![RetinaNet Structure](/images/retinanet.png)

## Installation

1. Install [PyTorch](http://pytorch.org/) and [torchvision](https://github.com/pytorch/vision). 
2. For faster data augmentation, install [pillow-simd](https://github.com/uploadcare/pillow-simd):

```
pip uninstall -y pillow
pip install pillow-simd
```

## Training

### [COCO 2017](http://cocodataset.org/)

1. First, install [pycocotools](https://github.com/pdollar/coco/):

```bash
git clone https://github.com/pdollar/coco/
cd coco/PythonAPI
make
python setup.py install
cd ../..
rm -r coco
```

2. Then download [COCO 2017](http://cocodataset.org/dataset.htm#overview) into `./datasets/COCO/`:

```bash
cd datasets
mkdir COCO
cd COCO

# If using wget:
wget http://images.cocodataset.org/zips/train2017.zip &&
wget http://images.cocodataset.org/zips/val2017.zip &&
wget http://images.cocodataset.org/annotations/annotations_trainval2017.zip

# Using aria2c (recommended for higher bandwidth connections and for easier resuming of the download,
# tune the number of connections as needed):
aria2c -x 10 -j 10 http://images.cocodataset.org/zips/train2017.zip &&
aria2c -x 10 -j 10 http://images.cocodataset.org/zips/val2017.zip &&
aria2c -x 10 -j 10 http://images.cocodataset.org/annotations/annotations_trainval2017.zip

unzip *.zip
rm *.zip
```

Then just run:

```
python train_coco.py --gpu
```


### Custom Dataset
Lots to write here. :wink:

## Evaluation

## Credits
