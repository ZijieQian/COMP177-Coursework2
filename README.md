# COMP177-Coursework2
COMP177 Coursework2 Code:

We developed five variations of models for detecting landslides in satellite images of Nepal. Among these, the model whose name includes (focal+lr+input) was selected for the final analysis.

The dataset used for training and evaluation is publicly available at [Zenodo](https://zenodo.org/records/3688363). A major challenge in this dataset is the severe class imbalance: positive pixels (representing landslides) constitute only about 1% of all pixels in the training set and 0.7% in the validation set. This extreme imbalance makes conventional accuracy metrics misleading, as a naive model could achieve high accuracy by simply predicting the majority class.

To address this, our models prioritize IoU (Intersection over Union) as the primary performance metric rather than accuracy. Furthermore, we experimented with different loss functions and architectural improvements to improve segmentation of the rare positive class. One key strategy is the use of multi-input features, which has been shown to help models focus on small, sparse signals and alleviate class imbalance.

The performance ranking of the models based on IoU is as follows:

1. bse+input+lr – best performance

2. input+focal+lr – strong performance, selected for final analysis

3. Model without multi-input – baseline performance

Here, input refers to the multi-input design, which significantly improves the model's ability to capture subtle landslide features in highly imbalanced datasets. The use of focal loss and learning rate adjustments further enhances the segmentation of rare positive pixels. Overall, these strategies allow the models to effectively detect landslides despite the extreme class imbalance.
