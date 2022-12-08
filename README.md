# TAG: Boosting Text-VQA via Text-aware Visual Question-answer Generation

The code base for [TAG: Boosting Text-VQA via Text-aware Visual Question-answer Generation](https://arxiv.org/abs/2208.01813)
<br>Jun Wang, Mingfei Gao, Yuqian Hu, Ramprasaath R. Selvaraju, Chetan Ramaiah, Ran Xu, Joseph F. JaJa, Larry S. Davis


**NEWS**
- [22-09-30] 🔥 TAG is accepted at BMVC 2022.

## Abstract
<div style="text-align: justify">Text-VQA aims at answering questions that require understanding the textual cues in an image. Despite the great progress of existing Text-VQA methods, their performance suffers from insufficient human-labeled question-answer (QA) pairs. However, we observe that, in general, the scene text is not fully exploited in the existing datasets -- only a small portion of text in each image participates in the annotated QA activities. This results in a huge waste of useful information. To address this deficiency, we develop a new method to generate high-quality and diverse QA pairs by explicitly utilizing the existing rich text available in the scene context of each image. Specifically, we propose, TAG, a text-aware visual question-answer generation architecture that learns to produce meaningful, and accurate QA samples using a multimodal transformer. The architecture exploits underexplored scene text information and enhances scene understanding of Text-VQA models by combining the generated QA pairs with the initial training data. Extensive experimental results on two well-known Text-VQA benchmarks (TextVQA and ST-VQA) demonstrate that our proposed TAG effectively enlarges the training data that helps improve the Text-VQA performance without extra labeling effort. Moreover, our model outperforms state-of-the-art approaches that are pre-trained with extra large-scale data. </div>

<!-- <p>&nbsp;</p> -->

<br>![network](https://github.com/HenryJunW/TAG/blob/main/figs/TAG_overview_figure.png)
<!-- <img src="https://drive.google.com/file/d/1i3pMn_5cVaHpDTChtF41miRt1SzfAj6A/view?usp=sharing" width="600"> -->


### Features
* A generic text-aware question-answer generation approach for Text-related VQA.
* Support major Text-VQA datasets: TextVQA, ST-VQA.

## Installation

See [installation instructions](INSTALL.md).

## Getting Started

See [Getting Started with TAG](GETTING_STARTED.md).


## Model Zoo and Baselines

We provide a large set of trained models available for download in the [TAG Model Zoo](MODEL_ZOO.md).


## Citation
Please cite our work if you found it useful,

```
@inproceedings{Wang_2022_BMVC,
author    = {Jun Wang and Mingfei Gao and Yuqian Hu and Ramprasaath R. Selvaraju and Chetan Ramaiah and Ran Xu and Joseph JaJa and Larry Davis},
title     = {TAG: Boosting Text-VQA via Text-aware Visual Question-answer Generation},
booktitle = {33rd British Machine Vision Conference 2022, {BMVC} 2022, London, UK, November 21-24, 2022},
publisher = {{BMVA} Press},
year      = {2022},
url       = {https://bmvc2022.mpi-inf.mpg.de/0033.pdf}
}

```

# Acknowledgement

The source code of TAG is based on [TAP](https://github.com/microsoft/TAP) and [M4C](https://github.com/facebookresearch/mmf/tree/main/projects/m4c). 
