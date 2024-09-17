# Strawberry Disease Semantic Segmentation  

<h3> Dataset </h3>  
Strawberry Disease Dataset is found on kaggle.com and contains images of strawberry plant including plants infected with 7 diseases typical for this plant. Dataset is well prepared for image segmentation task: data is split in train and test set, and each image is accompanied by .json file containing the points for mask reconstruction. This means that data is specifically prepared for semantic segmentation task. Total number of training images is 1450, which is not enough data for most models built for this task. To face this issue we will have to apply ML techniques such as Transfer Learning and image augmentation. Transfer Learning means that we will use prototyoe of existing model and this will improve training efficiency and accuracy. Augmentation is name for techniques to generate more data from existing dataset.

<h3> Semantic Segmentation </h3> 
Image segmentation is a task that splits pixels of image in different fields by classifying every pixel in an image (by assigning label to it). It provides much more information than other image ML techniques such as object detection or image classification. In a way semantic segmentation can be thought of as image classification on a pixel level. If for example, there are 3 cats in the image, semantic segmentation forms a mask over each cat and pixels of all 3 cats would get classified as cat (a single label). Final output of semantic segmentation is predicted mask. This technique is used in real world applications such as biomedical applications (such as diagnosing different conditions), as well as for self driving cars, clothes segmentation etc. Semantic segmentation is often combined with GANs.

<h3> Transfer Learning </h3>  
To perform semantic segmentation on this dataset we will use technique called Transfer Learning which refers to using pretrained model. Because deep networks used for image segmentation usually consist of large amount of layers, this technique can save a lot of time when it comes to both building and training our model. We will use version of U-Net architecture commonly used in biomedical image segmentation, already trained on ImageNet data (we are importing weights), as a base for our model. Then we will retrain it with data adding the Strawberry Disease Dataset to the model.

<h3> U-Net </h3>  
U-Net is a ccn that is mostly used for medical image processing, and uses encoder-decoder approach to semantic segmentation. Encoder extracts important features, while decoder registers patterns in data to create the mask. This means that decoder is also responsible for the output. Final output gets the resolution of original image.
