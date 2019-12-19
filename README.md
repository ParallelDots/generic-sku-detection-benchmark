# Generic Product detection in retail environments.

> **Benchmark for Generic Product Detection: A strong baseline for Dense Object Detection**
> Srikrishna Varadarajan, Sonaal Kant, Muktabh Mayank Srivastava
> [Paper link](coming.soon)

## Abstract
Object detection in densely packed scenes is a new area where standard object detectors fail to train well [1].  We show that the performance of the standard object detectors on densely packed scenes is superior when it is trained on normal scenes rather than dense scenes.  We train a standard object detector on a small, normally packed dataset with data augmentation techniques.  This achieves significantly better results than state-of-the-art methods which are trained on densely packed scenes. We also create a varied benchmark for generic SKU product detection by providing full annotations for multiple public datasets. We hope that this benchmark helps in building robust detectors which perform reliably across different settings.



## Benchmark Datasets

The images of these datasets can be obtained from their original websites (link provided in the table). The annotations for generic product detection is provided in this repository under the folder `annotations`. 

The `WebMarket`, `GP` datasets were annotated entirely by us. The missing generic product annotations of `CAPG-GP` were added by us. The annotations of `Holoselecta`, `TobaccoShelves` were converted from their original formats to suit the standard evaluation code. The authors can let us know if they do not wish to make the annotations available here.

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

| Dataset        | Method                        | AP        | AP<sup>$.50$</sup> | AP<sup>$.75$</sup> | AR<sub>$300$</sub> | AR<sup>$.50$</sup><sub>$300$</sub> |
| -------------- | ----------------------------- | --------- | ------------------ | ------------------ | ------------------ | ---------------------------------- |
| SKU110K-Test   | RetinaNet [1]                 | 0.455     | -                  | 0.389              | 0.530              | -                                  |
|                | Full Approach (RetinaNet) [1] | 0.492     | -                  | 0.556              | 0.554              | -                                  |
|                | Faster-RCNN [1]               | 0.045     | -                  | 0.010              | 0.066              | -                                  |
|                | Faster-RCNN (ours)            | **0.685** | 0.827              | **0.755**          | **0.756**          | 0.855                              |
| WebMarket      | Faster-RCNN (ours)            | 0.597     | 0.754              | 0.661              | 0.677              | 0.785                              |
| TobaccoShelves | Faster-RCNN (ours)            | 0.436     | 0.569              | 0.523              | 0.474              | 0.576                              |
| Holoselecta    | Faster-RCNN (ours)            | 0.661     | 0.853              | 0.765              | 0.769              | 0.905                              |
| GP             | Faster-RCNN (ours)            | 0.537     | 0.792              | 0.604              | 0.656              | 0.879                              |
| CAPG-GP        | Faster-RCNN (ours)            | 0.648     | 0.900              | 0.749              | 0.760              | 0.955                              |



## References

>  [1] Precise Detection in Densely Packed Scenes, CVPR 2019



## Citation

If you found this work useful, please consider citing our paper

> coming soon

Also, do consider citing the corresponding datasets as well

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

