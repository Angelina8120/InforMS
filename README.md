# Informative Classes Matter: Towards Unsupervised Domain Adaptive Nighttime Semantic Segmentation

## Setup Environment
The code is run with Python 3.8.13. To install the packages, use:
```bash
pip install -r requirements.txt
```
### Set Data Directory

The following environment variable must be set:
```bash
export DATA_DIR=/path/to/data/dir
```

## Setup Datasets
<details>
  <summary>Cityscapes</summary>
  
  Please, download leftImg8bit_trainvaltest.zip and gt_trainvaltest.zip from [here](https://www.cityscapes-dataset.com/downloads/) and extract them to `$DATA_DIR/Cityscapes`.

  ```
  $DATA_DIR
  ├── Cityscapes
  │   ├── leftImg8bit
  │   │   ├── train
  │   │   ├── val
  │   ├── gtFine
  │   │   ├── train
  │   │   ├── val
  ├── ...
  ```
</details>

<details>
  <summary>ACDC</summary>
  
  Please, download rgb_anon_trainvaltest.zip and gt_trainval.zip from [here](https://acdc.vision.ee.ethz.ch/download) and extract them to `$DATA_DIR/ACDC`.

  ```
  $DATA_DIR
  ├── ACDC
  │   ├── rgb_anon_trainvaltest
  │   │   ├── rgb_anon
  │   │   │   ├── fog
  │   │   │   ├── night
  │   │   │   ├── rain
  │   │   │   ├── snow
  │   ├── gt_trainval
  │   │   ├── gt
  │   │   │   ├── fog
  │   │   │   ├── night
  │   │   │   ├── rain
  │   │   │   ├── snow
  ├── ...
  ```
</details>

<details>
  <summary>Dark Zurich</summary>
  
  Please, download the Dark_Zurich_train_anon.zip, Dark_Zurich_val_anon.zip, and Dark_Zurich_test_anon_withoutGt.zip from [here](https://www.trace.ethz.ch/publications/2019/GCMA_UIoU/) and extract them to `$DATA_DIR/DarkZurich`.

  ```
  $DATA_DIR
  ├── DarkZurich
  │   ├── rgb_anon
  │   │   ├── train
  │   │   ├── val
  │   │   ├── val_ref
  │   │   ├── test
  │   │   ├── test_ref
  │   ├── gt
  │   │   ├── val
  ├── ...
  ```
</details>

<details>
  <summary>Nighttime Driving</summary>
  
  Please, download the NighttimeDrivingTest.zip from [here](http://data.vision.ee.ethz.ch/daid/NighttimeDriving/NighttimeDrivingTest.zip) and extract it to `$DATA_DIR/NighttimeDrivingTest`.


  ```
  $DATA_DIR
  ├── NighttimeDrivingTest
  │   ├── leftImg8bit
  │   │   ├── test
  │   ├── gtCoarse_daytime_trainvaltest
  │   │   ├── test
  ├── ...
  ```
</details>

## Training
Awaiting soon...

## Testing
Awaiting soon...

## Results
To facilitate qualitative segmentation comparisons, validation set predictions of InforMS can be directly downloaded.

| Model         | Task           | Test Set       | Test Score    | Predictions  |
|---------------|----------------|-----------------|-----------------|------------|
| Refign-DeepLabv2 | Cityscapes→ACDC | ACDC-night-test | 51.7 mIoU | [ACDC-night-val]() 
| Refign-DAFormer | Cityscapes→ACDC | ACDC-night-test | 56.9 mIoU |  [ACDC-night-val]() 
| Refign-HRDA     | Cityscapes→ACDC | ACDC-night-test | 65.1 mIoU |  [ACDC-night-test]()
| Refign-HRDA     | Cityscapes→ACDC | ACDC-night-val | 55.4 mIoU | [ACDC-night-val]()
|||||||
| Refign-DeepLabv2 | Cityscapes→Dark Zurich | Dark Zurich-test | 55.0 mIoU |  [Dark Zurich-val]() 
| Refign-DAFormer | Cityscapes→Dark Zurich | Dark Zurich-test | 57.7 mIoU |  [Dark Zurich-val]() 
| Refign-HRDA     | Cityscapes→Dark Zurich | Dark Zurich-test | 63.4 mIoU |   [Dark Zurich-test]()
| Refign-HRDA     | Cityscapes→Dark Zurich | Dark Zurich-val | 52.5 mIoU |  [Dark Zurich-val]()
