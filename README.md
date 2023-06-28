# Spectral-Spatial Global Graph Reasoning for Hyperspectral Image Classification (TNNLS 2023)

### Di Wang, Bo Du, and Liangpei Zhang

### Pytorch implementation of our [paper](https://arxiv.org/pdf/2106.13952.pdf) for graph convolution based hyperspectral image classification.

<figure>
<img src=model.png>
<figcaption align = "center"><b>Figure - The proposed SSGRN. </b></figcaption>
</figure>

## Usage
1. Install Pytorch 1.9 with Python 3.8.
2. Clone this repo.
```
git clone https://github.com/DotWang/SSGRN.git
```
3. Prepare a suitable GCC version, then install the SSN
```
cd utils/src
python setup.py install
```
4. Training, validation, testing and prediction with ***trainval.py*** :

For example, when implementing SSGRN on [Salinas Valley dataset](http://www.ehu.eus/ccwintco/index.php/Hyperspectral_Remote_Sensing_Scenes)

```
 CUDA_VISIBLE_DEVICES=0 python -u trainval.py \
    --dataset 'salina' --network 'ssgrn' \
    --norm 'norm' \
    --input_mode 'whole' \
    --input_size 128 128 --overlap_size 54 \
    --experiment-num 10 --lr 1e-3 \
    --epochs 1000 --batch-size 1 \
    --val-batch-size 1 \
    --se_groups 256 --sa_groups 256
```
Then the evaluated accuracies, the trained models and the classification maps are separately saved.

When training on the Houston dataset, using the mode of `part` and setting the input_size

```
    --input_mode 'part' \
    --input_size 349 635 --overlap_size 0 \
```

## Paper and Citation

If this repo is useful for your research, please cite our [paper](https://arxiv.org/abs/2106.13952).

```
@ARTICLE{wang_2023_ssgrn,
  author={Wang, Di and Du, Bo and Zhang, Liangpei},
  journal={IEEE Transactions on Neural Networks and Learning Systems}, 
  title={Spectral-Spatial Global Graph Reasoning for Hyperspectral Image Classification}, 
  year={2023},
  volume={},
  number={},
  pages={1-14},
  doi={10.1109/TNNLS.2023.3265560}}

```

## Thanks
[GCN-Pytorch](https://github.com/tkipf/pygcn) &ensp; [MDGCN](https://github.com/LEAP-WS/MDGCN) &ensp; [SSN](https://github.com/NVlabs/ssn_superpixels) &ensp; [SSN-Pytorch](https://github.com/perrying/ssn-pytorch)


## Relevant Projects
[1] <strong> Pixel and Patch-level Hyperspectral Image Classification </strong> 
<br> &ensp; &ensp; Adaptive Spectral–Spatial Multiscale Contextual Feature Extraction for Hyperspectral Image Classification, IEEE TGRS, 2020 | [Paper](https://ieeexplore.ieee.org/document/9121743/) | [Github](https://github.com/DotWang/ASSMN)
<br> <em> &ensp; &ensp;  Di Wang<sup>&#8727;</sup>, Bo Du, Liangpei Zhang and Yonghao Xu</em>

[2] <strong> Image-level/Patch-free Hyperspectral Image Classification </strong> 
<br> &ensp; &ensp; Fully Contextual Network for Hyperspectral Scene Parsing, IEEE TGRS, 2021 | [Paper](https://ieeexplore.ieee.org/document/9347487) | [Github](https://github.com/DotWang/FullyContNet)
 <br><em> &ensp; &ensp; Di Wang<sup>&#8727;</sup>, Bo Du, and Liangpei Zhang</em>
 
[3] <strong> Neural Architecture Search for Hyperspectral Image Classification </strong> 
<br> &ensp; &ensp; HKNAS: Classification of Hyperspectral Imagery Based on Hyper Kernel Neural Architecture Search, IEEE TNNLS, 2023 | [Paper](https://ieeexplore.ieee.org/document/10159237) | [Github](https://github.com/DotWang/HKNAS)
 <br><em> &ensp; &ensp; Di Wang<sup>&#8727;</sup>, Bo Du, Liangpei Zhang, and Dacheng Tao</em>

[4] <strong> ImageNet Pretraining and Transformer based Hyperspectral Image Classification </strong> 
<br> &ensp; &ensp; DCN-T: Dual Context Network with Transformer for Hyperspectral Image Classification, IEEE TIP, 2023 | [Paper](https://ieeexplore.ieee.org/document/10112639) | [Github](https://github.com/DotWang/DCN-T)
 <br><em> &ensp; &ensp; Di Wang<sup>&#8727;</sup>, Jing Zhang, Bo Du, Liangpei Zhang, and Dacheng Tao</em>
