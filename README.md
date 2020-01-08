# Generic Product detection in retail environments.

> **Benchmark for Generic Product Detection: A Low Data Baseline for Dense Object Detection**  
> Srikrishna Varadarajan, Sonaal Kant, Muktabh Mayank Srivastava  
> [Paper link](https://arxiv.org/abs/1912.09476)

## Abstract
Object detection in densely packed scenes is a new area where standard object detectors fail to train well. Dense object detectors like RetinaNet trained on large and dense datasets show great performance. We train a standard object detector on a small, normally packed dataset with data augmentation techniques. This dataset is 265 times smaller than the standard dataset, in terms of number of annotations. This low data baseline achieves satisfactory results (mAP=0.56) at standard IoU of 0.5. We also create a varied benchmark for generic SKU product detection by providing full annotations for multiple public datasets. We hope that this benchmark helps in building robust detectors that perform reliably across different settings in the wild.

## Approach

| Dataset       | #Images | #Obj/Img | #Anns   |
|---------------|---------|----------|---------|
| Our trainset  | 312     | 14.6     | 4556    |
| SKU110K-train | 8233    | 147.4    | 1,210,431 |

We explore the effectiveness of standard object detectors, trained on very low data. Our training data is 265 times smaller than the standard dataset, in terms of number of annotations. For more details, please checkout the [paper](https://arxiv.org/abs/1912.09476). 


## Benchmark Datasets

The images of these datasets can be obtained from their original websites (link provided in the table). The annotations for generic product detection is provided in this repository under the folder `annotations`. 

The `WebMarket`, `GP` datasets were annotated entirely by us. The missing generic product annotations of `CAPG-GP` were added by us. The annotations of `Holoselecta`, `TobaccoShelves` were converted from their original formats to suit the standard evaluation code. The authors can let us know if they do not wish to make the annotations available here.

Feel free to reach out if you have any doubts, feedback, thoughts or constructive criticism :)

| Dataset                                                      | Annotations                                               | #Images | #Objects | #Obj/Img |
| ------------------------------------------------------------ | --------------------------------------------------------- | ------- | -------- | -------- |
| [SKU110K-Test](https://github.com/eg4000/SKU110K_CVPR19)     | [Their webpage](https://github.com/eg4000/SKU110K_CVPR19) | 2941    | 432,312  | 146      |
| [WebMarket](http://yuhang.rsise.anu.edu.au/)                 | This repo                                                 | 3153    | 118,388  | 37       |
| [TobaccoShelves](https://github.com/gulvarol/grocerydataset) | This repo                                                 | 354     | 13,184   | 37       |
| [Holoselecta](https://www.autoidlabs.ch/ai-support/holoselecta/) | This repo                                             | 295     | 10,036   | 34       |
| [GP](https://sites.google.com/view/mariangeorge/datasets)    | This repo                                                 | 680     | 9184     | 13       |
| [CAPG-GP](http://zju-capg.org/capg-gp.html)                  | This repo                                                 | 234     | 4756     | 20       |

## Evaluation code

The evaluation code can be accessed from this [repository](https://github.com/skrish13/SKU110K-evaluation).

## Leaderboard

We welcome the community to report results on this benchmark. Please open an issue with your output files and a brief description of your method. We provide the predictions of our method in this repository under the folder `predictions`

| Dataset        | Method                        | AP        | AP<sup>.50</sup> | AP<sup>.75</sup> | AR<sub>300</sub> | AR<sup>.50</sup><sub>300</sub> |
| -------------- | ----------------------------- | --------- | ------------------ | ------------------ | ------------------ | ---------------------------------- |
| SKU110K-Test   | RetinaNet [1]                 | 0.455     | -                  | 0.389              | 0.530              | -                                  |
|                | Full Approach (RetinaNet) [1] | 0.492     | -                  | 0.556              | 0.554              | -                                  |
|                | Full Approach* [3]            | 0.514     | 0.853              | 0.569              | 0.571              | 0.872                              |
|                | Faster-RCNN [1]               | 0.045     | -                  | 0.010              | 0.066              | -                                  |
|                | *LDB300* [2]                  | 0.186     | 0.560              | 0.052              | 0.264              | 0.647                              |
|                | ShelfWise v1 [4]              | 0.529     | 0.892              | 0.583              | 0.598              | 0.926                              |
| WebMarket      | *LDB300* [2]                  | 0.322     | 0.621              | 0.248              | 0.455              | 0.684                              |
| TobaccoShelves | *LDB300* [2]                  | 0.108     | 0.442              | 0.009              | 0.159              | 0.491                              |
| Holoselecta    | *LDB300* [2]                  | 0.239     | 0.707              | 0.072              | 0.347              | 0.816                              |
| GP             | *LDB300* [2]                  | 0.234     | 0.596              | 0.125              | 0.334              | 0.713                              |
| CAPG-GP        | *LDB300* [2]                  | 0.312     | 0.745              | 0.169              | 0.434              | 0.895                              |

## License

The annotations provided here are strictly for research purposes only and cannot be used for commercial purposes. The licenses of individual datasets can be found in their respective websites. 

## References

> [1] Precise Detection in Densely Packed Scenes, CVPR 2019  
> [2] https://arxiv.org/abs/1912.09476  
> [3] https://github.com/eg4000/SKU110K_CVPR19/issues/9  
> [4] https://github.com/ParallelDots/generic-sku-detection-benchmark/issues/3  

## Citation

If you found this work useful, please consider citing our paper and the corresponding datasets as well.

> ```
> @misc{varadarajan2019benchmark,
>     title={Benchmark for Generic Product Detection: A Low Data Baseline for Dense Object Detection},
>     author={Srikrishna Varadarajan and Sonaal Kant and Muktabh Mayank Srivastava},
>     year={2019},
>     eprint={1912.09476},
>     archivePrefix={arXiv},
>     primaryClass={cs.CV}
> }
> ```
> 

#### SKU110K

> ```
> @inproceedings{goldman2019dense,
>  author    = {Eran Goldman and Roei Herzig and Aviv Eisenschtat and Jacob Goldberger and Tal Hassner},
>  title     = {Precise Detection in Densely Packed Scenes},
>  booktitle = {Proc. Conf. Comput. Vision Pattern Recognition (CVPR)},
>  year      = {2019}
> }
> ```
> 

#### WebMarket

>```
>@inproceedings{Zhang:2007:WW:1775614.1775708,
> author = {Zhang, Yuhang and Wang, Lei and Hartley, Richard and Li, Hongdong},
> title = {Where's the Weet-bix?},
> booktitle = {Proceedings of the 8th Asian Conference on Computer Vision - Volume Part I},
> series = {ACCV'07},
> year = {2007},
> isbn = {3-540-76385-6, 978-3-540-76385-7},
> location = {Tokyo, Japan},
> pages = {800--810},
> numpages = {11},
> url = {http://dl.acm.org/citation.cfm?id=1775614.1775708},
> acmid = {1775708},
> publisher = {Springer-Verlag},
> address = {Berlin, Heidelberg},
>}
>```

#### TobaccoShelves
>```
> @inproceedings{10.1117/12.2179127,
> author = {Gül Varol and Rıdvan Salih Kuzu},
> title = {{Toward retail product recognition on grocery shelves}},
> volume = {9443},
> booktitle = {Sixth International Conference on Graphic and Image Processing (ICGIP 2014)},
> editor = {Yulin Wang and Xudong Jiang and David Zhang},
> organization = {International Society for Optics and Photonics},
> publisher = {SPIE},
> pages = {46 -- 52},
> keywords = {object recognition, object detection, retail product, grocery image, bag of words},
> year = {2015},
> doi = {10.1117/12.2179127},
> URL = {https://doi.org/10.1117/12.2179127}
> }
>```
#### Holoselecta

>```
>@inproceedings{Fuchs:2019:TIP:3365871.3365899,
> author = {Fuchs, Klaus and Grundmann, Tobias and Fleisch, Elgar},
> title = {Towards Identification of Packaged Products via Computer Vision: Convolutional Neural Networks for Object Detection and Image Classification in Retail Environments},
> booktitle = {Proceedings of the 9th International Conference on the Internet of Things},
> series = {IoT 2019},
> year = {2019},
> isbn = {978-1-4503-7207-7},
> location = {Bilbao, Spain},
> pages = {26:1--26:8},
> articleno = {26},
> numpages = {8},
> url = {http://doi.acm.org/10.1145/3365871.3365899},
> doi = {10.1145/3365871.3365899},
> acmid = {3365899},
> publisher = {ACM},
> address = {New York, NY, USA},
> keywords = {CNN, Computer vision, Product identification},
>} 
>```

#### GP
>```
>@InProceedings{10.1007/978-3-319-10605-2_29,
>author="George, Marian
>and Floerkemeier, Christian",
>editor="Fleet, David
>and Pajdla, Tomas
>and Schiele, Bernt
>and Tuytelaars, Tinne",
>title="Recognizing Products: A Per-exemplar Multi-label Image Classification Approach",
>booktitle="Computer Vision -- ECCV 2014",
>year="2014",
>publisher="Springer International Publishing",
>address="Cham",
>pages="440--455",
>isbn="978-3-319-10605-2"
>}
>```
#### CAPG-GP

>```
>@inproceedings{Geng:2018:FGP:3240508.3240522,
> author = {Geng, Weidong and Han, Feilin and Lin, Jiangke and Zhu, Liuyi and Bai, Jieming and Wang, Suzhen and He, Lin and Xiao, Qiang and Lai, Zhangjiong},
> title = {Fine-Grained Grocery Product Recognition by One-Shot Learning},
> booktitle = {Proceedings of the 26th ACM International Conference on Multimedia},
> series = {MM '18},
> year = {2018},
> isbn = {978-1-4503-5665-7},
> location = {Seoul, Republic of Korea},
> pages = {1706--1714},
> numpages = {9},
> url = {http://doi.acm.org/10.1145/3240508.3240522},
> doi = {10.1145/3240508.3240522},
> acmid = {3240522},
> publisher = {ACM},
> address = {New York, NY, USA},
> keywords = {fine-grained object recognition, product categorization},
>} 
>```

