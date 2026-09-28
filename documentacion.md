# Documentación para consultar

Glosario de todos los términos de Python y pandas que se usan en el taller, con el enlace a su documentación oficial.

La documentación de pandas está en inglés; puede usar la opción **Traducir** del navegador. La documentación de Python enlazada está en español.

**Ayuda dentro del notebook:** escriba `help(pd.merge)` o agregue un signo de interrogación al final, como `pd.merge?`, para ver la ayuda de cualquier función sin salir de Colab.

## Guías generales

| Término | Para qué sirve | Enlace |
|---|---|---|
| Tutoriales de introducción a pandas | Diez tutoriales cortos: leer datos, seleccionar, graficar, combinar tablas, fechas, texto | [Ver documentación](https://pandas.pydata.org/docs/getting_started/intro_tutorials/index.html) |
| 10 minutos con pandas | Recorrido rápido por las funciones principales | [Ver documentación](https://pandas.pydata.org/docs/user_guide/10min.html) |
| Guía: combinar tablas | `merge`, `join` y `concat` con diagramas | [Ver documentación](https://pandas.pydata.org/docs/user_guide/merging.html) |
| Guía: agrupar datos | Explicación del proceso dividir, aplicar y combinar | [Ver documentación](https://pandas.pydata.org/docs/user_guide/groupby.html) |
| Guía: datos faltantes | Cómo detectar y tratar valores vacíos | [Ver documentación](https://pandas.pydata.org/docs/user_guide/missing_data.html) |
| Google Colab | Introducción al entorno de notebooks en la nube | [Ver documentación](https://colab.research.google.com/notebooks/intro.ipynb) |

## Lectura y exploración

| Término | Para qué sirve | Enlace |
|---|---|---|
| `pd.read_csv()` | Lee un archivo CSV y lo convierte en tabla (DataFrame). `parse_dates` indica qué columnas son fechas y `chunksize` permite leer por bloques | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.read_csv.html) |
| `.head()` | Muestra las primeras filas de una tabla | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.head.html) |
| `.columns` | Nombres de las columnas de una tabla | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.columns.html) |
| `.info()` | Resumen de la tabla: columnas, tipos de dato y valores no vacíos | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.info.html) |
| `.shape` | Número de filas y columnas de una tabla | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.shape.html) |
| `.dtypes` | Tipo de dato de cada columna (número, texto, fecha…) | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.dtypes.html) |
| `.min()` / `.max()` | Valor mínimo y máximo de una columna | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.min.html) |

## Selección y filtrado

| Término | Para qué sirve | Enlace |
|---|---|---|
| `.loc[]` | Selecciona filas y columnas por etiqueta; también permite rangos como `"2017-01":"2018-08"` | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.loc.html) |
| Filtrado con condiciones | Seleccionar filas que cumplen una condición, como `tabla[tabla["col"] == valor]`, y combinar condiciones con `&` | [Ver documentación](https://pandas.pydata.org/docs/user_guide/indexing.html#boolean-indexing) |
| `.filter()` | Selecciona columnas cuyo nombre contiene un texto (`like=`) | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.filter.html) |
| `.notna()` | Devuelve `True` donde el valor **no** está vacío | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.notna.html) |
| `.isna()` | Devuelve `True` donde el valor está vacío (NaN) | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.isna.html) |
| `.isin()` | Verifica si cada valor pertenece a una lista o conjunto | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.isin.html) |
| `.dropna()` | Elimina los valores vacíos | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.dropna.html) |
| `.copy()` | Crea una copia independiente de una tabla para modificarla sin afectar la original | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.copy.html) |
| `.drop()` | Elimina columnas (`columns=`) o filas de una tabla | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.drop.html) |

## Combinar tablas

| Término | Para qué sirve | Enlace |
|---|---|---|
| `.merge()` | Une dos tablas usando una columna en común (`on=`), como un JOIN de SQL. `how="left"` conserva todas las filas de la tabla izquierda | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.merge.html) |

## Agrupar y resumir

| Término | Para qué sirve | Enlace |
|---|---|---|
| `.groupby()` | Agrupa las filas por los valores de una columna para calcular algo por grupo | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.groupby.html) |
| `sum`, `mean`, `count`, `nunique`, `agg` | Cálculos que se aplican después de `groupby`: suma, promedio, conteo, conteo de valores distintos y varios cálculos a la vez | [Ver documentación](https://pandas.pydata.org/docs/reference/groupby.html) |
| `.mean()` | Promedio. Sobre una columna de `True`/`False` da la proporción de `True` | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.mean.html) |
| `.nunique()` | Cuenta cuántos valores distintos hay | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.nunique.html) |
| `.value_counts()` | Cuenta cuántas veces aparece cada valor. Con `normalize=True` da proporciones | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.value_counts.html) |
| `.sort_values()` | Ordena los valores (`ascending=False` para ordenar de mayor a menor) | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.sort_values.html) |
| `.idxmax()` | Devuelve la etiqueta (por ejemplo, el mes) donde está el valor máximo | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.idxmax.html) |
| `.cumsum()` | Suma acumulada, útil para el análisis de Pareto | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.cumsum.html) |
| `.clip()` | Limita los valores a un máximo o mínimo (`upper=5`) | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.clip.html) |
| `pd.cut()` | Divide una columna numérica en rangos o intervalos (`bins`) con nombres (`labels`) | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.cut.html) |
| `.mul()` / `.round()` | Multiplica (por ejemplo, por 100 para obtener porcentajes) y redondea | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.mul.html) |
| `.add()` | Suma dos series alineando por etiqueta; `fill_value=0` trata las etiquetas faltantes como cero | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.add.html) |

## Fechas y horas

| Término | Para qué sirve | Enlace |
|---|---|---|
| `.dt` | Accesor para trabajar con columnas de fecha: extraer año, mes, día, hora, día de la semana… | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.dt.html) |
| `.dt.to_period()` | Convierte una fecha en un periodo, por ejemplo el mes (`"M"`) | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.dt.to_period.html) |
| `.dt.hour` | Extrae la hora (0 a 23) de una fecha | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.dt.hour.html) |
| `.dt.days` | Número de días de una diferencia entre dos fechas | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.dt.days.html) |
| Guía: series de tiempo | Todo sobre fechas en pandas | [Ver documentación](https://pandas.pydata.org/docs/user_guide/timeseries.html) |

## Texto

| Término | Para qué sirve | Enlace |
|---|---|---|
| `.str` | Accesor para aplicar operaciones de texto a toda una columna | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.str.html) |
| `.str.lower()` | Convierte el texto a minúsculas | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.str.lower.html) |
| `.str.replace()` | Reemplaza partes del texto; con `regex=True` acepta expresiones regulares | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.str.replace.html) |
| `.str.split()` | Separa el texto en una lista de palabras | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.str.split.html) |
| `.str.len()` | Longitud de cada texto | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.str.len.html) |
| `.str.contains()` | Verifica si el texto contiene un patrón; la barra vertical del patrón significa "o" | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.str.contains.html) |
| `.explode()` | Convierte cada elemento de una lista en una fila propia | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.explode.html) |
| Módulo `re` (expresiones regulares) | Sintaxis de patrones como `[^a-z]` (cualquier carácter que no sea letra) o la barra vertical ("o") | [Ver documentación](https://docs.python.org/es/3/library/re.html) |
| Guía: trabajar con texto | Todas las operaciones de texto en pandas | [Ver documentación](https://pandas.pydata.org/docs/user_guide/text.html) |

## Datos semiestructurados y APIs

| Término | Para qué sirve | Enlace |
|---|---|---|
| `requests.get()` | Consulta una dirección web (API) desde Python; `params` agrega los parámetros de la consulta | [Ver documentación](https://requests.readthedocs.io/en/latest/user/quickstart/) |
| Módulo `json` | Lee (`json.load`) y escribe (`json.dump`, `json.dumps`) datos en formato JSON | [Ver documentación](https://docs.python.org/es/3/library/json.html) |
| `pd.json_normalize()` | Aplana registros JSON (con campos anidados) y los convierte en tabla | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.json_normalize.html) |
| `pd.to_numeric()` | Convierte texto a número; `errors="coerce"` deja vacío lo que no se puede convertir | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.to_numeric.html) |
| API de datos.gov.co (Socrata) | Cómo funcionan las direcciones (*endpoints*) de la API de datos abiertos | [Ver documentación](https://dev.socrata.com/docs/endpoints.html) |
| Parámetro `$limit` | Cuántos registros devuelve la API en cada consulta | [Ver documentación](https://dev.socrata.com/docs/queries/limit.html) |
| Portal datos.gov.co | Catálogo de datos abiertos de Colombia | [Ver documentación](https://www.datos.gov.co) |
| Ley 1581 de 2012 | Ley colombiana de protección de datos personales | [Ver documentación](http://www.secretariasenado.gov.co/senado/basedoc/ley_1581_2012.html) |

## Volumen y formatos

| Término | Para qué sirve | Enlace |
|---|---|---|
| `.memory_usage()` | Memoria que ocupa cada columna; con `deep=True` mide también el texto | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.memory_usage.html) |
| `.to_parquet()` | Guarda una tabla en formato Parquet | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.to_parquet.html) |
| `pd.read_parquet()` | Lee un archivo Parquet | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.read_parquet.html) |
| Lectura por bloques (`chunksize`) | Cómo recorrer un archivo grande por partes sin cargarlo completo | [Ver documentación](https://pandas.pydata.org/docs/user_guide/io.html#iterating-through-files-chunk-by-chunk) |
| Guía: escalar a grandes volúmenes | Qué hacer cuando los datos no caben en memoria | [Ver documentación](https://pandas.pydata.org/docs/user_guide/scale.html) |
| Apache Parquet | Documentación del formato columnar usado en Big Data | [Ver documentación](https://parquet.apache.org/docs/overview/) |
| `time.perf_counter()` | Reloj de alta precisión para medir cuánto tarda una operación | [Ver documentación](https://docs.python.org/es/3/library/time.html#time.perf_counter) |
| `os.path.getsize()` | Tamaño de un archivo en bytes | [Ver documentación](https://docs.python.org/es/3/library/os.path.html#os.path.getsize) |
| `psutil` | Información del computador, como la memoria RAM total | [Ver documentación](https://psutil.readthedocs.io/) |

## Gráficos

| Término | Para qué sirve | Enlace |
|---|---|---|
| `.plot()` | Dibuja gráficos desde una tabla o serie; `kind=` elige el tipo (`line`, `bar`, `barh`) | [Ver documentación](https://pandas.pydata.org/docs/reference/api/pandas.Series.plot.html) |
| Guía: visualización en pandas | Tipos de gráficos y ejemplos | [Ver documentación](https://pandas.pydata.org/docs/user_guide/visualization.html) |
| `matplotlib.pyplot` | Librería de gráficos: títulos, ejes y `plt.show()` | [Ver documentación](https://matplotlib.org/stable/api/pyplot_summary.html) |

## Python básico

| Término | Para qué sirve | Enlace |
|---|---|---|
| f-strings | Textos con valores incrustados: `f"Total: {valor:.1%}"` | [Ver documentación](https://docs.python.org/es/3/tutorial/inputoutput.html) |
| Ciclo `for` | Repetir una instrucción para cada elemento | [Ver documentación](https://docs.python.org/es/3/tutorial/controlflow.html) |
| `try` / `except` | Manejo de errores: intentar algo y reaccionar si falla | [Ver documentación](https://docs.python.org/es/3/tutorial/errors.html) |
| Diccionarios | Estructuras clave → valor, como los registros JSON | [Ver documentación](https://docs.python.org/es/3/tutorial/datastructures.html#dictionaries) |
