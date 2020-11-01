# Face_Generation

## Overview
In this project, I trained a DCGAN using the [Large-scale CelebFaces Attributes (CelebA) Dataset](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html). The goal is to get a generator network to generate new images of faces that look as realistic as possible.

## Steps
1. **Pre-processed Data**   
Here the images have already been cropped to remove parts of the images that don't include a face, then resized down to 64x64x3 NumpPy images. Some sample data is shown below.
![Faces from dataset](https://github.com/cl3080/Face_Generation/blob/main/SampleFaces.png)

2.**Define the Model**   
A GAN is comprised of two adversarial networks, a discriminator and a generator.
* **Discriminator:** This is a convolutional classifier without any maxpooling layers. The inputs to the discriminator are 32x32x3 tensor images. The output is a single value that will indicate whether a given image is real or fake.

* **Generator:** The generator should upsample an input and generate a new image of the same size as the training data 32x32x3. This should be mostly transpose convolutional layers with normalization applied to the outputs.

3.**Training**   
Training will involve alternating between training the discriminator and the generator.
For the discriminator, the total loss is the sum of the losses for real and fake images, `d_loss = d_real_loss + d_fake_loss`. The generator loss will look similar only with flipped labels. The generator's goal is to get the discriminator to *think* its generated images are *real*.

4.**Generate samples from training**   
Training will involve alternating between training the discriminator and the generator. 
![Generated faces](https://github.com/cl3080/Face_Generation/blob/main/GeneratedFaces.png)

## Codes
The details for each step can be found in this jupyter notebook:
[**Jupyter notebook**](http://htmlpreview.github.io/?https://github.com/cl3080/Face_Generation/blob/main/dlnd_face_generation.html)
