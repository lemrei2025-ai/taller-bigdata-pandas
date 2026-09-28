# Guía docente · Taller práctico de Big Data (semanas 6 y 7)

## Propósito

| Semana | Resultado esperado |
|---|---|
| 6 | El estudiante identifica, **con cifras**, las ventajas de usar los datos de una organización y los riesgos de no hacerlo. |
| 7 | El estudiante valora el universo de los datos: reconoce las fuentes según el capítulo 3 de Joyanes, distingue datos estructurados, semiestructurados y no estructurados, y entiende por qué el volumen exige herramientas de Big Data. |

**Nivel de programación requerido:** básico. Las celdas ✏️ solo piden completar un nombre de columna o de método. El peso del taller está en la **interpretación**.

**Organización sugerida:** equipos de 2 o 3 estudiantes, un computador por equipo, sesiones de unas 2 horas.

---

## Preparación antes de clase

- [ ] Ejecute los notebooks de `docente/soluciones/` con los datos reales. Así confirma que todo funciona y conoce las cifras que obtendrán los estudiantes.
- [ ] Suba los CSV de Olist a una carpeta **`olist`** en su Google Drive y compártala con el grupo (ver `datos/README.md`). Así evita que cada estudiante tenga que crear una cuenta en Kaggle.
- [ ] Reemplace `USUARIO` en los enlaces del `README.md` para que los botones **Abrir en Colab** funcionen.
- [ ] **Semana 7:** pruebe la API de datos.gov.co desde la red de la universidad. Si la conexión es inestable, ejecute la celda de descarga antes de clase y comparta el archivo `secop.json` generado.
- [ ] **Semana 7:** asigne la lectura del capítulo 3 como trabajo previo.

---

## Semana 6 · Agenda sugerida (≈ 2 horas)

| Tiempo | Actividad |
|---|---|
| 10 min | **Detonante.** Presente el caso: un gerente con años de datos que nunca ha mirado. Pregunte: *¿qué creen que está perdiendo?* Anote las hipótesis en el tablero. |
| 15 min | Secciones 0 y 1: cargar datos y primer vistazo. Recorra con el grupo el ejemplo resuelto de la sección 2. |
| 50 min | Secciones 2 a 6 en equipos. Circule por los equipos y pida que interpreten en voz alta cada resultado. |
| 25 min | Sección 8: tabla *Del hallazgo a la decisión* y pitch. |
| 20 min | **Plenaria.** Dos o tres equipos leen su pitch. Contraste los hallazgos con las hipótesis iniciales del tablero. |

### Qué deberían descubrir

Las cifras exactas las obtiene al correr la solución con los datos reales. Estas son las tendencias que suelen aparecer con este dataset:

- **Estacionalidad:** un pico marcado en **noviembre de 2017**, asociado al Black Friday. Hay muy pocos pedidos en la madrugada.
- **Pareto:** una fracción pequeña de las categorías concentra la mayor parte de los ingresos.
- **Entregas tardías:** son una minoría de los pedidos, pero su calificación promedio es **mucho menor**, y cae más a medida que aumenta el retraso. Es el hallazgo más claro para hablar de *riesgo de no usar los datos*: la empresa podría culpar al producto cuando el problema es la logística.
- **Recompra:** la gran mayoría de los clientes compra **una sola vez**. Es el hallazgo que más impacta.
- **`customer_id` frente a `customer_unique_id`:** si el estudiante agrupa por `customer_id`, obtiene 100 % de clientes de una sola compra. Úselo para discutir que **entender cómo se generó el dato** es parte del análisis (veracidad).

### Ejemplo de fila bien construida

| Hallazgo (con cifra) | Área | Beneficio si lo usa | Riesgo si lo ignora |
|---|---|---|---|
| Los pedidos tardíos tienen una calificación promedio X puntos menor | Operación / clientes | Priorizar transportadoras y rutas con más retrasos; avisar al cliente antes de que se queje | Reseñas negativas, pérdida de reputación y de clientes, y decisiones equivocadas si se culpa al producto |

---

## Semana 7 · Agenda sugerida (≈ 2 horas)

| Tiempo | Actividad |
|---|---|
| 15 min | **Repaso del capítulo 3.** Los equipos completan en el notebook la tabla de categorías de Joyanes con ejemplos propios. Socialice dos o tres ejemplos por categoría. |
| 15 min | Fuente 1: datos estructurados y valores faltantes (veracidad). |
| 30 min | Fuente 2: API de SECOP II. Haga énfasis en el JSON crudo, los campos anidados, los campos ausentes y que todo llega como texto. Discuta los datos personales y la Ley 1581 de 2012. |
| 25 min | Fuente 3: comentarios de clientes. Relacione las palabras de las reseñas negativas con el hallazgo de entregas tardías de la semana 6. |
| 20 min | Sección 4: volumen. Deje que los equipos lean la tabla del experimento mental y respondan: *¿qué harían con 500 millones de filas?* Introduzca la idea de procesamiento distribuido (Hadoop, Spark). |
| 15 min | Inventario de fuentes, fuentes no aprovechadas y conclusión. |

### Puntos clave para la discusión

- **Las categorías de Joyanes:** web y redes sociales, máquina a máquina, grandes transacciones, biométricos y generados por personas. El notebook incluye esta clasificación; verifique los nombres exactos con la edición que usa el curso y ajuste la tabla si es necesario.
- **Semiestructurado ≠ desordenado:** el JSON sí tiene organización, pero su esquema es flexible (campos anidados u opcionales). `json_normalize` lo convierte en tabla.
- **No estructurado:** el texto de las reseñas explica el *por qué* que las tablas no muestran. Además, una parte grande de los clientes no deja comentario escrito: eso también es un dato.
- **Volumen:** pandas trabaja en la memoria RAM de un solo computador. Leer por bloques (`chunksize`) es la intuición detrás de MapReduce, y Parquet es el formato típico de los *data lakes*.
- **Fuentes no aprovechadas que suelen proponer:** GPS de repartidores (M2M), clics y navegación en la tienda en línea (web), comentarios en redes sociales, llamadas al servicio al cliente (generados por personas), datos del clima o de festivos (externos).

---

## Rúbrica (aplica a cada semana)

| Criterio | Peso | Excelente | Aceptable | Insuficiente |
|---|---|---|---|---|
| Código | 30 % | Todas las celdas ✏️ completas y el notebook se ejecuta sin errores | Algunas celdas con errores menores | La mayoría de las celdas sin completar o con errores |
| Interpretación | 30 % | Las respuestas 💬 usan las cifras obtenidas y las explican | Las respuestas son correctas pero generales, sin cifras | Respuestas ausentes o que no corresponden a los resultados |
| Semana 6: beneficios y riesgos · Semana 7: clasificación de fuentes | 25 % | Tabla completa, con cifras, áreas y categorías bien asignadas y justificadas | Tabla incompleta o con errores de clasificación | Tabla ausente |
| Comunicación | 15 % | Pitch (S6) o conclusión (S7) claro, persuasivo y apoyado en datos | Claro pero sin apoyo en datos | Confuso o ausente |

---

## Adaptaciones

- **Grupo con poca experiencia en Python:** haga en vivo, proyectando, las secciones 0 a 2 de cada notebook y deje a los equipos solo la interpretación y las tablas.
- **Grupo avanzado:** en la semana 7, pídales que repitan la sección 2 con un dataset distinto de datos.gov.co (reto opcional del notebook) y que lo crucen con otra fuente.
- **Sin internet en la sala:** comparta por Drive los CSV de Olist y el archivo `secop.json` descargado previamente.
- **Puente con semanas posteriores:** la sección de volumen de la semana 7 deja planteada la pregunta que responden Hadoop y Spark.
