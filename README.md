# Emotion Recognition of Images
The project aimed at detecting anger emotion in images using Genetic Algorithm for feature selection and Logistic Regression, Support Vector Machine (SVM) and K-Nearest Neighbor (KNN) for classification.

### Dataset
The models were trained on the Extended Cohn-Kanade Dataset (CK+) consisting of 651 grey scale images of 48x48 resolution. Based on the emotion labels, the images were grouped into 2 classes - anger and not anger - and were then passed through OpenFace to extract features. Finally csv files with 711 features were obtained for each image.

### Methodology
The genetic algorithm acts like a wrapper function over the classifier and uses the accuracy obtained from the classifier as the fitness function. In each generation, the classifier was trained on CK+ dataset for all feature subsets present in the population and the accuracies obtained were used to generate the next population. The population was represented using a string of 0s and 1s. If an index contains 0, the corresponding feature was not included in the subset and if it contains 1, the corresponding feature was used for training the classifier. 
