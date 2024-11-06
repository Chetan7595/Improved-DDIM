# DDIM Pytorch

[DDIM (Denoising Diffusion Implicit Models)](https://arxiv.org/abs/2010.02502) is a powerful diffusion-based generative model implemented in Pytorch.

## Installation

This code works fine with Python version `3.12.7`. Install the required modules by running the following command:

```
pip install -r requirements.txt
```

## Training

You can train the DDIM model on various datasets:

### Cifar10 (64 dimension)

```commandline
python train.py -c ./config/cifar10.yaml
```

### Cifar10 (128 dimension) 

```commandline
python train.py -c ./config/cifar10_128dim.yaml
```

### CelebA-HQ

```commandline
python train.py -c ./config/celeba_hq_256.yaml
```

## Inference

You can run inference on the trained models:

### Cifar10 (64 dimension)

```commandline
python inference.py -c ./config/inference/cifar10.yaml -l /path_to_cifar10_64dim.pt/cifar10_64dim.pt
```

### Cifar10 (128 dimension)

```commandline
python inference.py -c ./config/inference/cifar10_128dim.yaml -l /path_to_cifar10_128dim.pt/cifar10_128dim.pt
```

### CelebA-HQ

Download the CelebA-HQ dataset from the Google Drive link and save it according to the following file structure:

```
- DDIM
    - /config
    - /src
    - /images_README
    - inference.py
    - train.py
    ...
    - /data (make the directory if you don't have it)
        - /celeba_hq_256
            - 00000.jpg
            - 00001.jpg
            ...
```

Then, run the following command for inference:

```commandline
python inference.py -c ./config/inference/celeba_hq_256.yaml -l /path_to_celeba_hq_256.pt/celeba_hq_256.pt
```

The trained model checkpoints will be saved in the `results` folder after running the training commands. You can find the specific paths to the `.pt` files and update the inference commands accordingly.
