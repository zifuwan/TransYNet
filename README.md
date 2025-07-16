# TransY-Net Learning Fully-Transformer-Network-for-Change-Detection-of-Remote-Sensing-Images

## Usage

### 1. Download pre-trained Swin Transformer models
* [Get models in this link](https://github.com/SwinTransformer/storage/releases/download/v1.0.0/swin_base_patch4_window7_224_22kto1k.pth):SwinB pretrain in ImageNet22K 


### 2. Prepare data

Please use split.py to split the images first, and use bimap.py, deal.py and check.py to make the images become binary images.

### 3. Environment

Please prepare an environment with python=3.7, opencv, torch and torchvision. And then when running the program, it reminds you to install whatever library you need.

### 4. Train/Test

- If you want to try the model, you can directly use the train.py.

```bash
CUDA_VISIBLE_DEVICES=0 python train.py
```

- If you want to use the ssim and iou loss function with crossEntropy loss funtion together, you just need to remove comment in train.py(below the crossEntropy loss) and add the loss operation in loss calculation place.
- Especially, when you calculate the iou loss, you need to convert the images(convert 0->1, 1->0). Because the image pixels values are mostly 0, and it will influence the iou loss calculation(Based on iou loss characteristic).

- If you want to obtain the result, you can directly use the test.py.
```bash
python test.py 
```

## Reference
* [Swin Transformer](https://github.com/microsoft/Swin-Transformer)


## Citations

```bibtex
@article{yan2023transy,
  title={Transy-net: Learning fully transformer networks for change detection of remote sensing images},
  author={Yan, Tianyu and Wan, Zifu and Zhang, Pingping and Cheng, Gong and Lu, Huchuan},
  journal={IEEE Transactions on Geoscience and Remote Sensing},
  volume={61},
  pages={1--12},
  year={2023},
  publisher={IEEE}
}
```
