# Semantic Segmentation
# 1. Network Details
Ive used UNET with efficientnet and mobilenet bases. UNET is an encoder decoder architecture. The encoder part can be any CNN architecture so ive used efficientnet and mobilenet and decoder part is bascially resizing the feature map to the original size of the image with minimum information.
Pretrained weights of imagenet were loaded in EfficientNetB0 block. This was used as an encoder. The decoder block was made using deconvolution layers for  resizing map to original size.
Pretrained weights of imagenet were loaded in MobileNetV2 block. This was used as an encoder. The decoder block was made using deconvolution layers for  resizing map to original size.

 
  
  # 2. Instructions for installations
 If you are using google colab than install tensorflow and its packages.

```
!pip install tensorflow
```  
and then import following modules:
```import tensorflow as tf
from tensorflow.keras.layers import Conv2D, BatchNormalization, Activation, MaxPool2D, Conv2DTranspose, Concatenate, Input
from tensorflow.keras.models import Model
from tensorflow.keras.applications import EfficientNetB0,MobileNetV2

```
# 3. Instructions for running script
In order to run the script on google Colab:
1. Download the .ipynb file and upload it to colab. 
2. Put data files on drive.
3. Update the path locations in colab file according to your data path locations.
4. Execute the cells.


 # 4. Quantitative results
 

|     Evaluation Metrics    |     UNET with Efficient net base    |     UNET with Mobile net base    |
|---------------------------|-------------------------------------|----------------------------------|
|     Accuracy              |     0.1755                          |                0.2356                   |
|     Dice coefficient      |     0.87999                         |                0.90555                  |
|     Sensitivity           |     0.86285                         |                   0.912420               |
|     Specificity           |     0.47777                         |                   0.644608               |

# 5. Visual Results 
### Original test images with ground truths

<img width="484" alt="testimg" src="https://github.com/mnasim99/CV-A2/assets/57056774/8e0a996d-832c-4517-b051-ccee449b2e0a">


### Mobilenet - UNET
<img width="445" alt="mobnet" src="https://github.com/mnasim99/CV-A2/assets/57056774/cb1f4ddb-f61b-44b0-836e-a36222646bd4">

### Efficient net - UNET
<img width="402" alt="effnet" src="https://github.com/mnasim99/CV-A2/assets/57056774/326f01bc-619b-4235-a75d-84c246565494">

# 6. Authors
Mariam Nasim - 399635






