:tada: # Detection on 360° images

---


<p align="center"> :rocket: Model yolact(4th experiment_120), 665ba25f92424b03aa8265cd9cedb76f.jpg
</p>

---

## :package: Dataset :

The dataset is put in folder : `/smarterplan-mtf/indoor_trainR_valR/`
- `trainR/images/` : all the training images
- `trainR/trainval.json` : the json file of annotation(training)
- `valR/images/` : all the validation images
- `valR/trainval.json` : the json file of annotation(validation)

## :construction: Training :

1. Change the config in file : `/smarterplan-mtf/yolact/data/config.py`

2. run `/smarterplan-mtf/yolact/train.py`
```
python train.py --config=yolact_resnet101_indoor1216R_all4_add_config --batch_size=3
```

## :white_check_mark: Validation :
1. Plot images of mask and bounding box
```
python val.py --config=yolact_resnet101_indoor1216R_all4_add_config --top_k=35 --images=test_images:output
```

The output will be plotted in folder `output`.

2. Output file json :
```
python val_output.py --config=yolact_resnet101_indoor1216R_all4_add_config --top_k=35 --images=test_images:output
```

## :pencil: Summary

`Yolact_summary` contains summary of the 4 experiments using yolact and dataset trainR, valR on 34 classes(35 classes with background). 
