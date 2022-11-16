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
  
  Please, download the NighttimeDrivingTest.zip from [here](http://people.ee.ethz.ch/~daid/NightDriving/) and extract it to `$DATA_DIR/NighttimeDrivingTest`.


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
To facilitate qualitative segmentation comparisons, validation set and testing set predictions of InforMS can be directly downloaded.

| Model         | Task           | Test Set       | Test Score    | Predictions  |
|---------------|----------------|-----------------|-----------------|------------|
| InforMS-DeepLabv2 | Cityscapes→ACDC | ACDC-night-test | 51.7 mIoU | [ACDC-night-test](https://drive.google.com/file/d/1NcRK41NuiRWvllHbVxzENPFIv3Da2npr/view?usp=share_link) 
| InforMS-DeepLabv2 | Cityscapes→ACDC | ACDC-night-val | 42.9 mIoU | [ACDC-night-val](https://drive.google.com/file/d/1R4njeMDgMZVQBFxRfxbFjd5EPxttq6iT/view?usp=share_link) 
| InforMS-DAFormer | Cityscapes→ACDC | ACDC-night-test | 56.9 mIoU |  [ACDC-night-test](https://drive.google.com/file/d/16fo7soGtaNZUgIlkhvoDYuDAbGhUMjWh/view?usp=share_link) 
| InforMS-DAFormer | Cityscapes→ACDC | ACDC-night-val | 47.7 mIoU |  [ACDC-night-val](https://drive.google.com/file/d/1IuxaR1iTTaNyZKroxi6Nj_QxYicCeOp-/view?usp=share_link) 
| InforMS-HRDA     | Cityscapes→ACDC | ACDC-night-test | 65.1 mIoU |  [ACDC-night-test](https://drive.google.com/file/d/1X04iT1bv2DxhcQnsrg8UvlUP1kVkhcX2/view?usp=share_link)
| InforMS-HRDA     | Cityscapes→ACDC | ACDC-night-val | 55.4 mIoU | [ACDC-night-val](https://drive.google.com/file/d/1tGo0nsQGAnfBKjMLdH-96sdTHggmRxNo/view?usp=share_link)
|||||||
| InforMS-DeepLabv2 | Cityscapes→Dark Zurich | Dark Zurich-test | 55.0 mIoU |  [Dark Zurich-test](https://drive.google.com/file/d/1Vst6d_uXXjb0Iu2wPJhYlUS94DrfhnKn/view?usp=share_link) 
| InforMS-DeepLabv2 | Cityscapes→Dark Zurich | Dark Zurich-val | 40.0 mIoU |  [Dark Zurich-val](https://drive.google.com/file/d/1sMBRgnPnwMFn8b2JZjw0buHCxPA6nD39/view?usp=share_link) 
| InforMS-DAFormer | Cityscapes→Dark Zurich | Dark Zurich-test | 57.7 mIoU |  [Dark Zurich-test](https://drive.google.com/file/d/126B69O1DjTwIIbbJBeZTjsLaJfdcyz6x/view?usp=share_link) 
| InforMS-DAFormer | Cityscapes→Dark Zurich | Dark Zurich-val | 42.7 mIoU |  [Dark Zurich-val](https://drive.google.com/file/d/1lHvMruDDmuOoDjlh8-BDGy0tu-CR-MUO/view?usp=share_link) 
| InforMS-HRDA     | Cityscapes→Dark Zurich | Dark Zurich-test | 63.4 mIoU |   [Dark Zurich-test](https://drive.google.com/file/d/1OIp0P2PtBKD6JVpfuPQUHHbHHgKmznKt/view?usp=share_link)
| InforMS-HRDA     | Cityscapes→Dark Zurich | Dark Zurich-val | 52.5 mIoU |  [Dark Zurich-val](https://drive.google.com/file/d/16s-j6xHeAPaOIEDHISIElYayCHRvpDDh/view?usp=sharing)
