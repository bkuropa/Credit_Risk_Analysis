# Credit_Risk_Analysis

## Overview
Several machine learning models are generated and analyzed to better understand the potential and the risks on loan status.  This includes analysis of low_risk and high_risk scenarios.  Credit risk is a large field in the banking industry and critical for organizations aiming to maintain or augment their financial status.  Several models from the Imbalanced-Learn & Scikit-Learn libraries will be implimented to gain perspectives on loan statuses.

## Results
Evaluated largely by Balanced Accuracy Score (0 - 1), Precision (Prec), and Recall (Rec).
### The first technique examined is Naive Random Oversampling
![naive_random_oversampling](https://user-images.githubusercontent.com/19878877/165420985-5c2dbf29-281a-4fdd-bd46-b53f066de6c9.png)
An oversampling technique is a reasonable beginning to model devolpment with a 0.66 Balanced Accuracy Score; Prec = 0.99, Rec. = 0.63.  The large sample contrast between low_risk and high_risk quantities makes this a logical approach to suitable compare the situations.

### The SMOTE oversampling technique is implimented next
![SMOTE](https://user-images.githubusercontent.com/19878877/165421104-85ffdacd-df5e-4b6d-ae71-c0644c2b67fb.png)
The Synthetic Minority Over-sampling Technique is implemented as an attempt to raise the effectiveness of the above NRO.  Balanced Accuracy Score = 0.66; Prec = 0.99; Rec = 0.69.  In this case, the recall is slightly improved (6%) but the other determining parameters are very similar.  Of the two, SMOTE may be slightly better, further balancing the recall.

### Undersampling is also examined
![undersampling](https://user-images.githubusercontent.com/19878877/165421166-9b71c724-0e95-4bae-8b0b-05f6d6973356.png)
Undersampling does not seem overly effective in this case with a Balanced Accuracy Score of 0.54; Prec = 0.99; Rec = 0.40. Though the simplicity of the model was worth investigating, the resuts did not land an effective model.  With a BAS 0.12 lower and a significant diminishing in the recall, the attempt was undesirable.

### Combinination (Over-Under) is now examined utilising SMOTEENN
![SMOTEENN](https://user-images.githubusercontent.com/19878877/165421291-c0cfe032-e92f-4dbd-9759-1e90ef5fb972.png)
The use of SMOTE-ENN yields a BAS = 0.64 (comparible to SMOTE); Prec = 0.99; Rec = 0.59.  For this particular modelling situation, SMOTEENN is not an effective choice.

### A genearl random forest is also examined
![random_forest](https://user-images.githubusercontent.com/19878877/165421359-0bf91c39-ccde-4260-8626-f6d200d3797e.png)
The ensemble random forest shows a clear upgrade from the past attempts with a 0.79 Balanced Accuracy Score; Prec = 0.99; Rec = 0.87.  The bagging of the data included in the loan dataset seems to make good use of the information albeit, it can be a little difficult to track the logic behind the creation of the random forest itself as it takes a trial-and-error approach.

### Lastly, one investigates the AdaBoost model
![adaboost](https://user-images.githubusercontent.com/19878877/165421419-70d7169a-1e20-421b-a618-471b9c616cc7.png)
In this case, AdaBoost shows a clear improvement with a Balanced Accuracy Score of 0.93 which is well beyond that of the other attempts mentioned above.  Prec = 0.99; Rec = 0.94.  The generation of the tree stumps seems to have encountered and applied the most influencial functions (shown below).  There's a good chance 'total_rec_prncp' has the lowest Gini index.  A strong model for sure as it is able to compensate for the erronious classifications during construction.

![feature_importance](https://user-images.githubusercontent.com/19878877/165553484-96aab680-3316-4b32-82fc-ec5d1a5d4c06.png)


## Summary
The first four models implemented were modest in their prediction capibilities towards this application.  Having BAS scores around 60% is not an overly strong achievement but an excellent first step towards understanding.  The ensemble classifiers on the other hand are quite strong for modelling credit risk are quite effective.  The strongest of all the models generated was with the AdaBoost algorithm showing a BAS of 0.93, a Prec of 0.99, and Rec of 0.94.  This method shows a much better balance between precision and recall, resulting in an effective outcome.  It is notable that the original dataset only presented 1% high-risk loans as opposed to the 99% low risk loans.  The process of enlarging/enhancing the dataset may result in the neccessity to further investigate information sources to gain a full understanding of the situation.
