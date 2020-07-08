
# QTool: A low bit quantization toolbox for computer vision neural networks

This project provides aboundant choices of quantization strategies (such as the quantization algoirthms, training schedules and empirical tricks) for quantizing the image classification neural networks into low bit counterparts. Associated projects demonstrate that this project can also benefit other computer vision tasks, such as object detection, segmentation and text parsing. Pretrained models are provided to show high standard of the code on achiving appealing quantization performance. 

## Quantization result

- [Classification](./doc/result_cls.md)

### Detection

Selected results are listed in the following table. More data and detailed instructions can be found in [detection.md](./doc/detection.md)

Dataset | Task Method | Quantization method | Model | A/W | Reported | AP  | Comment 
--- |:---:|:---:|:---:|:---:|:---:|:---:|:---:
COCO | Retina-Net | - | Torch-18 | 32/32 | - | 31.5 | 1x
COCO | Retina-Net | - | Torch-18 | 32/32 | - | 32.8 | 1x, FPN-BN,Head-GN
COCO | Retina-Net | - | Torch-18 | 32/32 | - | 33.0 | 1x, FPN-BN,Head-BN
COCO | Retina-Net | - | Torch-34 | 32/32 | - | 35.2 | 1x
COCO | Retina-Net | - | Torch-50 | 32/32 | - | 36.6 | 1x
COCO | Retina-Net | - | Torch-50 | 32/32 | - | 37.8 | 1x, FPN-BN,Head-BN
COCO | Retina-Net | - | MSRA-R50 | 32/32 | - | 36.4 | 1x
COCO | FCOS | - | MSRA-R50 | 32/32 | - | 38.6 | 1x
COCO | FCOS | - | Torch-50 | 32/32 | - | 38.4 | 1x
COCO | FCOS | - | Torch-50 | 32/32 | - | 38.5 | 1x,FPN-BN
COCO | FCOS | - | Torch-50 | 32/32 | - | 38.9 | 1x,FPN-BN,Head-BN
COCO | FCOS | - | Torch-34 | 32/32 | - | 37.3 | 1x
COCO | FCOS | - | Torch-18 | 32/32 | - | 32.2 | 1x
COCO | FCOS | - | Torch-18 | 32/32 | - | 33.4 | 1x,FPN-BN
COCO | FCOS | - | Torch-18 | 32/32 | - | 33.9 | 1x,FPN-BN, FP16
COCO | FCOS | - | Torch-18 | 32/32 | - | 33.9 | 1x,FPN-BN,Head-BN
COCO | FCOS | - | Torch-18 | 32/32 | - | 34.3 | 1x,FPN-SyncBN,Head-SyncBN
COCO | FCOS | Dorefa-Net | Torch-18 | 2/2 | - | 33.4 | 1x,FPN-BN, Quantize-Backbone
COCO | FCOS | Dorefa-Net | Torch-18 | 2/2 | - | 30.3 | 1x,FPN-BN, Quantize-All
COCO | FCOS | LQ-Net | Torch-18 | ter/ter | - | 32.6 | 1x,FPN-BN, Quantize-Backbone
COCO | FCOS | LQ-Net | Torch-18 | ter/ter | - | 26.2 | 1x,FPN-BN, Quantize-All

Above experiments conducted in 2020 Q1, performance might be better by the newest code. See [detection.md](./doc/detection.md).

### Segmentation

Selected results are listed in the following table. More data and detailed instructions can be found in [detection.md](./doc/detection.md).

Dataset | Task Method | Quantization method | Model | A/W | Reported | seg AP  | Comment 
--- |:---:|:---:|:---:|:---:|:---:|:---:|:---:
COCO | Mask-RCNN | - | Torch-18 | 32/32 | - | 31.4 | 1x FP16
COCO | BlendMask | - | Torch-18 | 32/32 | - | 29.7 | 550-R-18-aux-1x-FPN-BN,FP16
COCO | BlendMask | - | Torch-50 | 32/32 | - | 33.9 | 550-R-50-aux-1x,FP16
COCO | BlendMask | - | Torch-50 | 32/32 | - | 36.1 | 550-R-50-aux-3x,FP16

Above experiments conducted in 2020 Q1, performance might be better by the newest code. See [detection.md](./doc/detection.md).

### Text parsing

in progress

## Update History

- Super Resolution (preparing)
- Text parsing (preparing)
- Instance Segmentation (preparing)
- Object Detection (preparing)
- 2020.06.23 Add classification quantization



## Algorithms

Please cite if you use this method

1. LQnet:
```BibTeX
@inproceedings{zhang2018lq,
  title={LQ-Nets: Learned Quantization for Highly Accurate and Compact Deep Neural Networks},
    author={Zhang, Dongqing and Yang, Jiaolong and Ye, Dongqiangzi and Hua, Gang},
      booktitle=ECCV,
        year={2018}
}
```

2. Dorefa-net

```BibTeX
@article{zhou2016dorefa,
	title={DoReFa-Net: Training low bitwidth convolutional neural networks with low bitwidth gradients},
	author={Zhou, Shuchang and Wu, Yuxin and Ni, Zekun and Zhou, Xinyu and Wen, He and Zou, Yuheng},
	journal={arXiv preprint arXiv:1606.06160},
	year={2016}
}
```

3. PACT

```BibTeX
@article{choi2018pact,
  title={Pact: Parameterized clipping activation for quantized neural networks},
  author={Choi, Jungwook and Wang, Zhuo and Venkataramani, Swagath and Chuang, Pierce I-Jen and Srinivasan, Vijayalakshmi and Gopalakrishnan, Kailash},
  journal={arXiv preprint arXiv:1805.06085},
  year={2018}
}
```

4. LSQ / TET
```BibTeX
@inproceedings{esser2019learned,
  title={Learned step size quantization},
  author={Esser, Steven K and McKinstry, Jeffrey L and Bablani, Deepika and Appuswamy, Rathinakumar and Modha, Dharmendra S},
  booktitle=ICLR,
  year=2020
}

@misc{jin2019efficient,
    title={Towards Efficient Training for Neural Network Quantization},
    author={Qing Jin and Linjie Yang and Zhenyu Liao},
    year={2019},
    eprint={1912.10207},
    archivePrefix={arXiv},
    primaryClass={cs.CV}
}
```

5. Xnor-Net / Xnor-Net++

```BibTeX
% XNOR-net
@inproceedings{rastegari2016xnor,
	title={Xnor-net: Imagenet classification using binary convolutional neural networks},
	author={Rastegari, Mohammad and Ordonez, Vicente and Redmon, Joseph and Farhadi, Ali},
	booktitle=ECCV,
	pages={525--542},
	year={2016}
}

@misc{bulat2019xnornet,
    title={XNOR-Net++: Improved Binary Neural Networks},
    author={Adrian Bulat and Georgios Tzimiropoulos},
    year={2019},
    eprint={1909.13863},
    archivePrefix={arXiv},
    primaryClass={cs.CV}
}
```

6. Bi-Real Net

```BibTeX
@article{liu2018bi,
  title={Bi-Real Net: Binarizing Deep Network Towards Real-Network Performance},
  author={Liu, Zechun and Luo, Wenhan and Wu, Baoyuan and Yang, Xin and Liu, Wei and Cheng, Kwang-Ting},
  journal={arXiv preprint arXiv:1811.01335},
  year={2018}
}
```

7. Group-Net

```BibTeX
@inproceedings{zhuang2019structured,
  title={Structured Binary Neural Network for Accurate Image Classification and Semantic Segmentation},
  author={Zhuang, Bohan and Shen, Chunhua and Tan, Mingkui and Liu, Lingqiao and Reid, Ian},
  booktitle=CVPR,
  year={2019}
}
```

8. TResnet (The work is not quantization oriented, but might insipre efficent inference)

```BibTeX
@misc{ridnik2020tresnet,
    title={TResNet: High Performance GPU-Dedicated Architecture},
    author={Tal Ridnik and Hussam Lawen and Asaf Noy and Itamar Friedman and Emanuel Ben Baruch and Gilad Sharir},
    year={2020},
    eprint={2003.13630},
    archivePrefix={arXiv},
    primaryClass={cs.CV}
}
```

9. Fixup Initilization / Mixup (The work is not quantization oriented, but might insipre quantization in specific tasks)

```BibTeX
@misc{zhang2019fixup,
    title={Fixup Initialization: Residual Learning Without Normalization},
    author={Hongyi Zhang and Yann N. Dauphin and Tengyu Ma},
    year={2019},
    eprint={1901.09321},
    archivePrefix={arXiv},
    primaryClass={cs.LG}
}

@misc{zhang2017mixup,
    title={mixup: Beyond Empirical Risk Minimization},
    author={Hongyi Zhang and Moustapha Cisse and Yann N. Dauphin and David Lopez-Paz},
    year={2017},
    eprint={1710.09412},
    archivePrefix={arXiv},
    primaryClass={cs.LG}
}
```


## Contributors

Current Contributors:

- [Blueardour](https://github.com/blueardour)
- [bohanzhuang](https://github.com/bohanzhuang)
- [liujingcs](https://github.com/liujingcs)
- [liuchunlei0430](https://github.com/liuchunlei0430)


To contribute, PR is appreciated and suggestions are welcome to discuss. Private conact is available at blueardour@gmail.com

## License

For academic use, this project is licensed under the 2-clause BSD License. See LICENSE file.

