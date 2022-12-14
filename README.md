# Práctica Kaggle APC UAB 2022-23
### Nombre: Joel Sánchez de Murga Pacheco 
### DATASET: Mushroom Classification
### URL: [Kaggle](https://www.kaggle.com/datasets/uciml/mushroom-classification)
## Resumen
Este dataset contiene datos sobre diferentes especies de champiñones, una parte són venenosos y los otros comestibles. Esta diferencia esta basada en la distribución de los 22 atributos que la componen.
Tenemos 8192 datos con 22 atributos cada dato. Todos los atributos són categoricos.
### Objectivos del dataset
Queremos poder classificar de manera correcta los champiñones para poder saber cual es venenoso y cual es comestible.
## Experimentos
Hemos realizado diferentes pruebas con diferentes modelos. Las hemos realizado tanto escalando los datos con y sin PCA, y sin escalar los datos con y sin PCA. En este notebook solo vereis representados los datos escalados con y sin PCA, ya que estos generan una mayor accuracy respecto los datos sin escalar.
Ademas que todos los modelos han sido testeados con *GridSearchCV* para poder implementar los mejores hiperparametros posibles.
### Modelos
| Modelos | Hiperparametros | Test Accuracy |
| -- | -- | -- |
| Decision Tree Classifier (Sin PCA) | ccp_alpha=0.001 criterion='entropy' max_depth=9 max_features='auto' | 99.92% |
| Logistic Regression (Sin PCA) | c=1000 penalty='l2' | 97.79% |
| SVM (Sin PCA) | C=0.75 decision_function_shape='ovo' gamma=1 kernel='rbf' | 99.63% |
| KNN (Sin PCA) | metric='euclidean' n_neighbors=3 wrights='uniform' | 99.96% |
| Random Forest (Sin PCA) | n_estimators=200 criterion='gini' max_depth=8 max_features='auto' | 99.96% |
| -- | -- | -- |
| Decision Tree Classifier (Con PCA) | ccp_alpha=0.001 criterion='gini' max_depth=7 max_features='auto' | 92.98% |
| Logistic Regression (Con PCA) | c=0.1 penalty='l2' | 65.42% |
| SVM (Con PCA) | C=2 decision_function_shape='ovo' gamma=1 kernel='rbf' | 94.30% |
| KNN (Con PCA) | metric='manhattan' n_neighbors=11 wrights='distance' | 93.56% |
| Random Forest (Con PCA) | n_estimators=500 criterion='gini' max_depth=8 max_features='auto' | 94.30% |
## Conclusiones
Los mejores modelos han sido *KNN (Sin PCA)* y *Random Forest (Sin PCA)* con un 99.96% seguido de *Decision Tree Classifier (Sin PCA)* con un 99.92% de *Accuracy*.
## Licencia
El proyecto se ha desenvolupado bajo la licencia de CC0: Public Domain.
