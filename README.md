# Prediction-of-Product-Sales

This project analyzes data related to food items sold at various stores. The insights gained will help retailers understand what factors can help increase sales.

## Figure Preview

**The below figure shows a positive correlation between ItemMRP and ItemOutletSales. As ItemMRP increases, so does the ItemOutletSales.**

![ItemMRP_V_ItemOutletSales_regplot_week3](https://github.com/IndiaTJohnson/Prediction-of-Product-Sales/assets/12077809/aec4aee0-d312-422e-a82b-4ffa77cd06c1)

**The figure below is a heatmap of feature correlations of the numerical data in the dataset. Interestingly, OutletEstablishmentYear and ItemWeight have a moderately strong positive correlation.**

![Correlation_Heatmap_week3](https://github.com/IndiaTJohnson/Prediction-of-Product-Sales/assets/12077809/547dba95-13c7-4bee-8fdc-b4ca9d22ec3d)

###**ML Model**

In this project, we are currently using a tuned Random Forest Regression model. Overall I recommend the tuned random forest model. Of the parameters I tested, these gave me the best results: {'randomforestregressor__max_depth': None, 'randomforestregressor__max_features': 'sqrt', 'randomforestregressor__min_samples_leaf': 3, 'randomforestregressor__n_estimators': 200, 'randomforestregressor__oob_score': True}

The above model gave me an R^2 value of 0.734 on the training data and 0.588 on the test data, which was better than both the linear regression model and the default random forest model.

The R^2 value represents the percentage of variation that a model can explain. In other words, the R^2 value explains how well a model predicts the target values. So a score of .588 means the model can account for about 59% of the variation in your target values using your feature values. Generally, a higher R^2 is better.

Mean Absolute Error (MAE) measures error by using the absolute values of all the errors a model makes so positive and negative errors don't cancel each other out and make the overall error seem less than what it is. The lower the MAE is, the better.

Mean Squared Error (MSE) squares the error values as opposed to taking the absolute values. Squaring the error values automatically makes them positive, so error canceling due to a negative error does not occur. MSE punishes larger errors more than smaller errors, as an error twice as large results in a penalty that is four times higher. We would rather have smaller errors than less very large errors, and MSE is good at detecting large errors. The lower the MSE, the better.

Root Mean Squared Error (RMSE) is like the best of both worlds when compared to MAE and MSE. It takes the square root of the MSE (mean squared error). This means it punishes large errors and is expressed in the same units as the target, making it easier to interpret. The lower the RSME, the better.
