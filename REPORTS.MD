# Report 01:
- Branch: Main
- Resume: Inicio dos treinamentos dos modelos de regressão, sem tratamentos, apenas preenchimento de campos vazios e criação de colunas para dados nominais
- Results:

Model | MSE | MAE | R^2 |
------|----|-----|-----|
Regressão Linear | 11506965226.9626   | 4827.8988 | -0.4680 |
Random Forest | 4934797656.7463 | 1412.3837 | 0.3704 |
KNN | 7831743813.4294 | 9396.8295 | 0.0008 |



# Report 02:

- Branch: Main
- Resume: Transformação da target utilizando função logarítmica
- Results:

| Model | MSE | MAE | R^2 |
| --- | --- | --- | --- |
| Regression | 9.884347e+17 | 12444764.62 | -1059080630.59 |
| Random Forest | 142208902.25 | 1758.0319 | 0.8476270737 |
| KNN | 961896561.52 | 5896.2910 | -0.03064570167 |


# Report 03:

- Branch: Pipeline
- Resume: Utilização de pipelines para evitar _dataleak_ e mais Transformações logarítmicas, nas features `['goal','total_posts','total_contributions','total_contributors']`
- Results:

| Model | MSE | MAE | R^2 |
| --- | --- | --- | --- |
| Regressão Linear | 1859319859.0239 | 6951.067 | -0.9922 |
| Random Forest | 101975042.2319 | 1549.544 | 0.8907 |
| KNN | 960700231.9057 | 5893.638 | -0.0294 |
| Gradient Boosting | 448086994.2584 | 2176.940 | 0.5199 |


# Report 04:

- Branch: Pipeline
- Resume: Uso de `StandardScaler` e `MinMaxScaler` dentro do processo da Pipeline
- Results:

| Model | MSE | MAE | R^2 |
| --- | --- | --- | --- |
| Regressão Linear | 1859319979.9410 | 6951.0671 | -0.9922 |
| Random Forest | 110502829.9716 | 1565.7464 | 0.8816 |
| KNN | 370944798.2366 | 1951.4408 | 0.6025 |
| Gradient Boosting | 448060618.4273 | 2175.7289 | 0.5199 |