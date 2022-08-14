# Getting Started
Please see [Data Organization with TAP](https://github.com/microsoft/TAP) for full usage.



## Preparing Datasets for TAG

### Expected dataset structure for Text-VQA Dataset
```
TAG
├── data
│   ├── imdb
│   ├── detectron
│   ├── feat_resx
│   ├── 1600-400-20
│   ├── ocr_feat_resx
│   ├── feat_resx
│   ├── m4c_vocabs
│   ├── original_dl
```

The model configs are located within [save/exp_yaml](https://github.com/HenryJunW/TAG/blob/main/save/exp_yaml) for different models. 


### Inference with Pre-trained TAG Models

1. Pick a configuration file and its corresponding model from
  [model zoo](MODEL_ZOO.md),
  for example, the config file of ./stvqa_TAG_inference.yaml.

2. Inference with a pretrained model. Run it with:
```
python -m torch.distributed.launch --nproc_per_node $num_gpu tools/run.py --tasks vqa --datasets m4c_stvqa --model m4c_split --config save/exp_yaml/stvqa_TAG_inference.yaml --save_dir save/$refine_savedir --run_type val --resume_file save/STVQA_tag_best.ckpt training_parameters.distributed True

```
Save the corresponding QA pairs together with the originally labeled data in $save_aug_imdb_path

### Train a TAG Model
1. Pick a configuration file and its corresponding model from
  [model zoo](MODEL_ZOO.md),
  for example, the config file of ./stvqa_TAG_training.yaml.

2. Train a TAG model. Run it with:
```
python -m torch.distributed.launch --nproc_per_node $num_gpu tools/run.py --tasks vqa --datasets m4c_stvqa --model m4c_split --seed $seed --config save/exp_yaml/stvqa_TAG_training.yaml --save_dir save/$savedir training_parameters.distributed True
```

### Downstream Text-VQA Models
The generated QA pairs from TAG together with the originally labeled data
are subsequently used to train Text-VQA models, leading to better Text-VQA performance.
1. Pick a configuration file and its corresponding model from
  [model zoo](MODEL_ZOO.md),
  for example, the config file of ./stvqa_tap_w_tag_textvqa_pretrain.yaml.

2. Train a Text-VQA model with the augmented QA pairs. Run it with:
Pretrain:
```
python -m torch.distributed.launch --nproc_per_node $num_gpu tools/run.py --pretrain --tasks vqa --datasets m4c_stvqa --model m4c_split --seed $seed --config save/exp_yaml/stvqa_tap_pretrain_w_tag_textvqa.yaml --save_dir save/$pretrain_savedir training_parameters.distributed True
```
Fine-tuning:
```
python -m torch.distributed.launch --nproc_per_node $num_gpu tools/run.py --tasks vqa --datasets m4c_stvqa --model m4c_split --seed $seed --config save/exp_yaml/stvqa_tap_refine_w_tag_textvqa.yaml --save_dir save/$refine_savedir --resume_file save/$pretrain_savedir/$savename/best.ckpt training_parameters.distributed True
```

3. Evaluate a Text-VQA model. Run it with: 
```
python -m torch.distributed.launch --nproc_per_node $num_gpu tools/run.py --tasks vqa --datasets m4c_stvqa --model m4c_split --config save/exp_yaml/stvqa_tap_pretrain_w_tag_textvqa.yaml --save_dir save/$refine_savedir --run_type val --resume_file save/$refine_savedir/$savename/best.ckpt training_parameters.distributed True
```