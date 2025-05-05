

# Hoja de Trucos – Curso Python: Análisis y Manipulación de Datos

## 1. INTRODUCCIÓN

### 1.1. Convención

| **Identificador** | **Significado**                          |
|------------------|--------------------------------------|
| `pd`             | Alias común para **Pandas**, una librería para manipulación y análisis de datos      |
| `np`             | Alias común para **NumPy**, una librería para operaciones numéricas y matrices       |
| `df`             | Nombre común para una variable que contiene un **DataFrame** de Pandas               |
| `s`              | Nombre común para una variable que contiene una **Series** de Pandas                 |
| `plt`            | Alias común para **Matplotlib.pyplot**, usada para crear gráficos                    |
| `sns`            | Alias común para **Seaborn**, una librería de visualización estadística basada en Matplotlib |

## 2. RECOLECCIÓN Y LECTURA DE DATOS

### 2.1. Lectura de datos

| **Función o elemento**  | **Descripción**  | **Tipo de retorno** | **Guardado** |
|-------------------------|-----------------|---------------------|--------------|
| `pd.read_csv()`        | Carga datos delimitados desde un archivo o URL; usa la coma como delimitador predeterminado. | `DataFrame` | `df.to_csv()` |
| `pd.read_excel()`      | Lee datos tabulares desde un archivo Excel en formato XLS o XLSX. | `DataFrame` | `df.to_excel()` |
| `pd.read_html()`       | Lee todas las tablas encontradas en un documento HTML dado. | `Lista de DataFrame` | `df.to_html()` |
| `pd.read_xml()`        | Lee una tabla de datos desde un archivo XML. | `DataFrame` | `df.to_xml()` |
| `pd.read_stata()`      | Lee un conjunto de datos en formato de archivo Stata. | `DataFrame` | `df.to_stata()` |

## 3. BASES DATAFRAME Y SERIES

### 3.1. Bases DataFrame: Lectura, Impresión y Retorno de Información

| **Función o elemento**  | **Descripción**  | **Tipo de retorno** |
|-------------------------|-----------------|---------------------|
| `df`                   | Retorna el DataFrame completo. | `DataFrame` |
| `print(df)`            | Imprime el DataFrame en formato texto. | `No aplica` |
| `display(df)`          | Imprime el DataFrame en formato tabla mejorado. | `No aplica` |
| `df.iloc[0]`           | Retorna la primera fila del DataFrame (sin importar el índice de filas). | `Series` |
| `s_primera_fila = df.iloc[0]` | Crea una variable `Series` que contiene los datos asociados a la primera fila (sin importar el índice de filas). | `No aplica` |
| `df.loc[0]`            | Retorna la fila del DataFrame asociado al índice de fila 0. | `Series` |
| `s_fila_0 = df.loc[0]` | Crea una variable `Series` que contiene los datos asociados a la fila con el índice de fila 0. | `No aplica` |
| `df.loc[0, "col"]`     | Retorna el valor almacenado en la columna `"col"` correspondiente a la fila con índice 0. | `Escalar` |
| `df[["col1","col2","col3"]]` | Retorna un DataFrame que solo contiene las columnas `"col1"`, `"col2"` y `"col3"` del DataFrame original. | `DataFrame` |
| `df["col"]`            | Retorna una columna específica del DataFrame. | `Series` |
| `s_col = df["col"]`    | Crea una variable `Series` que contiene los valores de la columna `"col"` del DataFrame. | `No aplica` |
| `df["col"][0]`         | Retorna el valor almacenado en la columna `"col"` correspondiente a la fila con índice 0. | `Escalar` |
| `df.columns.tolist()`  | Retorna una lista con los índices de las columnas. | `List` |
| `df.index.tolist()`    | Retorna una lista con los índices de las filas. | `List` |
| `df.dtypes`            | Retorna los tipos de los datos de las columnas. | `Series` |
| `df.head(n)`           | Retorna las primeras `n` filas del DataFrame (por defecto retorna las primeras 5). | `DataFrame` |
| `df.tail(n)`           | Retorna las últimas `n` filas del DataFrame (por defecto retorna las últimas 5). | `DataFrame` |
| `df.info()`            | Imprime información general del DataFrame, como tipos de datos y valores nulos. | `No aplica` |
| `df.describe()`        | Retorna estadísticas descriptivas de las columnas numéricas. | `DataFrame` |

### 3.2. Bases DataFrame: Modificación y Borrado

| **Función o elemento**  | **Descripción**  | **Tipo de retorno** |
|-------------------------|-----------------|---------------------|
| `df.loc[0, "col"] = 5` | Modifica el valor almacenado en la columna `"col"`, en la fila con índice `0`, y lo reemplaza por `5`. Si `"col"` no existe, la crea. | `No aplica` |
| `df["col"] = "Hola"`   | Modifica todos los valores en la columna `"col"` y los reemplaza por `"Hola"`. Si `"col"` no existe, la crea con el valor `"Hola"`. | `No aplica` |
| `df["col"] = df["col"] * 2` | Modifica todos los valores en la columna `"col"`, duplicándolos. | `No aplica` |
| `df["col"] = np.round(df["col"], 2)` | Modifica todos los valores en la columna `"col"` del DataFrame redondeando los decimales a dos cifras. | `No aplica` |
| `df = df.drop(0, axis=0)` | Borra la fila con índice `0` del DataFrame. | `No aplica` |
| `df = df.drop(columns="col")` | Borra la columna `"col"` del DataFrame. | `No aplica` |
| `df = pd.concat([df, df1], axis=1)` | Modifica `df`, ahora será un DataFrame concatenado de `df` más `df1`. `axis=1` indica que la concatenación se realiza por columnas, basado en los índices de filas de ambos DataFrames. | `No aplica` |

### 3.3. Bases Series: Lectura, Impresión y Retorno de Información

| **Función o elemento**  | **Descripción**  | **Tipo de retorno** |
|-------------------------|-----------------|---------------------|
| `s`                    | Retorna la `Series` completa. | `Series` |
| `print(s)`             | Imprime la `Series` en formato texto. | `No aplica` |
| `display(s)`           | Imprime la `Series` en formato tabla mejorado. | `No aplica` |
| `s.iloc[0]`            | Retorna el primer valor de la `Series` (sin importar el índice). | `Escalar` |
| `s.loc[0]`            | Retorna el valor de la `Series` asociado al índice `0` (aplica cuando los índices son números). | `Escalar` |
| `s.loc["col"]`         | Retorna el valor de la `Series` asociado al índice `"col"` (aplica cuando los índices son texto). | `Escalar` |
| `s.index.tolist()`     | Retorna una lista con los índices de la `Series`. | `List` |
| `s.value_counts()`     | Retorna la cantidad de veces que aparece cada valor en la `Series`. Ignora valores `NaN` por defecto. Para incluirlos, usar `dropna=False`. | `Series` |
| `s.sort_values()`      | Retorna los valores de la `Series` ordenados de menor a mayor (o de mayor a menor con `ascending=False`). | `Series` |
| `s.mean()`             | Retorna el promedio de los valores de la `Series`. | `Escalar` |
| `s.sum()`             | Retorna la suma de los valores de la `Series`. | `Escalar` |
| `s.min()`             | Retorna el valor mínimo de la `Series`. | `Escalar` |
| `s.max()`             | Retorna el valor máximo de la `Series`. | `Escalar` |
| `s[s > 5]`            | Retorna los valores de la `Series` que cumplen la condición definida (en este caso, los valores mayores a `5`). | `Series` |
| `s_filtrada = s[s > 5]` | Crea una nueva variable `Series` con los valores mayores a `5` de la `Series` `"s"`. | `No aplica` |

## 4. LIMPIEZA Y PREPARACIÓN DE DATOS

### 4.1. Datos Faltantes

| **Función o elemento**  | **Descripción**  | **Tipo de retorno** |
|-------------------------|-----------------|---------------------|
| `df = df.replace("?", np.NaN)` | Reemplaza los valores `"?"` en `df` con `NaN` (datos faltantes). | `No aplica` |
| `df.isna()`            | Retorna un `DataFrame` booleano con `True` en posiciones donde hay `NaN`. | `DataFrame` |
| `s.isna()`             | Retorna una `Series` booleana con `True` en posiciones donde hay `NaN`. | `Series` |
| `df = df.fillna(0)`    | Reemplaza todos los valores `NaN` en `df` con `0`. | `No aplica` |
| `df = df.dropna(axis=0)` | Elimina todas las filas del `DataFrame` que contienen `NaN`. `axis=0` borra filas, `axis=1` borra columnas. | `No aplica` |
| `df = df.dropna(subset=["col"])` | Elimina solo las filas donde `"col"` tiene `NaN`. | `No aplica` |

### 4.2. Reemplazo por Valor Estándar, Promedio y Valor Más Frecuente

| **Función o elemento**  | **Descripción** |
|-------------------------|----------------|
| `df["col"] = df["col"].replace(np.NaN, "Hola")` | Reemplaza los valores `NaN` en `"col"` de `df` con un valor estándar (ej: `"Hola"`). |
| `mean = df["col"].astype("float").mean()` <br><br> `df["col"] = df["col"].replace(np.NaN, mean)` | Calcula el promedio de la columna `"col"`. Y Reemplaza los valores `NaN` en `"col"` de `df` con el promedio de la columna. |
| `idxmax = df["col"].value_counts().idxmax()` <br><br> `df["col"] = df["col"].replace(np.NaN, idxmax)` | Encuentra el valor más frecuente de la columna `"col"`. Y  Reemplaza los valores `NaN` en `"col"` con el valor más frecuente de la columna. |
| `valmax = df["col"].mode()[0]` <br><br> `df["col"] = df["col"].replace(np.NaN, valmax)` | Encuentra el valor más frecuente de la columna `"col"` (otra forma). Y  Reemplaza los valores `NaN` en `"col"` con el valor más frecuente de la columna. |

### 4.3. Formateo de Datos

| **Función o elemento**  | **Descripción** |
|-------------------------|----------------|
| `df["col"] = df["col"].replace("viejo", "nuevo")` | Reemplaza los valores `"viejo"` en `"col"` de `df` con `"nuevo"`. |
| `df = df.rename(columns={"viejo":"nuevo"})` | Cambia el nombre de la columna `"viejo"` a `"nuevo"` en `df`. |
| `df["col"] = df["col"].astype("float")` | Convierte los valores de la columna `"col"` al tipo de dato `"float"`. |

### 4.4 Normalización

| **Función o elemento** | **Descripción** |
|------------------------|----------------|
| `df["col_normalizada"] = df["col"]/df["col"].max()` | Crea una columna normalizada llamada `"col_normalizada"` utilizando **Simple Feature Scaling**. Este método escala en función del valor máximo y no garantiza un rango fijo de los datos. |
| `df["col_normalizada"] = (df["col"] - df["col"].min()) / (df["col"].max() - df["col"].min())` | Crea una columna normalizada llamada `"col_normalizada"` utilizando **Min-Max Scaling**. Este método escala en un rango fijo (0 a 1). |

### 4.5 Agrupamiento

| **Función o elemento** | **Descripción** |
|------------------------|----------------|
| `bins = np.linspace(df["col"].min(), df["col"].max(), num=4)` <br><br> `etiquetas = ["Grupo 1", "Grupo 2", "Grupo 3"]` <br><br> `df["col_agrupada"] = pd.cut(df["col"], bins=bins, labels=etiquetas, include_lowest=True)` | Crea una columna agrupada llamada `"col_agrupada"` utilizando **Binning Uniforme**. Este método divide los datos en intervalos de igual tamaño. |
| `etiquetas = ["Q1", "Q2", "Q3", "Q4"]` <br><br> `df["col_agrupada"] = pd.qcut(df["col"], q=4, labels=etiquetas)` | Crea una columna agrupada llamada `"col_agrupada"` utilizando **Binning Basado en Frecuencia**. Este método crea “bins” que contienen aproximadamente la misma cantidad de datos. |
| `bins = [0, 100, 200, 300]` <br> `etiquetas = ["Baja", "Media", "Alta"]` <br><br> `df["col_agrupada"] = pd.cut(df["col"], bins=bins, labels=etiquetas, include_lowest=True)` | Crea una columna agrupada llamada `"col_agrupada"` utilizando **Binning Manual**. Este método crea “bins” dependiendo de rangos personalizados basados en reglas de negocio. |

### 4.6 Datos Categóricos

| **Función o elemento** | **Descripción** |
|------------------------|----------------|
| `df_dummy_col = pd.get_dummies(df["col"], prefix="col", dtype=int)` <br><br> `df = pd.concat([df, df_dummy_col], axis=1)` | Añade una columna booleana (0 o 1) por cada valor único en `"col"`, con el prefijo `"col"`. Este método se denomina **One-Hot Encoding**. |
| `df = pd.get_dummies(df, columns=['col'], prefix="col", dtype=int)` | Otra forma más corta de **One-Hot Encoding**. |
| `from sklearn.preprocessing import LabelEncoder` <br><br> `le = LabelEncoder()` <br><br> `df['col_codificada'] = le.fit_transform(df['col'])` | Añade una columna de categorías basada en números enteros sin ningún orden específico (sólo índices). Este método se denomina **Label Encoding**. |
| `from sklearn.preprocessing import OrdinalEncoder` <br><br> `orden = [['val1', 'val2']] ` <br><br> `oe = OrdinalEncoder(categories=orden)` <br><br> `df['col_codificada'] = oe.fit_transform(df[['col']]).astype(int)` | Añade una columna de categorías basada en números enteros con un orden específico (`val1` el menor, `val2` el mayor). Este método se denomina **Ordinal Encoding**. |

## 5. ANÁLISIS EXPLORATORIO DE DATOS

### 5.1. Estadísticas Descriptivas

| Función o elemento                  | Descripción                                                                                   | Tipo retorno |
|------------------------------------|-----------------------------------------------------------------------------------------------|--------------|
| `s.mean()`                         | Retorna el promedio de los valores de la Series.                                               | Escalar      |
| `s.median()`                       | Retorna la mediana de la Series, es decir, el valor que está en el centro al ordenar.         | Escalar      |
| `s.mode()[0]`                      | Retorna la moda de la Series, el valor que más se repite (con `[0]` tomamos el primero si hay varias). | Escalar |
| `s.max() - s.min()`                | Retorna el rango de la Series, es decir, la diferencia entre el valor máximo y el mínimo.     | Escalar      |
| `s.var()`                          | Retorna la **varianza muestral** de la Series, midiendo la dispersión de los datos.               | Escalar      |
| `s.std()`                          | Retorna la **desviación estándar muestral** de la Series, mostrando cuánto varían los datos respecto a la media. | Escalar |
| `df.describe()`                    | Retorna estadísticas descriptivas de las columnas numéricas.                                  | DataFrame    |
| `df.describe(include=[object])`   | Retorna estadísticas descriptivas de las columnas tipo texto `object`.                         | DataFrame    |

### 5.2. Visualización de datos

#### 5.2.1. Distribución Categóricas - Barras

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("05-auto.csv")
s_conteo_marcas = df["marca"].value_counts()

s_conteo_marcas.plot(kind='bar')
plt.xlabel("Marca")
plt.ylabel("Cantidad de Autos")
plt.title("Distribución de Autos por Marca")
plt.show()
```
<img src="https://github.com/user-attachments/assets/94026d38-0ef5-4f09-9276-984b99753eef" width="300">

#### 5.2.2. Distribución Categóricas - Pastel

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("05-auto.csv")
s_conteo_marcas = df["marca"].value_counts()

plt.figure(figsize=(8, 8))
s_conteo_marcas.plot(kind='pie', autopct='%1.1f%%')
plt.title("Distribución de Autos por Marca")
plt.ylabel("") # ocultar etiqueta del eje Y
plt.show()
```

<img src="https://github.com/user-attachments/assets/66f31f83-4505-40b0-b6c1-bd9882b0e202" width="300">

#### 5.2.3. Distribución Numéricas - Histograma

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("05-auto.csv")
s_potencia_hp = df["potencia_hp"]

s_potencia_hp.plot(kind='hist', bins=3)
plt.xlabel("Potencia HP")
plt.ylabel("Cantidad de Autos")
plt.title("Distribución de Autos por Potencia HP")
plt.show()
```

<img src="https://github.com/user-attachments/assets/03244664-c228-493a-9476-b0cc7981a2dd" width="300">

#### 5.2.4. Distribución Numéricas - Boxplot - Con limites

```python
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

alturas = [140, 150, 155, 160, 165, 170, 175, 220]

Q1 = np.percentile(alturas, 25)
Q2 = np.median(alturas)
Q3 = np.percentile(alturas, 75)
IQR = Q3 - Q1
limite_inferior = Q1 - 1.5 * IQR
limite_superior = Q3 + 1.5 * IQR

sns.boxplot(y=alturas)
plt.axhline(limite_superior, color='purple', linestyle='--')
plt.axhline(limite_inferior, color='purple', linestyle='--')
plt.ylabel("Altura")
plt.title("Boxplot de Alturas")
plt.grid(axis='x')
plt.show()
```

<img src="https://github.com/user-attachments/assets/ca1c8df0-9510-4127-af1a-addbd4bb56a4" width="300">

#### 5.2.5. Distribución Numéricas - Boxplot

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("05-auto.csv")
s_consumo_ciudad_kpg = df["consumo_ciudad_kpg"]

sns.boxplot(y=s_consumo_ciudad_kpg, color="lightblue")
plt.xlabel("Consumo Ciudad kpg")
plt.title("Diagrama de Caja para Consumo Ciudad kpg")
plt.show()
```

<img src="https://github.com/user-attachments/assets/14f3778a-631a-4f27-920c-a5b53e5e692d" width="300">

#### 5.2.6. Relaciones entre Variables - Scatter plot

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("05-auto.csv")

sns.scatterplot(data=df, x="tamano_motor", y="precio")
plt.title("Relación entre Tamaño Motor y Precio")
plt.grid(True)
plt.show()
```

<img src="https://github.com/user-attachments/assets/f4665545-cb05-45e8-b7fa-9c0aed63b953" width="300">

#### 5.2.7. Relaciones entre Variables - Boxplot

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("05-auto.csv")

sns.boxplot(data=df, x="ubicacion_motor", y="precio")
plt.show()
```

<img src="https://github.com/user-attachments/assets/77a8ab23-60b8-4fee-95e8-6302c73be77b" width="300">

### 5.3. Agrupamiento

#### 5.3.1. GroupBy

| Función o elemento                         | Descripción                                                              | Tipo retorno |
|-------------------------------------------|-------------------------------------------------------------------------|--------------|
| `dfgb = df.groupby("col")`                | Crea una variable DataFrameGroupBy que agrupa el DataFrame por la columna `"col"` | No aplica    |
| `df_grupo = dfgb.get_group("grupo")`      | Crea una variable DataFrame con los datos del grupo `"grupo"`             | No aplica    |
| `dfgb.mean()`                             | Retorna un DataFrame con los promedios de cada grupo            | DataFrame      |
| `dfgb.sum()`                              | Retorna un DataFrame con la suma de cada grupo                  | DataFrame      |

#### 5.3.2. Pivot

```python
df_pivot = df.pivot(index="marca", columns="num_puertas", values="precio")
```

Crea una tabla pivotada reorganizando el DataFrame, usando `"marca"` como índice, `"num_puertas"` como columnas y `"precio"` como valores. 
**Nota:** esta función solo reorganiza los datos, sin agregación, y sin permitir valores duplicados.

#### 5.3.3. Pivot_table

```python
df_pivot = df.pivot_table(
  index="marca",
  columns="numero_puertas",
  values="precio",
  aggfunc="mean"
)
```

Crea una tabla pivotada usando `"marca"` como índice, `"num_puertas"` como columnas, y `"precio"` promedio como valores (utilizando la función de agregación `"mean"`).
**Nota:**  esta función permite agrupar datos utilizando funciones de agregación, y permite valores duplicados.
