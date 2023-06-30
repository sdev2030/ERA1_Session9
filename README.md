# ERA1_Session9
## Assignment
    1. Use CIFAR10 dataset 
    2. Write a new network that 
        1. has the architecture to C1C2C3C40 (No MaxPooling, but 3 3x3 layers with stride of 2 instead) (If you can figure out how to use Dilated kernels here instead of MP or strided convolution, then 200pts extra!) 
           C1[cs1 cs1 cs3] C2[cs1 cs1 cs3] C3[cs1 cs1 cs3] C40[cs1 cs1 cs1] GAP + 
        2. total RF must be more than 44 
        3. one of the layers must use Depthwise Separable Convolution 
        4. one of the layers must use Dilated Convolution 
        5. use GAP (compulsory):- add FC after GAP to target #of classes (optional) 
        6. use albumentation library and apply: 
            1. horizontal flip 
            2. shiftScaleRotate 
            3. coarseDropout (max_holes = 1, max_height=16px, max_width=16px, min_holes = 1, min_height=16px, min_width=1px, fill_value=(mean of your dataset), mask_fill_value = None) 
        7. achieve 85% accuracy, as many epochs as you want. Total Params to be less than 200k. 

## Solution - Notebook [s9_assignment](https://github.com/sdev2030/ERA1_Session9/s9_assignment.ipynb)
In this we will use Depthwise separable convolution layer and dilated convolution layer instead of Max Pooling or strided convolution to achieve target test accuracy of more than 85% from the 25th epoch.

Following are the model parameter, train and test accuracies achieved in training the model for 30 epochs.
- Model Parameters - 199200
- Train Accuracy - 82.72%
- Test Accuracy - 86.46%

Graphs from training showing loss and accuracy for train and test datasets
![Training Graphs](https://github.com/sdev2030/ERA1_Session9/blob/main/images/training_graphs.png)

Ten misclassified images from the batchnorm trained model.
![Misclassied images](https://github.com/sdev2030/ERA1_Session9/blob/main/images/wrong_classified.png)
