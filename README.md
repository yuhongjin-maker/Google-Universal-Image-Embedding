## Google Universal Image Embedding

### Introduction

In this competition, participants develop models to retrieve images from a database of the same objects as the query. Images in the competition dataset include various object types such as clothing, artwork, landmarks, furniture, packaging, etc

The competition is in the form of representational learning: we will create a model to extract feature embeddings of the image(Embedding), submitting models via kaggle notebooks. 

* Competition Type: This competition belongs to computer vision/ feature embedding, so the recommended model or library: EfficientNet/CLIP/Swin Transformer

* Competition Data： No training set will be provided for this competition

* Evaluation: Submissions are evaluated according to the mean Precision @ 5 metric, where we introduce a small modification to avoid penalizing queries with fewer than 5 expected index images. In detail, the metric is computed as follows:

<img width="529" alt="Screen Shot 2023-03-14 at 6 42 03 PM" src="https://user-images.githubusercontent.com/59128675/225158226-00cb012f-64b2-4f08-b9a4-3f8bb3be5660.png">

