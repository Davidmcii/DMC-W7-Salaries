# DMC-W7-Salaries

Se realiza una predicción de Kaggle para determinar el sueldo de una persona que trabaja en el sector del data analytics tomando como base los datos proporcionados. Estos datos tienen 500 datos con el resultado de salarios mientras que otro dataset no dispone de los salarios. El objetivo es intentar predecir el resultado de los salarios.

Explorando el dataset con los salarios, se encuentra que: 

Cómo varía el salario dependiendo del rol:

<img width="700" alt="1" src="https://raw.githubusercontent.com/Davidmcii/DMC-W7-Salaries/main/3-Plots/salary_role.png">



Estos roles se simplifican y se deja en 4 categorías:

<img width="700" alt="1" src="https://raw.githubusercontent.com/Davidmcii/DMC-W7-Salaries/main/3-Plots/salary_role_simpl.png">

El sueldo medio de cada categoría es: 

<img width="700" alt="1" src="https://raw.githubusercontent.com/Davidmcii/DMC-W7-Salaries/main/3-Plots/salary_roleAVG.png">

Cómo varía el salario dependiendo del rol:

<img width="700" alt="1" src="https://raw.githubusercontent.com/Davidmcii/DMC-W7-Salaries/main/3-Plots/salary_expertise_evg.png">

Se revisa como varía el sueldo según el país:

<img width="1000" alt="1" src="https://raw.githubusercontent.com/Davidmcii/DMC-W7-Salaries/main/3-Plots/salary_country.png">

Revisamos como varía el salario con el tamaño de la empresa:

<img width="700" alt="1" src="https://raw.githubusercontent.com/Davidmcii/DMC-W7-Salaries/main/3-Plots/salary_comSize.png">

## Transformaciones: 

1- Se quitan los outlayers. Se ejecuta el código con diferentes resultados dejando <200k, <250k y el data set tal como es sin quitar ningún valor. 
2- Se incluye el coste de vida de cada uno de los países como un valor. Los datos recogidos corresponden a un archivo de kaggle: 

https://www.kaggle.com/code/olgaluzhetska/cost-of-living-analysis

Al cual le ajusté valores para que se adaptase mejor al salario medio de cada país. 

El coste de vida se usó tanto en el país donde está ubicada la empresa así como donde está el trabajador. 

3-Ajusté el salario según la media del expertise según el puesto. 
4- ajusté el teletrabajo para hacerle separación por dummies y que no fuese numérico 100/50/0. 
5- Ajusté el año para hacerle separación por dummies y que no fuese numérico 2022/2021/2020
6- Se eliminaron las columnas employment_type, employee_residence, company_location, work_year y company_size. sEgún el modelo se probó a dejarlas o eliminarlas. 

Finalmente se realizó un ajuste de machine learning con los siguientes modelos: 

LogisticRegression 
rain_test_split
LinearRegression  
Lasso
Ridge
ElasticNet
RandomForestRegressor
ExtraTreeRegressor
GradientBoostingRegressor
XGBRegressor
CatBoostRegressor
LGBMRegressor

y se analiza tanto en la muestra como el test los valores de: 

mean_squared_error
r2_score

## Resultados: 

Finalmente se consiguen estos valores para cada uno de los modelos: 

<img width="700" alt="1" src="https://raw.githubusercontent.com/Davidmcii/DMC-W7-Salaries/main/3-Plots/Results.PNG">

El modelo que se ha entendido como mejor ajustado han sido Ridge al estar mejor fitteado y dar una predicción en el test mejor que el resto de modelos.

Con este, se ven los valores depende principalmente de: 

<img width="700" alt="1" src="https://raw.githubusercontent.com/Davidmcii/DMC-W7-Salaries/main/3-Plots/result1.png">

La distribución de salarios por experiencia es: 

<img width="700" alt="1" src="https://raw.githubusercontent.com/Davidmcii/DMC-W7-Salaries/main/3-Plots/output.png">

Por otro lado, la distribución de experiencia por role es: 

<img width="700" alt="1" src="https://raw.githubusercontent.com/Davidmcii/DMC-W7-Salaries/main/3-Plots/result_Salary_country.png">





