# Artistic_style_transfer

## About the Project:
This project demonstrates artistic style transfer using deep learning, allowing an image's style to be blended with another image's content to create a new, unique image. The model leverages pre-trained convolutional neural networks (CNNs)—specifically VGG16 and VGG19—to separate style and content features and then combine them iteratively. This project involves the dissection of images into high-level content and low-level style representations and showcases the impact of different CNN architectures on the final image quality.

## Libraries Used:
**TensorFlow / PyTorch**: For implementing the VGG models and performing neural network operations.<br>
**NumPy:** For efficient numerical operations and data handling.<br>
**Matplotlib / PIL:** For visualizing and processing images.<br>
**PIL:** to open, manipulate, and save various image file formats. <br>

## Image Dissection VGG16:
The project splits the image into:<br>

**High-level layers:** block4_conv1 - block4_conv3; block5_conv1 - block5_conv3 : High-level layers capture abstract features and semantic information, such as object parts, overall structure, and spatial hierarchies. <br>

**Mid-level layers:** block3_conv1 - block3_conv3 : Mid-level layers capture more complex shapes and patterns, such as local structures and parts of objects. They start to represent groups of edges and more detailed textures.  <br>

**low-level layers:** block1_conv1 - block1_conv2; block2_conv1 - block2_conv1 : These layers capture basic features like edges, colors, textures, and simple patterns. <br>

**Total Layers:** 13 convolutional layers, 5 max-pooling layers, and 3 fully connected layers (21 layers in total).

## Image Dissection VGG19:
The project splits the image into:<br>

**High-level layers:** block4_conv1 - block4_conv4; block5_conv1 - block5_conv4 : Abstract object parts, spatial hierarchies, and semantic structure. <br>

**Mid-level layers:** block3_conv1 - block3_conv4 : More complex patterns, shapes, and intermediate structures.  <br>

**low-level layers:** block1_conv1 - block1_conv2; block2_conv1 - block2_conv2 : Basic textures, edges, colors, and simple patterns. <br>

**Total Layers:** 16 convolutional layers, 5 max-pooling layers, and 3 fully connected layers (24 layers in total).

## Metrics, Performance (VGG16 vs. VGG19):

**Content Clarity:** Achieved by tuning the content weight and image size hyperparameters to capture distinct content features. Higher weights and high image sizes lead to clearer structures from the content image.<br>

**Style Coherence:** Adjusted through style weight to capture intricate textures and patterns from the style image. <br>

### Performance Comparison:
**VGG16:** Faster convergence with fewer layers, leading to quicker style transfer but sometimes less detail.<br>

**VGG19:** Provides more refined style transfer but at the cost of additional computational time, as it has more layers than VGG16 ut in few cases the basic clarity is achieved within fewer epochs. <br>

## Analysis Summary:
**Convergence and Optimization:** Observed a relatively slower convergence in VGG19 due to its depth, while VGG16 often converges faster but with less clarity. Optimized performance using SGD with learning rate decay to ensure that the combination image captures both content and style without excessive blurring or distortion.<br>

**Style-Content Balance:** Achieved balanced outputs by experimenting with various weights for content and style loss. Higher style weights lead to more artistic texture, while higher content weights preserve more structure.<br>

**Overall Recommendation:** VGG19 is recommended for a better style transfer projects with slightly better clarity with a decent computational demands. <br>

This project exemplifies the potential of CNNs in artistic applications, with VGG16 and VGG19 providing distinctive advantages in speed and quality, respectively.

# Style Image:

<img src="https://github.com/user-attachments/assets/aac38441-eb85-40b1-a6f5-ab0ff4d06734" alt="" width="500" height="400">

# Content Image:

<img src="https://github.com/user-attachments/assets/bac5d94a-c351-400f-b855-39f6791c4ba8" alt="" width="500" height="400">

# My Combination Image:

<img src="https://github.com/user-attachments/assets/43fe2315-89f7-4d6e-8fc1-633c73f63a96" alt="" width="500" height="400">
