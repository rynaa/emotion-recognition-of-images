# Emotion Recognition of Images
The project aimed at detecting anger emotion in images using Genetic Algorithm for feature selection and supervised learning techniques like Logistic Regression, Support Vector Machine (SVM) and K-Nearest Neighbor (KNN) for classification.

### Dataset
The models were trained on the Extended Cohn-Kanade Dataset (CK+) consisting of 651 grey scale images of 48x48 resolution. Based on the emotion labels, the images were grouped into 2 classes - anger and not anger - and were then passed through OpenFace to extract features. Finally csv files with 711 features were obtained for each image.

### Methodology
The genetic algorithm acts like a wrapper function over the classifier and uses the accuracy obtained from the classifier as the fitness function. In each generation, the classifier was trained on CK+ dataset for all feature subsets present in the population and the accuracies obtained were used to generate the next population. The population was represented using a string of 0s and 1s. If an index contains 0, the corresponding feature was not included in the subset and if it contains 1, the corresponding feature was used for training the classifier. 

![Blank diagram-3](https://user-images.githubusercontent.com/40691704/109348342-d38eb900-788d-11eb-96bb-f1424514ce3e.png)

### Experiments
- Classifiers :
We used 3 different classifiers to experimentally determine which model would work the best for this particular dataset including Logistic Regression, SVM and KNN method. We found out that for this particular dataset, logistic regression was generally giving the better results after fine tuning the parameters.
 
- Selection :
We used 4 different selection processes - Roulette Wheel, Ranking and Tournament.

- Crossover :
We tried out 3 different crossover techniques - Single Point, Two Point and Uniform crossover. In a single point crossover, a random crossover point is selected and the halves of the parents swapped. In two point crossover, two random crossover points are selected and alternate parts are swapped between the two parents. In uniform crossover, a random masking string is generated and is used for selecting features from the two parents. 

- Mutation :
We tried two different types of mutation techniques namely - Bit Flip and Bit Swap. In bit flip, a random feature’s value was inverted (0 -> 1 and 1-> 0) for a random subset in the population. In bit swap, we choose two random subsets in the population and swap their values for a random feature. 


### Results
On testing the model on CK+ dataset, an accuracy of 98% was achieved. However, when tested on personal photographs, the accuracy decreased to 83% because of the demographic differences. 
| Test Set  | Accuracy |
| ------------- | ------------- |
| 80-20 Split on CK+ Data  | 98%  |
| Testing on our images  | 83%  |
