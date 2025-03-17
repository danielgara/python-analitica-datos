

# Hoja de Trucos – Curso Python: Análisis y Manipulación de Datos

## 1. INTRODUCCIÓN

### 1.1. Convención

| **Identificador** | **Significado**                          |
|------------------|--------------------------------------|
| `pd`            | Representa la librería **Pandas**    |
| `np`            | Representa la librería **NumPy**     |
| `df`            | Representa una variable que contiene un **DataFrame** |
| `s`             | Representa una variable que contiene una **Series** |

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
| `mean = df["col"].astype("float").mean()` <br> `df["col"] = df["col"].replace(np.NaN, mean)` | Calcula el promedio de la columna `"col"`. Y Reemplaza los valores `NaN` en `"col"` de `df` con el promedio de la columna. |
| `idxmax = df["col"].value_counts().idxmax()` <br> `df["col"] = df["col"].replace(np.NaN, idxmax)` | Encuentra el valor más frecuente de la columna `"col"`. Y  Reemplaza los valores `NaN` en `"col"` con el valor más frecuente de la columna. |
| `valmax = df["col"].mode()[0]` <br> `df["col"] = df["col"].replace(np.NaN, valmax)` | Encuentra el valor más frecuente de la columna `"col"` (otra forma). Y  Reemplaza los valores `NaN` en `"col"` con el valor más frecuente de la columna. |

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
