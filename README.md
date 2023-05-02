# CV-A2
# 1. Network Details

Original input image was 224x224, it was resized because of the limited resources. For full size images code was crashing. Images were resized to 100 x 100 pixels. Transfer learning was used. VGG16 and ResNet 50 were used as base models. Pretrained weights of imagenet were loaded in VGG16 and resnet block. Even though
the imagenet dataset was not that relevent still it helped the
model to converge. Without imagenet pretrained weights there was no increase in accuracy whereas pretrained weights after 2 to 3 epocs there was a
gradual increase in the accuracy. The output of the model was flattended and connected to the emotion expression
label output later with softmax activation. The output later of valence and
arousal uses this same as input and outputs the continous attributes with
linear activation.
Transfer learning was done using following method: \url{https://www.tensorflow.org/guide/keras/transfer_learning }<img width="511" alt="VGG16" src="https://user-images.githubusercontent.com/57056774/235596059-d5605a8e-14e1-437b-bdae-9d45feb2515f.PNG">

<img width="630" alt="resnet" src="https://user-images.githubusercontent.com/57056774/235595939-7fcfb991-5f8e-4f7e-997a-9dd28cb9f96e.PNG">


 
  
  # 2. Instructions for installations
 If you are using google colab than install tensorflow and its packages.

```
!pip install tensorflow-addons
```  
and then import following modules:
```import tensorflow as tf
from tensorflow.keras.applications import VGG16,EfficientNetV2L,ResNet50,ResNet101
from tensorflow.keras.utils import to_categorical
from tensorflow.keras.optimizers import SGD
from matplotlib import pyplot as plt
import tensorflow_addons as tfa
```
# 3. Instructions for running script
In order to run the script on google Colab:
1. Download the .ipynb file and upload it to colab. 
2. Put .tar files for dataset on drive.
3. Update the path locations in colab file according to your data path locations.
4. Execute the cells.


 # 4. Quantitative results
 
 ## a. Labels

|     Evaluation metric for classsification    |     VGG16    |     ResNet50                                                                                                                       |
|----------------------------------------------|--------------|------------------------------------------------------------------------------------------------------------------------------------|
|     Accuracy                                 |      0.2345        |     0.145                                                                                                                          |
|     F1-Score                                 |     0:  0.2718   ,  1: 0.3932  ,   2:  0.0009304  ,   3:  0.0002458 ,    4:  0.0001625  ,   5:  0.3041   ,  6:  0.0002598   ,  7:  0.3046         |     0:  0.142  ,   1:  0.168    , 2:  0.0002   ,  3:  0.00000531  ,   4:  0.00000532  ,   5:  0.208 ,    6:  0.00000802   ,  7:  0.179    |
|     Cohens Kappa                             |      0.12521        |     0.02347678                                                                                                                     |
|     Krippendorfs Alpha                       |         0.12     |     0.50128144                                                                                                                     |
|     Area Under Curve                         |        0.4700      |     0.50128144                                                                                                                     |
|     AUC Precision Recall                     |         0.9953     |     0.995433                                                                                                                       |
                                                                                                                                  
## b. Valence
|     Measures for Valence    |     VGG16    |     ResNet50      |
|-----------------------------|--------------|-------------------|
|     RMSE                    |0.508141      |     0.48378897    |
|     Correlation             |0.2638869     |     0.13519513    |
|     CCC                     |0.240682      |     0.03560       |

## c. Arousal
|     Measures for Arousal    |     VGG16    |     ResNet50    |
|-----------------------------|--------------|-----------------|
|     RMSE                    | 0.42576      |     0.380309    |
|     Correlation             |0.018337      |     0.03687     |
|     CCC                     |0133316       |     0.008140    |

 

# 5. Visual Results 
### ResNet50
<img width="613" alt="corr-resnet" src="https://user-images.githubusercontent.com/57056774/235596696-1199371e-de7e-45d9-b0fc-243157a74981.PNG">

  <img width="498" alt="inc-resnet" src="https://user-images.githubusercontent.com/57056774/235596676-20b5a0ff-4921-42b2-8729-abab448c8162.PNG">



### VGG16
<img width="532" alt="corr-vgg" src="https://user-images.githubusercontent.com/57056774/235651680-85dee8bc-6a90-49ce-b786-9a794f39a6e7.PNG">

<img width="552" alt="inc-vgg" src="https://user-images.githubusercontent.com/57056774/235651649-140ef270-dcd5-4d45-9ca0-e7c973eb2437.PNG">

# 6. Authors
Mariam Nasim - 399635






