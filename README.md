# :cherry_blossom: Semantic segmentation on 360° images :cherry_blossom:



### :tea: Model yolact(4th experiment_120) 665ba25f92424b03aa8265cd9cedb76f.png 




#


## :floppy_disk: Dataset :

<details>
  <summary> notes : </summary>
  1. From lableme to coco : [This github](https://github.com/Tony607/labelme2coco.git)
  2. From mask to polygon : Inspire from [here](https://github.com/cocodataset/cocoapi/issues/131)
</details>

The dataset is put in folder : `/smarterplan-mtf/indoor_trainR_valR/`
- `trainR/images/` : all the training images
- `trainR/trainval.json` : the json file of annotation(training)
- `valR/images/` : all the validation images
- `valR/trainval.json` : the json file of annotation(validation)

## :computer: Training :
<details>
  <summary> notes : </summary>
  1. Finetune : Please look [here](https://github.com/dbolya/yolact/issues/36)
</details>

1. Change the config in file : `/smarterplan-mtf/yolact/data/config.py`

2. run `/smarterplan-mtf/yolact/train.py`
```
python train.py --config=yolact_resnet101_indoor1216R_all4_add_config --batch_size=3
```

## :clipboard: Validation :
1. Plot images of mask and bounding box
```
python val.py --config=yolact_resnet101_indoor1216R_all4_add_config --top_k=35 --images=test_images:output
```

The output will be plotted in folder `output`.

2. Output file json :
```
python val_output.py --config=yolact_resnet101_indoor1216R_all4_add_config --top_k=35 --images=test_images:output
```

## :bulb: Summary

`Yolact_summary.pdf` contains summary of the 4 experiments using yolact and dataset trainR, valR on 34 classes(35 classes with background). 

## :doughnut: link
- [GitHub official Yolact](https://github.com/dbolya/yolact)
- [Gitlab Smarterplan for Yolact](https://gitlab.com/thai-binh.phan/smarterplan-mtf/-/tree/yolact/)
