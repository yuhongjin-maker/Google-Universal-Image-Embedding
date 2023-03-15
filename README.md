## Google Universal Image Embedding

<img width="842" alt="Screen Shot 2023-03-14 at 6 47 14 PM" src="https://user-images.githubusercontent.com/59128675/225158965-9d8908eb-b8dd-4638-a793-3afe2ad84ba9.png">


### Objective

In this competition, participants were asked to developer models that could efficiently retrieve images from a large database. For each query image, the model was to retrieve the most similar image from an index set

### Introduction

In this competition, participants develop models to retrieve images from a database of the same objects as the query. Images in the competition dataset include various object types such as clothing, artwork, landmarks, furniture, packaging, etc

The competition is in the form of representational learning: we will create a model to extract feature embeddings of the image(Embedding), submitting models via kaggle notebooks. 

* Competition Type: This competition belongs to computer vision/ feature embedding, so the recommended model or library: EfficientNet/CLIP/Swin Transformer

* Competition Data： No training set will be provided for this competition

* Evaluation: Submissions are evaluated according to the mean Precision @ 5 metric, where we introduce a small modification to avoid penalizing queries with fewer than 5 expected index images. In detail, the metric is computed as follows:

<img width="529" alt="Screen Shot 2023-03-14 at 6 42 03 PM" src="https://user-images.githubusercontent.com/59128675/225158226-00cb012f-64b2-4f08-b9a4-3f8bb3be5660.png">

* Data description

Distribution of object types in the dataset

<img width="836" alt="Screen Shot 2023-03-14 at 6 49 10 PM" src="https://user-images.githubusercontent.com/59128675/225159248-c99e6d21-a4c5-49fd-982b-87c86aa18016.png">

### Methodology

1. This competition based on CLIP ViT-H/14 on LAION-2B model and add an arcface layer to it in order to train image retrieval skills.

2. Because this competition does not provide an official training set, the organizers only provided the types of images, such as clothing and accessories, packaged goods, landmarks, furniture and home decor, so wer targeted three datasets as our training and validation images.

* imagenet1k: This dataset was created by imagenet(1k). To decrease the size of dataset, each class in this dataset only contains 50 images

* products10k: This dataset was created by product10k. To decrease the size of dataset, each class in this dataset only contains 50 images

* Google landmark recognition 2021(Competition dataset): This dataset was created from the kaggle competition dataset. To reduce the size of dataset, this dataset uses the top 7k class images and a large number of images(50 images per class)

3. This training is using google tpu, part of the codes for tpu optimization, It could reproduce the code results in kaggle or google colab

### Result

We selected larger datasets targeted for training and validation based on the image categories separately. Then the CLIP with outstanding few-shot capability was selected as our pre-training model. Because of the large model and large amount of data, our training was done on the TPU provided by kaggle, and the code was adjusted with targeted optimization. Finaaly, we obtained a precision of 0.65 @5.
