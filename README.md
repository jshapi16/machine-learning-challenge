# machine-learning-challenge
Using ML to classify candidate exoplanets. 

### Project Intro
When astronomers see objects in space, how can they tell whether or not the object is an exoplanet? Using the exoplanet dataset from, [Kaggle Exoplanet dataset](https://www.kaggle.com/nasa/kepler-exoplanet-search-results), this repository trains a gridsearch model and a deep learning model to determine whether it's possible to predict exoplanets from the observation of the space object.

### Project Setup
#### Grid Search
The model begins with a RandomForestClassifier to select most impactful features. Although these features may not be the most impactful when not using a Random Forest model, it helepd narrow the data to preform a grid search. 
Selected the top 5 features, isolated training and testing data, scaled it using a MinMaxScaler and ran the grid search. 

![Grid Search Setup](https://github.com/jshapi16/machine-learning-challenge/blob/main/images/grid_search_setup.png?raw=true)

Figure 1

Running the grid search using the top five features from the RandomForestClassifier did not yield a promising model, only 75% accuracy. Perhaps selecting the features from Random Forest Classifier did not yield the best results in a Grid Search model, but also finding objects in space requires immense precision so the next step uses a Deep Learning Model.

![Running Grid Search](https://github.com/jshapi16/machine-learning-challenge/blob/main/images/grid_search_model.png?raw=true)

Figure 2

![Grid Search Results](https://github.com/jshapi16/machine-learning-challenge/blob/main/images/grid_search_results.png?raw=true)

Figure 3


#### Deep Learning Model
While the overall model is different, in the setup for the Deep Learning Model, all the main features were used, excluding the features that were error measurements of the main features. 

![Deep Learning Setup](https://github.com/jshapi16/machine-learning-challenge/blob/main/images/deep_learning_setup.png?raw=true)

Figure 4

Used OneHotEncoding, to encode the y values (there were three values) and scaled the data to set up the full model. 

Added three layers using tensorflow.keras Dense and added a callback to the fit of the model created an overall accuracy of 85%. 

![Deep Learning Model Setup](https://github.com/jshapi16/machine-learning-challenge/blob/main/images/deep_learning_model_setup.png?raw=true)

Figure 5

![Deep Learning model outcome](https://github.com/jshapi16/machine-learning-challenge/blob/main/images/deep_learning_model_outcome.png?raw=true)

Figure 6 


### Conclusion
Overall this model fairly accurately predicts whether an observed mass in space is an exoplanet, but it could still be improved with additional fiddling of the models and features. 
