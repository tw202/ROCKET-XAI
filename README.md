# ROCKET-XAI
This repo contains the code that was part of a Masterthesis to develop an XAI method for Time series classification with ROCKET[1]. The purpose of this repository is to provide the python notebook to reproduce the results and idealy further develop the explainability of ROCKET.

# Notes
The whole experimental study was conducted in the google collaboratory environment (free version). If desired other data than the artificially generated can be used. The code is heavily commented, to help the usability of the fragments, although this is not a good practise in a clean code of sense.

# Structure
## Parameters setting
Here the parameters can be set to define which of the different developed/tested XAI methods should be run. Furthermore needed directories will be created in the collab environment. This sections also provides some additional parameters that were not part of the paper like e.g. reducing the number of important kernels that are used to generate the relevance vectors. Users are animated to explore those parameters and test if they work or how they behave. 

## Creating data
As the name says this section creates the dataset that is used in the process of XAI development. It is a time series dataset with 200 instances based on a sine wave signal that is divided into two classes of which one has an anomaly for a discriminative sub series. The data is scaled across the features space as needed to use ROCKET. Although the sktime implementation of ROCKET automatically does that before transforming the data, this feature was not used, but the data is scaled in the next section. 

## Predict and apply XAI
In this section the data is scaled, transformed by ROCKET (only ppv features are used in the further process) and predictions are made by the KNeighbors Classifier. After that shap values are calculated for each ppv feature and the important kernels are then re-applied to extract the used weight values and to calculate a relevance vector for each instance of the test set. For each instance a plot is generated that shows the relevance of each time point as a heatmap.

## Quantitative evaluation 

In this section the metric relevance mass accuracy is calculated [2] and a pertubation method[3] is shortly tested

# References
[1]A. Dempster, F. Petitjean, and G. I. Webb, “Rocket: exceptionally fast and
accurate time series classification using random convolutional kernels,”
Data Mining and Knowledge Discovery, vol. 34, no. 5, pp. 1454–1495,
2020.

[2]L. Arras, A. Osman, and W. Samek, “Clevr-xai: A benchmark dataset for
the ground truth evaluation of neural network explanations,” Information
Fusion, vol. 81, pp. 14–40, 2022.

[3]U. Schlegel, H. Arnout, M. El-Assady, D. Oelke, and D. A. Keim,
“Towards a rigorous evaluation of xai methods on time series,” in 2019
IEEE/CVF International Conference on Computer Vision Workshop (IC-
CVW). IEEE, 10/27/2019, pp. 4197–4201.
