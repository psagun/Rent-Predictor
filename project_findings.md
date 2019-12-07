## (1) Data Usage

```
(a) What outside data have you appended to the original data set? Why did you choose this data?

    We decided to use NYC Department of Buildings' Building Violations and Building Complaints datasets. One 
    reason was that it would be easy to join to out original dataset, since every complaint/violation was 
    dependent on a bin number. We also assumed that builings with fewer complaint/violation would be in better 
    neighborhoods or with better managment and therefore have higher rents. Another assumption was buildings 
    without complaint/violation would be newly built and therefore have higher rents.

(b) Does the inclusion of this additional data raise any ethical considerations?

    The datasets raise no ethical considerations.

```

## (2) Data Exploration.
```
(a) What outliers present issues for your analysis? How have you chosen to handle them? Why?

    The outliers which had the most effect on the model were square feet and rent, since they were strongly 
    correlated. We handled them by normalizing the dataset and exlcuding the top five percent of rents and 
    square footage. This seemed to be the best way of ensuring that only the problemtic data points were 
    removed without affecting the overall distribution.

(b) To what extent do missing values pose a challenge for your analysis? How have you chosen to
handle them? Why?

    Missing values were handled in a few different ways: for binary data points, they were all set to zero. 
    Floor count, year built, and minutes to subway were filled in with the means of the columns. 
    All other were filled in with columns medians. With binary values like has fireplace or has garage we 
    assumed if someone did offer those ameneities they would want a tenant to know, so missing values meant 
    they were not availble. Means were used for features they had weaker correlations. Medians seem to be the 
    best subsitiute for all others.

(c) Are there any other aspects of the data your exploration shows might be problematic?

    Our distribution plots and scatter plots show a large number of listings have square footage in the range 
    of 500 and 1500. While not that big of an issue in our current test sets, this could be a problem if we 
    start seeing alot of listing outside of this range. These "clusters" could cause significant deviations in another dataset.

(d) Create at least one visualization that demonstrates the predictive power of your data.

    Please see the Jupyter Notebook for visualizations.

```
## (3) Transformation and Modeling.
```
(a) Describe 5 features you think play the biggest role in your model.
• How did you create these features?
• How do you know these features are playing key roles?
If your modeling process uses less than five features, explain why you think other features didn’t
add value.
    
  square footage, bathroom, floor count, has doorman, has gym
  These features all had the high Pearson Correlation between them and rent in the training dataset.
  All the other features we used had much weaker correlations, even the ones we would expect to have high such
  bedrooms and has pool.  
  
(b) Describe how you are implementing your model. Why do you think this works well?
    
    The model is currently being implmented by fitting the training data on the model directly. By elimianting
    outliers and filling in missing values, we have sufficently "good" data, there is no current need
    to split and validate it. 
    
(c) Describe your methodology for selecting your model. Why do you think this type of model works
well?
    The idea behind using Random Forests was that using an ensemble method would work better on data with a 
    lot of features. However, because of the Bias-Variance Tradeoff seems to have gotten in the way, as our 
    trees did not perform as well as we would have hoped. Another major reason was that that decision treestake 
    into account interactions between variables automatically, wheras a model like linear regression cannot. 
    Decision tree also allow non-linear data, wheras more linear model are limited in this approach.
    
```

## (4) Metrics, Validation, and Evaluation.
```
(a) How well do you think you model will perform on the hold out test set? How do you know?

    This model will probably perform well on the hold out test set. The low mean score error we obtained would
    indicate the our models is performing well. The hold out test set should be a good sub-sample, and since 
    the model worked well on the lower quality training data, there should be no issues with the test set.
    
(b) Is your model useful? Why or why not?

    The model is useful because it is accurate. The low MSE means we are close to the actual values (based on test1).
    Furthermore, random forest regression is actually used to predict housing prices by businesses. so it should be 
    useful.
    
(c) Are there any special cases in which your model works particularly well or particularly poorly?

    Our model work particularyly well for listings having square footage in the range of 500 and 1500. We see a large 
    cluster around here during the data exploration. However, this could become problematic if we start seeing a large 
    number of listings outside this range. Real estates prices are not really linear (as demontrated through our current 
    datasets) so our current model may not scale well for listing of particularly large sizes.

(d) Create at least one visualization that demonstrates the predictive power of your model.

    Please see the Jupyter Notebook for visualizations.
    
```
## (5) Conclusion
```
(a) How would you use this model?

    This model works well for listing of less than 5 bedrooms, 4 bathrooms, and less than 2300 square footage. So we would 
    continue to use this for for predicting rent prices.

(b) If you could have additional modeling features, what would they be?

    property value of the building, previous rents for the buildings, occupancy rates
    
(c) Would you rather have more data, or more features?

    We would rather have more features that have stringer correlations to the rent. We currently have almost around 16,000
    data points (including training, test1, test2). More data would not be that much more helpful, unlike more useful features.
    
```
