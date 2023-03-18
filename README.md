# Image-Classification-ML
## **Machine Learning Project: Image Classification**

In this project the MNIST dataset is used to build and evaluate the performance of different machine learning models for image classification. The goal of this project is to classify each image into one of the numbers.

### **Dataset**

The MNIST dataset includes `70,000 images` of handwritten digits (0-9) with a resolution of **28x28** pixels. The distribution of digits in the dataset is shown in a bar plot.

### **Project**

First of all, the MNIST data set is loaded using `fetch_openml()` method. 
Then, I inspected the dataset using it `keys()`. First ten image is displayed using `imshow()` method. 
Also, the distrubition of the digits is showed. Lastly, the dataset is splitted to the train and test sets.

First machine learning model is builded using SVM's classifier that is SVC. 
Since SVM is good at small and medium size of the dataset, I just used `10.000` image to train the model. 
After training the model, I evaluated the model using `classification_report()` method. Also, the confusion matrix is showed. Its accuracy evaluated as `96.14%`

Second classifier used Random Forest with 100 estimators. It was trained using whole training set. 
The performance of the classifier is evaluated using the accuracy score and the confusion matrix.
Its accuracy is evaluated as `96.73%`.

The third classifier is builded using Voting Classifier that combines the SVM and RF classifiers.
It is trained with first 20,000 images. The `soft` voting strategy is used instead of `hard` voting.
Its performance was better than previous two model, with `96.93%` accuracy.

The hyperparameters of the SVM and RF classifiers are then tuned using the `GridSearchCV` function. 
The best hyperparameters are found for each classifier, and the classifiers are retrained on the training set with the tuned hyperparameters.
As a result, small improvements is acquired.

Finally, the tuned SVM and RF classifiers are combined into a Voting Classifier.
Its accuracy is evaluated as `98.25%`.

### **Conclusion**

The SVM and RF models achieve similar accuracy on the MNIST dataset, but the ensemble model achieves the best results. The hyperparameter tuning improves the performance of the SVM and RF models. 