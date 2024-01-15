# **Cat Breeds Classification with Vision Transformer**
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Abstract

This project represents an end-to-end side project in the realm of computer vision, employing a dataset sourced from [Kaggle](https://www.kaggle.com/datasets/knucharat/pop-cats). It's worth noting that the resource can be traced back to [Petfinder](https://www.petfinder.com/developers/), accessible through the [petpy](https://github.com/aschleg/petpy) library. The dataset used in this endeavor has undergone thorough cleaning, and the ensuing integration involves storing path-label pairs in `labels.csv`.

The core of the project revolves around the utilization of the [vision transformer (VIT)](https://huggingface.co/google/vit-base-patch16-224), a pre-trained model released by Google. The model is fine-tuned to develop a classifier for 20 common cat breeds. The Google VIT comes pre-trained to classify 1000 classes of objects, encompassing 5 cat breeds. Importantly, three of these 5 breeds (Persian, Egyptian Mau, Siamese) align with our target 20 breeds. This setup presents a unique opportunity to explore fine-tuning a larger model to address a more specific task, offering valuable insights.

![VIT structure](figures/VIT_STRUCTURE.JPG)
<p align="center">
    The architecture overview of Vision Transformer. This diagram is extracted from
    https://arxiv.org/abs/2010.11929
</p>

## Result
In order to establish a baseline, I randomly selected 15 images from the three existing breeds in VIT targets (Persian, Egyptian Mau, Siamese) to test the model before fine-tuning. The accuracy at this initial stage was 66.7% (refer to [Cat_breeds_basic.ipynb](colab folder) for detailed information). After undergoing 260 epochs of fine-tuning, the model converged to an impressive accuracy of 92.6% on the test dataset. Subsequently, I conducted an additional training run on the entire dataset for 15 more epochs. Further details can be found in the colab folder.

The ultimate outcome of this project is shared on [HuggingFace](https://huggingface.co/PinChunPai/cat20_breed_fine_tune) and subsequently employed in constructing a [website application](https://huggingface.co/spaces/PinChunPai/cat20_breeds). This platform enables the public to assess the model's performance by uploading their own cat pictures, bringing the evaluation process into the real world and fostering broader engagement.

![web app](TEST/Test1.JPG)
<p align="center">
    Demonstration of website application.
</p>
