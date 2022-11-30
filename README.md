## The update is expected to be completed before Dec.  
## The overall structure has been slightly changed.  
## To be uploaded along with the paper of the changed structure.  

## Hierarchical-Attention-Network-for-Few-Shot-Object-Detection-Via-Meta-Contrastive-Learning
![Picture1](https://user-images.githubusercontent.com/59869350/179343518-7ae94313-66e6-45a7-b5e2-f57a2c069827.png)


## Introduction
This repo contains the official PyTorch implementation of our proposed methods Hierarchical Attention Network for Few-Shot Object Detection Via Meta-Contrastive Learning.
This repo is built upon DAnA.

## Updates
[2022/07/01] We release the official PyTorch implementation of hANMCL.  
[2022/09/21] Support Pascal VOC and MS-COCO datasets.  
[2022/11/30] Support Multi-GPU training, fine-tuning, and . 

## Requirements
<pre><code>Linux with Python == 3.7.0
PyTorch == 1.8.0+cu111
Torchvision == 0.9.0+cu111
CUDA 11.3
GCC == 7.5.0</code></pre>

## Getting Started
<pre><code>git clone https://github.com/infinity7428/hANMCL.git</code></pre>

## Compile COCO API
<pre><code>$ cd lib
$ git clone https://github.com/pdollar/coco.git 
$ cd coco/PythonAPI
$ make && make install</code></pre>


## Build hANIMAL
<pre><code>cd lib
python setup.py build develop</code></pre>

## Datasets
<pre><code>Pascal VOC(07,12)
> data/voc/images/train2014
> data/voc/annotations/voc_train
https://drive.google.com/drive/folders/1K94ot7sBrChubmUA8HK0ym_7QT-ZG4su?usp=sharing

MS-COCO
> data/coco/images/train2014
> data/coco/annotations/coco60_train

60 base classes for training (https://drive.google.com/file/d/10mXvdpgSjFYML_9J-zMDLPuBYrSrG2ub/view?usp=sharing)
20 novel classes for testing (https://drive.google.com/file/d/1FZJhC-Ob-IXTKf5heNeNAN00V8OUJXi2/view?usp=sharing)
Reference : https://github.com/Tung-I/Dual-awareness-Attention-for-Few-shot-Object-Detection

</code></pre>

## Train
<pre><code>python train.py --dataset coco_base --flip --net hanmcl --lr 0.001 --lr_decay_step 12 --bs 4 --epochs 12 --disp_interval 20 --save_dir models/hanmcl --way 2 --shot 3</code></pre>

## for Multi-GPU Train
<pre><code></code></pre>

## Inference
<pre><code>python inference.py --eval --dataset val2014_novel --net hanmcl --r --load_dir models/hanmcl --checkepoch 12 --checkpoint 34467 --bs 1 --shot 3 --eval_dir result</code></pre>

## Pretrained Weights
path: models/hanmcl/train/checkpoints/model_12_34467.pth  
link: https://drive.google.com/drive/folders/1sPiadJ-Aw5N9uFaR1lTS2qlx3ABUudXh?usp=sharing

## Results on Pascal VOC dataset(AP<sub>50</sub>)
<pre><code></code></pre>

## Results on COCO dataset(nAP)

## Result on Zero-shot Evaluation(nAP)

## Results on Cross-Domain Few-Shot Object Detection(nAP)
