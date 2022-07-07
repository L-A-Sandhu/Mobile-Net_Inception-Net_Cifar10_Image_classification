# Efficient-Image-Classification

 This repository contains comparisons of different convolution neural networks for the CIFAR-10 data-set.The model is fine tunned on cifar10 dataset. The model were earlier trained on imagenet dataset. The script automatically downloads the cifar 10 dataset. Clone this repo please follow the following steps 
```
git clone https://github.com/L-A-Sandhu/Efficient-Image-Classification.git

```

The rest of the repository is divided as follows. 
  1. Requirements
  2. Fine Tuning
  3. Using Pretrained Model
  4. Summary
## Requirements 
This repository requires 
* **tensorflow**
* **matplotlib**
* **scipy**
* **protobuf**


For complete installation please follow the following steps
```
cd M0bile_Net/
conda create  -n <environment -name> python==3.7.4
conda activate <environment-name>
pip install -r requirements.txt
```
## Fine Tuning 
This section disccusses the fine tunning method for Mobile Net and Inception net. The keras implementations of Mobile Net and Inception Net is used in this work. Their weights are trained on Image Net dataset. However, in this work we have  fine tuned the model on cifar10 dataset. 
### Mobile Net

This section explains traning, testing and infrence steps for Mobile Net. please follow the following commands 

#### Traning 
```
python Mobile-Net.py  --model_dir=<Location for saving model>  --inp=<train , test or infer> --b_s=< Batch size> --e=<epoch>
example command 
python Mobile-Net.py  --model_dir='./checkpoint/'  --inp=train --b_s=16 --e=100

```
#### Test 
```
python Mobile-Net.py  --model_dir=<Location for saving model>  --inp=<train , test or infer> --b_s=< Batch size> --e=<epoch>
example command 
python Mobile-Net.py  --model_dir='./checkpoint/'  --inp=test --b_s=16 --e=100

```

### Inception-Net
This section explains traning, testing and infrence steps for Inception Net. please follow the following commands 
```
cd ../Inception_NET/
```
### Traning 
 
```
python Inception-Net.py  --model_dir=<Location for saving model> --inp=<train , test > --b_s=< Batch size> --e=<epoch>
example command 
python Inception-Net.py  --model_dir='./checkpoint/' --inp=train --b_s=16 --e=100
```
### Test 
```
python Inception-Net.py  --model_dir=<Location for saving model> --inp=<train , test > --b_s=< Batch size> --e=<epoch>
example command 
python Inception-Net.py  --model_dir='./checkpoint/' --inp=test --b_s=16 --e=100

```
## Pretrained Model
we have trained the model on cifar10 dataset with batch size 128 and 50 epochs. You can download the pretrained weights and place them at **./Inception_NET/checkpoint/**  or **./M0bile_Net/checkpoint/**/older for inferene. The pretrained weights for Mobile net and Inception Net can be be downloaded from the folllowing links respectively. 
```
https://drive.google.com/file/d/1OCxDNDUbMJcoo8QbzB6hM4r4yqXOXpZU/view?usp=sharing
https://drive.google.com/file/d/144j9-G-v2x6YCTZ4u9_NDzXpVnVwT_kC/view?usp=sharing
``` 
## Results and comparision 
Test results and comparision for both models is shown in the following table 
| Model         | F1-Score | Accuracy | Precision | Recall |
|---------------|----------|----------|-----------|--------|
| Mobile-Net    | 0.835    | 0.836    | 0.848     | 0.836  |
| Inception-Net | 0.812    | 0.811    | 0.82      | 0.81   |


### Confusion Matrix 
Thee confusion matrix for Mobile net is shown shown below

[[728  18  75  20  63   3  30   1  49  13]
 [  0 964   1   4   2   0   5   0  12  12]
 [ 10   0 898  23  31   5  30   1   2   0]
 [  7   7  61 688  96  75  59   4   3   0]
 [  0   1  35  17 912  11  19   4   1   0]
 [  1   6  39 123  64 724  37   5   1   0]
 [  0   1  16  19  11   3 949   0   1   0]
 [  1   5  36  42  82  83  12 736   2   1]
 [  5  10  17   8  11   4   9   1 932   3]
 [  3  83   6  18   9   4  16   1  29 831]]

The confusion matrix for Inception net is shown below

[[894  12  14   9   3   1   2   1  43  21]
 [  7 933   1   2   2   0   3   0  27  25]
 [103   7 742  63  23  19  30   5   6   2]
 [ 27   3  50 765  33  66  19   5  19  13]
 [ 21   3  82  67 769  14  13   5  20   6]
 [ 10   8  32 207  31 687   6   5   7   7]
 [ 18   4  42  55  18  14 828   0  19   2]
 [ 19   4  27  70  66  73   8 715   3  15]
 [ 29   8   6   5   1   1   1   1 933  15]
 [ 25  74   4   7   0   4   1   3  32 850]]

