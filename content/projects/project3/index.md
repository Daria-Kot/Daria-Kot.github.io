+++
title = "Predicting Surface Temperature by Green Space Image Recognition"
description = "This project explored how urban green spaces affect surface temperatures in New York City by leveraging computer vision and artificial intelligence. Using satellite imagery, we developed machine learning models to predict whether a given area’s surface temperature is above or below NYC's average. This research highlighted the potential of AI in addressing urban heat inequality, a critical issue exacerbated by global warming."
weight = 2
[taxonomies]
tags = ["Machine Learning", "CNNs"]
+++

### Overview
Our project explored how urban green spaces affect surface temperatures in New York City by leveraging computer vision and artificial intelligence. Using satellite imagery, we developed machine learning models to predict whether a given area’s surface temperature is above or below NYC's average. This research highlighted the potential of AI in addressing urban heat inequality, a critical issue exacerbated by global warming.

### Key Highlights
#### Data Collection & Preparation:

<img src="/files/project3 media/green.png#end" alt="Satellite Image of NYC" style="display:block;">


- Utilized satellite imagery and datasets (e.g., NYC heat maps and vegetation indices) to quantify green space and temperature metrics.
- Preprocessed spatial data into image blocks and labels for model training, incorporating geo-spatial attributes like latitude and longitude.

<figcaption> New York City with NDVI mask. Darker green areas correspond to areas with
more vegetation.</figcaption>



#### Custom AI Models:
- Built a convolution neural network (CNN) from scratch in PyTorch to classify temperature regions.
- Enhanced the CNN with geo-spatial features, improving prediction accuracy from 78.1% to 84.2%.
- Fine-tuned a pre-trained ResNet model for faster training and higher accuracy using transfer learning techniques.
<img src="/files/project3 media/cnn.png" alt="" style="display:block;">


#### Causal Discovery:
- Applied causal AI algorithms to explore correlations between green spaces and temperature changes.
- Refined datasets to improve model performance, revealing strong correlations but limited evidence of causation due to data constraints.
<img src="/files/project3 media/cause.png" alt="" style="display:block;">
