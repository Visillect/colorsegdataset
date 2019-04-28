# A benchmark dataset for color segmentation

This repository contains color images of natural scenes with non-overdetailed objects together with pixel-by-pixel color-based segmentation annotations.
The dataset consists of 3 distinct parts (sub-datasets), any of which fully acquired with the use of a single camera sensor:

* Selected-SFU
* IITP-close
* IITP-diffuse

## Images

### Selected-SFU 

19 637x468 pixels images of natural scenes selected from [Barnard's DXC-930 SFU dataset](http://www.cs.sfu.ca/~colour/data/colour_constancy_test_images/index.html) for colour research. 
In the original dataset each scene is taken under 11 different close light sources. 
Here scenes under Philips Ultralume were chosen. 
Among chosen scenes 17 images contain flat varied in colour sheets of paper (so-called "mondrians"), 5 images contain volumetric objects without or with insignificant highlights, on 2 more images volumetric objects with highlights and  inter-reflection effects are depicted. For all images linear contrast adjustment with 95% quantile was applied, 5% of pixels were allowed to be saturated.

<img height="500px" width="840px" align="center" src="https://github.com/Visillect/colorsegdataset/blob/master/Selected-SFU/preview.png">

### IITP-close and IITP-diffuse 

The second and the third parts of the dataset consist of natural scene images taken at IITP RAS.
There are 5 about 450x500 images of scenes with close light source and 7 1280x1024 images of scenes with diffuse light source . The camera model for *IITP-close* is  unfortunatelly unknown. Images from *IITP-diffuse* sub-dataset was taken with Olympus D600L camera. All images contain volumetric objects, some of which with highlights, but with no inter-reflection effects.   

<img height="160px" width="840px" align="center" src="https://github.com/Visillect/colorsegdataset/blob/master/IITP-close/preview.png">

<img height="337px" width="840px" align="center" src="https://github.com/Visillect/colorsegdataset/blob/master/IITP-diffuse/preview.png">

## Ground truth

For annotation purposes, images were first automatically splitted into small subregions with guaranteed colour constancy, and then are manually merged if their colours were undistinguished by a human eye.
Segments containing less than 20 pixels were not annotated. 
In addition, annotations for regions corresponding to deep shadows (i.e. with average brightness close to zero) were provided. Such regions appears at *Selected-SFU* images containing volumetric objects. Information about colour in such regions is lost and can not be recovered. Annotation for each shadow segment is provided as a separate binary mask.

## License & citation

The dataset is licensed under Apache 2.0, quoted below.

    Copyright 2018 Visillect Service LLC
    Developed for Kharkevich Institute for Information Transmission Problems of the Russian Academy of Sciences (IITP RAS)
    
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
    
      http://www.apache.org/licenses/LICENSE-2.0
    
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

If you use this dataset, please cite the following for Selected-SFU subdataset:

    @article{barnard2002data,
        title={A data set for color research},
        author={Barnard, Kobus and Martin, Lindsay and Funt, Brian and Coath, Adam},
        journal={Color Research \& Application: Endorsed by Inter-Society Color Council, The Colour Group (Great Britain), Canadian Society for Color, Color Science Association of Japan, Dutch Society for the Study of Color, The Swedish Colour Centre Foundation, Colour Society of Australia, Centre Fran{\c{c}}ais de la Couleur},
        volume={27},
        number={3},
        pages={147--151},
        year={2002},
        publisher={Wiley Online Library}
    }

## Acknowledgements

Thanks to Dr. Pavel Chochia for dataset images collected at IITP RAS.

Sincere gratitude to Dmitry Sidorchuk for technical help.
