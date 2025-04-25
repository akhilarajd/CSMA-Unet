# CSMA-Unet
# CSMA-UNet: Enhanced UNet with Convolutional Shortcuts and Multi-head Attention Module

This repository is for the CSMA-UNet model proposed in the following paper:


## Dependencies
- Python 3.6
- PyTorch 1.5.1
- pytorch-msssim 0.2.0
- ptflops 0.6.3
- tqdm 4.48.2
- scikit-image 0.17.2
- yaml 0.2.5
- MATLAB (to create testing datasets)

## Dataset
For training, we used BSD500 dataset[
[Download](https://www.kaggle.com/datasets/balraj98/berkeley-segmentation-dataset-500-bsds500).  Image folders are in the './Dataset' folder. You can modify the ```train_files.txt``` and ```val_files.txt``` to load only part of the dataset.

## Training
Default parameters used in the paper are set in the ```config.yaml``` file:

```
patch size: 64
batch size: 16
learning rate: 1.e-4
weight decay: 1.e-5
scheduler gamma: 0.5
scheduler step: 3
epochs: 21
```
Additionally, you can choose the device, the number of workers of the data loader, and enable multiple GPU use.

To train the model use the following command:

```python main_train.py```

## Test

Place the pretrained models in the './Pretrained' folder. Modify the ```config.yaml``` 

Test datasets need to be prepared using the MATLAB codes in './Datasets' folder according to the desired noise level. The model CSMA-UNet is tested with [CBSD68](https://github.com/cszn/FFDNet/tree/master/testsets/CBSD68), [Kodak24](http://r0k.us/graphics/kodak/), and [Urban100](https://www.kaggle.com/datasets/harshraone/urban100/code) datasets.

To test the model use the following command:

```python main_test.py```


