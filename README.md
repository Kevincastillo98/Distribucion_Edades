# Distribucion de edades

El siguiente código muestra la distribucion de edades de un dataset 

Para dicho análisis se implementó la librería de **pandas** 
la cual nos permite trabajar con dataframes, de igual forma se implementó la libería re, la cuál nos permitirá extrar espresiones regulares.

- Lectura del csv

``` python
import  pandas as pd
import seaborn as sns
import  matplotlib.pyplot as plt
import re

df = pd.read_csv('edad_ingreso_sem.csv')

```

- Extracción de fecha de nacimiento,usando expresiones regulares

``` python

df['RFC_year'] = df['RFC'].str.extract('(\d{2})', expand=True)
df['complete_RFC'] = '19' + df['RFC_year'].astype(str)

df['year_INGRESO'] = df['FECHA_INGRESO'].str.extract('(\d{4})', expand=True)

df['edad'] = df['year_INGRESO'].astype(int) - df['complete_RFC'].astype(int)

df

```

![Dataset](https://github.com/Kevincastillo98/Distribucion_Edades/blob/master/dataset.png)

- Graficamos la distribución de edades por sexo.

![Distribucion](https://github.com/Kevincastillo98/Distribucion_Edades/blob/master/dist.png)


- Creamos un histograma de las edades,por sexo.

![Histograma](https://github.com/Kevincastillo98/Distribucion_Edades/blob/master/hist.png)













