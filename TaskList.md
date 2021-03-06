## 09.25 ~ 09.30

- 任务:   
  
    调研目前能够实现Image Style Transfer的技术，比如Transfer Learning，Neural Style Transfer.

    尝试对能够实现Image Style Transfer功能(特别针对路况图片，比如白天转换成晚上)的技术进行分类，并找出每一类中具有代表性的Framework.

- Reference Readings
    - [Neural Style Transfer: A Review](https://arxiv.org/abs/1705.04058)
    - [Deep Photo Style Transfer](http://openaccess.thecvf.com/content_cvpr_2017/papers/Luan_Deep_Photo_Style_CVPR_2017_paper.pdf)
    - 请添加

## 10.08

- style images数据集
    - [Berkeley-DeepDrive](http://bdd-data.berkeley.edu/portal.html#download) - \[local path\](/home/sway007/datasets/bdd100k)
    - [OXFORD ROBOTCAR DATASET](http://robotcar-dataset.robots.ox.ac.uk/) - \[local path\](/home/sway007/datasets/Images_Oxford_Sun)  
    `symlink->/home/undergrats/ywCHENG/Images_Oxford_Sun`

    上周CycleGAN和Deep Nerual Transfer的实验结果都不太好，猜测可能由于Style Image Datasets质量不高的原因导致，所以已经在服务器上下载了Berkeley-DeepDrive和OXFORD ROBOTCAR DATASET数据集，以后实验确定content image用udacity数据集，style image采用上面两个数据集的数据。

-------------------

## Remark

- CycleGAN也能实现Image Style Transfer
- [fast-neural-style](https://github.com/jcjohnson/fast-neural-style)

## 11.25

因为近期要对实验进行项目中期总结，所以咱们需要整理、展示一下跑过的几个model的合成图片效果。之前我们提出了3个framework的比较维度:fid, steering angle diff和traning time，因为后面跑的几个model没有训练的环节，所以我们现在重点考虑fid和steering angle diff。  
- 算fid的代码:[github_link](https://github.com/mseitzer/pytorch-fid)，这个yiwei和铭基已经跑过了，比较简单，大家有疑问可以问一下他俩，唯一需要注意的是为了统一比较标准，所有model的content image定位server上路径为`/home/sway007/datasets/udacity_day`的数据集，简单来说就是大家把之前跑过的model再以`/home/sway007/datasets/udacity_day`为content image跑一遍(style images以自己跑过的效果最好的图片为准)，然后拿到最新合成的图片算出和数据集`/home/sway007/datasets/udacity_day`之间的fid值。
