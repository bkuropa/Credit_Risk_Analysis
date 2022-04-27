# Credit_Risk_Analysis

## Overview
Several machine learning models are generated and analyzed to better understand the potential and the risks on loan status.  This includes analysis of low_risk and high_risk

## Results
### The first technique examined is Naive Random Oversampling
![naive_random_oversampling](https://user-images.githubusercontent.com/19878877/165420985-5c2dbf29-281a-4fdd-bd46-b53f066de6c9.png)
An oversampling technique is a reasonable beginning to model devolpment with a 0.66 Balanced Accuracy Score.  The large sample contrast between low_risk and high_risk quantities makes this a logical approach to suitable compare the situations.

### The SMOTE oversampling technique is implimented next
![SMOTE](https://user-images.githubusercontent.com/19878877/165421104-85ffdacd-df5e-4b6d-ae71-c0644c2b67fb.png)


### Undersampling is also examined
![undersampling](https://user-images.githubusercontent.com/19878877/165421166-9b71c724-0e95-4bae-8b0b-05f6d6973356.png)
Undersampling does not seem overly effective in this case with a Balanced Accuracy Score of 0.54. Though the simplicity of the model was worth investigating, the resuts did not land an effective model.

### Combinination (Over-Under) is now examined utilising SMOTEENN
![SMOTEENN](https://user-images.githubusercontent.com/19878877/165421291-c0cfe032-e92f-4dbd-9759-1e90ef5fb972.png)


### A genearl random forest is also examined
![random_forest](https://user-images.githubusercontent.com/19878877/165421359-0bf91c39-ccde-4260-8626-f6d200d3797e.png)
The ensemble random forest shows a clear upgrade from the past attempts with a 0.79 Balanced Accuracy Score.  The bagging of the data included in the loan dataset seems to make good use of the information albeit, it can be a little difficult to track the logic behind the creation of the random forest itself as it takes a trial-and-error approach.

### Lastly, one investigates the AdaBoost model
![adaboost](https://user-images.githubusercontent.com/19878877/165421419-70d7169a-1e20-421b-a618-471b9c616cc7.png)
In this case, AdaBoost shows a clear improvement with a Balanced Accuracy Score of 0.93 which is well beyond that of the other attempts mentioned above.  The generation of the tree stumps seems to have encountered and applied the most influencial functions (shown below).  There's a good chance 'total_rec_prncp' has the lowest Gini index.  A strong model for sure as it is able to compensate for the erronious classifications during construction.

![feature_importance](https://user-images.githubusercontent.com/19878877/165553484-96aab680-3316-4b32-82fc-ec5d1a5d4c06.png)


## Summary

