# Computer Vision Practice with Deep Learning Homework 1
* B09901142 電機四 呂睿超

## Environments
* Colab T4 GPU
* Python 3.10
* CUDA 11.8

0. Follow the `DETR_cvpdlhw1.ipynb` to set up on environment on google colab **or** the following steps
1. Install Pytorch and torchvision
   ```sh
   !pip install torch==2.4.0 torchvision==0.19.0 torchaudio==2.4.0 --index-url https://download.pytorch.org/whl/cu118
   ```
2. Install other needed packages
   ```sh
   pip install -r requirements.txt
   ```
3. Compiling CUDA operators
   ```sh
   cd models/dino/ops
   python setup.py build install
   cd ../../..
   ```


## Run

### Download

* Model Pre-trained checkpoint [LINK](https://drive.google.com/file/d/1CrzFP0RycSC24KKmF5k0libLRJgpX9x0/view)
* Pre-trained backbone checkpoint [LINK](https://github.com/SwinTransformer/storage/releases/download/v1.0.0/swin_large_patch4_window12_384_22k.pth)
* hw1_dataset
Download the pre-trained weight of model and backbone and place them as the following 
```
hw1_b09901142/
   ├── checkpoint0029_4scale_swin.pth
   ├── swin_large_patch4_window12_384_22k.pth
   ├── hw1_dataset/
      ├── ...
   └── ...
```

### Train

```sh
bash scripts/DINO_train_4scale_swin.sh swin_large_patch4_window12_384_22k.pth 
```

Or follow the training part in ```DETR_cvpdlhw1.ipynb``` 

### Predict
Please also refer to ```DETR_cvpdlhw1.ipynb```, specifically Part *Inference* to Part *Obtain output*. 