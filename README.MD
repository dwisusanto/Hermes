# Report Supervised Learning
### (dataset: Churn Prediction)

### Kelompok 5 - Hermes
Anggota:
* Dwi Susanto
* Mhd Fahmi Aziz
* Nur Ayu Asyifa
* Andre Yudha P
* Raden Roro Intan Dwi Nuraini


## Modeling
### Tuliskan Eksperiment
Eksperimen yang dilakukan dengan uji coba angka undersampling, oversampling, dan smote yang berbeda (antara 0.3-0.5) pada tahap class imbalance. Model evaluation yang digunakan adalah recall dengan mempertimbangkan precision. Hal ini dikarenakan nilai false negative tidak boleh lebih besar pada kasus churn prediction. Jika nilai false negative besar, maka customer yang mengalami churn tidak dihitung dalam prediksi dan tidak mendapatkan penangan dari pemilik bisnis. Hal ini dapat mengakibatkan pengurangan customer pada suatu bisnis. Nilai train dan test pada precision dan recall yang tergolong baik yaitu diatas 0.5. 
### Split Data Train dan Test
* Perbandingan train set dan test set yang digunakan untuk training model dan evaluasi model adalah 70:30
* Total rows & column of train set: (2828, 30)
* Total rows & column of test set: (1212, 30)
### Modelling (Algoritma yang dipilih)
Algoritma yang dipilih untuk melatih data Churn E commerce adalah Decision Tree, K-Nearest Neighbor, Random Forest, Logistic Regression, dan XGboost. 
Hal ini dikarenakan algoritma Decision Tree, K-Nearest Neighbor, Random Forest, Logistic Regression, dan XGboost dapat memberikan perhitungan terbaik untuk memprediksi customer yang akan churn.
### Model Evaluation : Pemilihan dan Perhitungan Metrics
Model evaluation yang digunakan adalah recall dengan mempertimbangkan precision. Hal ini dikarenakan nilai false negative tidak boleh lebih besar pada kasus churn prediction. Jika nilai false negative besar, maka customer yang mengalami churn tidak dihitung dalam prediksi dan tidak mendapatkan penangan dari pemilik bisnis. Hal ini dapat mengakibatkan pengurangan customer pada suatu bisnis. Nilai train dan test pada precision dan recall yang tergolong baik yaitu diatas 0.5. 
#### Hasil Decision Tree sebelum hyperparameter tuning sebagai berikut:  
* Precision (Train Set): 0.90
* Precision (Test Set): 0.60
* Recall (Train Set): 0.82
* Recall (Test Set): 0.80
#### Hasil K-Nearest Neighbor sebelum hyperparameter tuning sebagai berikut:  
* Precision (Train Set): 0.82
* Precision (Test Set): 0.77
* Recall (Train Set): 0.42
* Recall (Test Set): 0.31
#### Hasil Random Forest sebelum hyperparameter tuning sebagai berikut:  
* Precision (Train Set): 1.00
* Precision (Test Set): 0.92
* Recall (Train Set): 1.00
* Recall (Test Set): 0.75
#### Hasil Logistic Regression sebelum hyperparameter tuning sebagai berikut:  
* Precision (Train Set): 0.82
* Precision (Test Set): 0.71
* Recall (Train Set): 0.71
* Recall (Test Set): 0.59
#### Hasil XGboost sebelum hyperparameter tuning sebagai berikut:    
* Precision (Train Set): 0.90
* Precision (Test Set): 0.62
* Recall (Train Set): 0.81
* Recall (Test Set): 0.81
### Model Evaluation : Apakah Model Sudah Best Fit?
Belum best fit karena gap antara tes set dengan train set masih melebihi 0,05.
### Hyperparameter Tuning
Algoritma terbaik yang dipilih adalah XGboost karena nilai precision test set > 0.5 (memenuhi kriteria ideal) dan nilai recall train set dan test set > 0.5 (memenuhi kriteria ideal).
Hyperparameter tuning yang dilakukan berpengaruh kepada model yang telah dipilih. Nilai parameter yang digunakakan untuk mendapatkan model yang best fit adalah sebagai berikut. Nilai max_depth, min_child_weight, dan gamma akan berpengaruh pada kompleksitas model. Nilai dari masing-masing parameter sebagai berikut:
* Best max_depth: 3
* Best min_child_weight: 3
* Best gamma: 1
* Best tree_method: approx
* Best colsample_bytree: 0.6000000000000001
* Best eta: 0.28391959798994976
* Best num_round: 103
* Best lambda: 0.03535353535353536
* Best alpha: 0.0
### Hasil dari hyperparameter tuning sebagai berikut:
* Accuracy (Train Set): 0.93
* Accuracy (Test Set): 0.88
* Precision (Train Set): 0.90
* Precision (Test Set): 0.62
* Recall (Train Set): 0.81
* Recall (Test Set): 0.81
* F1-Score (Train Set): 0.85
* F1-Score (Test Set): 0.71
* AUC (Train Set): 0.89
* AUC (Test Set): 0.85
## Feature Importance
### Feature Important
Feature yang dianggap paling penting yaitu Tenure, OrderCat, dan DaySinceLastOrder.
Hal ini menunjukkan bahwa feature tersebut berpengaruh untuk customer tidak melakukan churn. Semakin besar nilai feature Tenure, OrderCat, dan DaySinceLastOrder maka customer tidak melakukan churn. 
Action items yang dapat  dilakukan adalah memberikan cashback terhadap customer yang berpotensi melakukan churn. Selain itu, pemilik bisnis dapat meningkatkan kualitas staff (meningkatkan kompetensi staff dalam melayani customer terutama customer yang melakukan complain).

### Feature selection
* Hasil dari feature selection setelah iterasi sebagai berikut: 
* precision (Train) :1.0
* precision (Test) :0.8722222222222222
* recall (Train) :0.9816993464052287
* recall (Test) :0.7302325581395349
* AUC (Train) :0.9908496732026144
* AUC (Test) :0.8535816752583333
* Feature selection setelah iterasi memiliki peningkatan nilai precision test, namun nilai recall testnya menurun.
