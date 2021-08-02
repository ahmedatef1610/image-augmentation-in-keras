# image-augmentation-in-keras

Data preparation is required when working with neural network and deep learning models. Increasingly data augmentation is also required on more complex object recognition tasks.

Data augmentation means to increase the amount of data. In, other words, having a larger dataset means a more robust model. But acquiring more data cannot always be as easy and there may be a problem of storing them and feeding it to model.

To mitigate this problem, we can manually increase the data by doing some changes or we can make use of one of Keras image preprocessing class that can do this in just a few lines of codes.

In this post you we’ll see how to use data preparation and data augmentation with your image datasets when developing and evaluating deep learning models in Python with Keras.

About the image augmentation API provide by Keras and how to use it with your models.

1. How to perform feature standardization.
2. How to perform ZCA whitening of your images.
3. How to augment data with random rotations, shifts and flips.
4. How to save augmented image data to disk.

Keras Image Augmentation API: ImageDataGenerator:

It generates batches of augmented data from the original batch. It takes the images, applies some random transformation on it, and produces a new batch for training.
Note: One thing to note here that ImageDataGenerator does not return the original images instead it just returns batches of augmented data which is a result of some transformation done on original data.

---

[code here](https://nbviewer.jupyter.org/github/ahmedatef1610/image-augmentation-in-keras/blob/master/image_augmentation.ipynb)

---

1. Loading Dataset

We will use MNIST handwritten digit recognition for data augmentation. Executing below code will load MNIST dataset from keras.datasets

![image](https://user-images.githubusercontent.com/39852784/127802554-9463bb5f-5c9a-442d-a693-fcc5f7d4f7df.png)


2. Standardizing Features

The pixel standardization is supported at two levels: either per-image (called sample-wise) or per-dataset (called feature-wise). Specifically, the mean and/or mean and standard deviation statistics required to standardize pixel values can be calculated from the pixel values in each image only (sample-wise) or across the entire training dataset (feature-wise).
You can perform feature standardization by setting the featurewise_center and featurewise_std_normalization arguments on the ImageDataGenerator class


![image](https://user-images.githubusercontent.com/39852784/127802660-c07c14b5-eb4e-420f-954f-98759da08f16.png)


3. ZCA Whitening

A whitening transform of an image is a linear algebra operation that reduces the redundancy in the matrix of pixel images. Typically, image whitening is performed using the Principal Component Analysis (PCA) technique. More recently, an alternative called ZCA shows better results and results in transformed images that keeps all of the original dimensions and unlike PCA, resulting transformed images still look like their originals.

![image](https://user-images.githubusercontent.com/39852784/127802692-18afa42e-bbf0-466c-88b1-63239b0632cc.png)

4. Random Rotations

ou can train your model to better handle rotations of images by artificially and randomly rotating images from your dataset during training. The example below creates random rotations of the MNIST digits up to 90 degrees by setting the rotation_range argument.

![image](https://user-images.githubusercontent.com/39852784/127802735-b5145a76-0627-47f5-ae62-d48d7b68b707.png)


5. Random Shifts

Objects in your images may not be centered in the frame. They may be off-center in a variety of different ways. You can train your deep learning network to expect and currently handle off-center objects by artificially creating shifted versions of your training data. Keras supports separate horizontal and vertical random shifting of training data by the width_shift_range and height_shift_range arguments.

![image](https://user-images.githubusercontent.com/39852784/127802906-b73ba5fd-fea5-4dc0-bf50-f6d1df2415d8.png)

6. Random Flips

Another augmentation to your image data that can improve performance on large and complex problems is to create random flips of images in your training data. Keras supports random flipping along both the vertical and horizontal axes using the vertical_flip and horizontal_flip arguments.

![image](https://user-images.githubusercontent.com/39852784/127802967-fca8da25-9a17-4b1d-881c-2aa883409405.png)


7. Save Augmented Images to file

![ScreenShot_20210802060608](https://user-images.githubusercontent.com/39852784/127803031-c4fe5630-a550-40c0-8d72-a7df99bf60d7.png)
 
 ---
 
 depend on these articles [link](https://medium.com/analytics-vidhya/image-augmentation-using-keras-99072b490c72) [link](https://machinelearningmastery.com/how-to-configure-image-data-augmentation-when-training-deep-learning-neural-networks/)
 
 ---
