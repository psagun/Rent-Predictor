## (1) Data Usage

```
(a) What outside data have you appended to the original data set? Why did you choose this data?

    We decided to use NYC Department of Buildings' Building Violations and Building Complaints datasets. One reason was that it would be     easy to join to out original dataset, since every complaint/violation was dependent on a bin number. We also assumed that builings       with fewer complaint/violation would be in better neighborhoods or with better managment and therefore have higher rents. Another       assumption was buildings without complaint/violation would be newly built and therefore have higher rents.

(b) Does the inclusion of this additional data raise any ethical considerations?

    The datasets raise no ethical considerations.

```

## (2) Data Exploration.
```
(a) What outliers present issues for your analysis? How have you chosen to handle them? Why?

    The outliers which had the most effect on the model were square feet and rent, since they were strongly correlated. We handled them     by normalizing the dataset and exlcuding the top five percent of rents and square footage. This seemed to be the best way of            ensuring that only the problemtic data points were removed without affecting the overall distribution.

(b) To what extent do missing values pose a challenge for your analysis? How have you chosen to
handle them? Why?

    Missing values were handled in a few different ways: for binary data points, they were all set to zero. Floor count, year built, and     minutes to subway were filled in with the means of the columns. All other were filled in with columns medians. With binary values       like has fireplace or has garage we assumed if someone did offer those ameneities they would want a tenant to know, so missing           values meant they were not availble. Means were used for features they had weaker correlations. Medians seem to be the best             subsitiute for all others.

(c) Are there any other aspects of the data your exploration shows might be problematic?

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
    
  bedroom, square footage, bathroom, no fee, dob complaints
  
(b) Describe how you are implementing your model. Why do you think this works well?
(c) Describe your methodology for selecting your model. Why do you think this type of model works
well?
```

## (4) Metrics, Validation, and Evaluation.
```
(a) How well do you think you model will perform on the hold out test set? How do you know?
(b) Is your model useful? Why or why not?
(c) Are there any special cases in which your model works particularly well or particularly poorly?
(d) Create at least one visualization that demonstrates the predictive power of your model.
```
## (5) Conclusion
```
(a) How would you use this model?
(b) If you could have additional modeling features, what would they be?
(c) Would you rather have more data, or more features?
```
