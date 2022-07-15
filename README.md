# Apple Leaf Health Status Using CNNs

Given a photo of an apple leaf, the notebook predicts which of the 4 classes the leaf belongs to. This is a Kaggle competition dataset and  there are no labels for the Test set. So, the training dataset will be split into Train and Validation sets. The challenge is to distinguish between leaves which are <b>healthy</b>, those which are infected with <b>apple rust</b>, those that have <b>apple scab</b>, and those with <b>more than one disease</b>.

Automated monitoring through installation of cameras in the Apple orchards can help focus on the plants which actually needs attention. Farmers can then decide on the treatment with chemicals for resolution.

The following sections were covered

- Data Augmentation
- Data Normalisation
- Training On GPU
- Learning rate scheduling : One Cycle Learning rate policy
- Weight Decay
- Adam & SGD Optimizers

https://www.kaggle.com/competitions/plant-pathology-2020-fgvc7/data

## Summary & Discussion

Training deep convolutional neural networks with high quality images and complex networks is resource and time intensive. I have done the below to improve the performance and reduce the training time.

<b>Data Normalization</b> The appleaf images are mostly dominated by green color and the pixel values from this channel can disproportionately impact the losses and gradients. This was overcome by subtracting the mean and dividing from the pixel values before dividing them with respective channel standard deviations.

<b>Data Augmentation</b> Due to small dataset size, random transformations were applied whihc helps the network in better training.

<b>Adam Optimizer</b> Instead of SGD, I have used adam optimizer whihc is state of the art whihc uses adaptive learning rate and helps in faster trainning.

## Further Improvements

The below techniques can further be applied along with running the model on a GPU will certainly improve the run time.

Using <b>Transfer learning</b> for faster training and check whether complex networks can really improve the accuracy with the dataset at hand. Also, the apple leaf dataset is small for a CNN project and it can be the reason for the poor performance. Adding <b>Residual connects</b> and <b> Batch Normalization </b> could potentially improve the performacnce of the model.
