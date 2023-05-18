# FTIR spectroscopy of biofluids

Introduction
---------
In this study, we evaluate a protocol for predicting biochemical parameters of blood using Di-ATR FTIR analysis of biological fluids. 
This work consists of two main part, one is dedicated towards prediction of biochemical parameters of blood via various regression techniques, as well as CNN was trained for this purposes. The second part is dedicated towards classification of mice urine samples into cirrhotic and control groups.

Main part
---------
##### ML for blood analysis


A dataset consisting of 140 blood samples was collected and registered. To increase the dataset size, a 100-fold augmentation was performed. Various ML methods were employed to create regression models for each parameter, calculating the %RMSE as an evaluation metric. Additionally, feature selection techniques were applied to enhance model performance. Through the analysis, satisfactory %RMSE values for the predicted parameters were obtained.  


|            | Linear Regression | Lasso Regression | Support Vector Regression | Random Forest Regression | Gradient Boosting Regression |
|------------|-------------------|-----------------|---------------------------|--------------------------|-----------------------------|
| ALT        | 43.481            | 44.475          | 29.517                    | 6.298                    | 22.735                      |
| AMYLASE    | 37.348            | 38.082          | 21.913                    | 3.365                    | 15.441                      |
| AST        | 25.054            | 26.529          | 18.575                    | 2.897                    | 14.578                      |
| PROTEIN    | 5.150             | 5.558           | 2.296                     | 0.718                    | 2.391                       |
| BILIRUBIN  | 46.558            | 49.261          | 36.855                    | 5.849                    | 23.818                      |
| GAMMA-GT   | 74.686            | 75.531          | 64.903                    | 12.973                   | 35.963                      |
| IRON       | 41.944            | 42.963          | 31.076                    | 2.614                    | 19.833                      |
| CALCIUM    | 3.124             | 3.486           | 2.757                     | 0.236                    | 1.427                       |


##### CNN for blood analysis

Moreover, CNN designed for the predictions also showed some interesting results, for example %RMSE were pretty low for calcium and protein level predictions, while for ALT, bilirubin and gamma-GT were poorly predicted. This suboptimal performance can be attributed to the fact that the architecture employed may not have been the best choice for this particular task, as well as further optimal hyperparameter search may be required.

| blood parameter | dense | dropout | batch size | %RMSE   |
|-----------------|-------|---------|------------|---------|
| AST             | 256.0 | 0.2     | 16.0       | 7.632   |
| ALT             | 256.0 | 0.2     | 32.0       | 15.987  |
| AMYLASE         | 128.0 | 0.4     | 16.0       | 8.756   |
| PROTEIN         | 128.0 | 0.2     | 16.0       | 2.179   |
| BILIRUBIN       | 256.0 | 0.2     | 16.0       | 14.945  |
| CALCIUM         | 128.0 | 0.2     | 16.0       | 2.306   |
| CHOLESTEROL     | 256.0 | 0.2     | 32.0       | 433.040 |
| IRON            | 128.0 | 0.2     | 32.0       | 7.007   |
| GAMMA-GT        | 128.0 | 0.4     | 32.0       | 32.806  |
| URIC ACID       | 256.0 | 0.4     | 16.0       | 7.374   |


##### Classification of urine samples

<img src="https://github.com/OlgaChechekina/FTIR_spectroscopy_of_biofluids/assets/60808830/38860a2b-70ec-475c-a7e5-ecd5eacead52" width="50%">

Furthermore, investigation was expanded by including urine spectra analysis. For the experiment, 35 urine spectra were registered, and 20-fold augmentation was performed. Feature selection techniques were also applied to create a refined dataset, as well as rationale behind the selected features was explained. The resulting dataset was used to construct multiple classification models and gave remarkable accuracies ranging from 0.9 to 1.0 for most of the models.

<img src="https://github.com/OlgaChechekina/FTIR_spectroscopy_of_biofluids/assets/60808830/854128f7-f5d0-41d8-9889-04b23ce2c9ea" width="50%">


Conclusion
---------
Overall, the study contributes to the field of chemometrics by means of FTIR spectroscopy. The findings highlight the significance of feature selection and model selection in achieving accurate predictions. Although the performance of the CNN model fell short of expectations, it presents an opportunity for future research to explore more suitable architectures. The successful classification of cirrhosis using urine spectra further demonstrates the potential of FTIR analysis in biomedical applications, as well as prediction of some of biochemical parameters by means of Random Forest Regression appear to be promising.
In conclusion, this research contributes to the field of FTIR analysis of biological fluids by evaluating and optimizing the protocol for predicting biochemical parameters of blood. The findings serve as a foundation for future investigations, with potential applications in medical diagnostics and disease classification.
