- (i) A 200-300 word explanation of the expected performance of the model in terms of mean
squared error and the key features driving the team’s modeling performance.

The model used for test2 data was Random Forest Regression. We expect a mean square error of roughly 3 million. When predictions were made using RFR on test1 data, the mean square error came out to 3.3 million. Combing that predicated data of roughly 2000 samples with the previous 12000 should somewhat improve the accuracy of our predications. Thus, having more data should bring the mean square error down by a few hundred thousand. Our idea behind using Random Forests was that using an ensemble method would work better on data with a lot of features. However, the Bias-Variance Tradeoff seems to have gotten in the way, as our trees did not beat out linear regression. One of the initial driving factors was we would have enough trees for the forest, so the model would avoid overfitting.



- (ii) A 200-300 word summary outlining the team’s intended strategy to improve the predictions
for the final round.

