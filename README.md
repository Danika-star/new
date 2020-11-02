# Dataset :

The dataset is put in folder : ```/smarterplan-mtf/indoor_trainR_valR/```
- ```trainR/images/``` : all the training images
- ```trainR/trainval.json``` : the json file of annotation(training)
- ```valR/images/``` : all the validation images
- ```valR/trainval.json``` : the json file of annotation(validation)

# Training :

1. Change the config in file : ```/smarterplan-mtf/yolact/data/config.py```

2. run ```/smarterplan-mtf/yolact/train.py``` by :
```
python train.py --config=yolact_resnet101_indoor1216R_all4_add_config --batch_size=3
```

# Validation :
1. Plot images of mask and bounding box
```
python val.py --config=yolact_resnet101_indoor1216R_all4_add_config --top_k=60 --images=test_images:output
```

The output will be plotted in folder ```output```.

2. Output file json :
```
python val_output.py --config=yolact_resnet101_indoor1216R_all4_add_config --top_k=35 --images=test_images:output
```
