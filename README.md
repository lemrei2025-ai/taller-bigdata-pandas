# Taller práctico de Big Data con Python y pandas

**Curso:** Fundamentos de Big Data · **Semanas 6 y 7**

Taller en dos fases sobre una misma empresa: el *marketplace* brasileño **Olist**, con cerca de 100 000 pedidos reales. En la semana 6 los estudiantes descubren lo que la empresa gana si usa sus datos y lo que pierde si no lo hace. En la semana 7 buscan y clasifican las fuentes de datos según el capítulo 3 del libro de Joyanes Aguilar.

| Semana | Tema | Notebook | Abrir en Colab |
|---|---|---|---|
| 6 | Ventajas de aplicar Big Data y riesgos de no usar los datos | [`semana06_costo_de_no_mirar_los_datos.ipynb`](notebooks/semana06_costo_de_no_mirar_los_datos.ipynb) | [Abrir en Colab](https://colab.research.google.com/github/USUARIO/taller-bigdata-pandas/blob/main/notebooks/semana06_costo_de_no_mirar_los_datos.ipynb) |
| 7 | El universo de los datos y dónde se encuentran (cap. 3, Joyanes) | [`semana07_cazando_datos.ipynb`](notebooks/semana07_cazando_datos.ipynb) | [Abrir en Colab](https://colab.research.google.com/github/USUARIO/taller-bigdata-pandas/blob/main/notebooks/semana07_cazando_datos.ipynb) |

> **Antes de publicar:** reemplace `USUARIO` en los enlaces de Colab por su nombre de usuario de GitHub (y `taller-bigdata-pandas` si le pone otro nombre al repositorio).

---

## ¿Qué hacen los estudiantes?

### Semana 6 · El costo de no mirar los datos
Actúan como consultores contratados por un gerente que nunca ha analizado sus datos. Con pandas responden cinco preguntas de negocio:

1. ¿Cuándo vende más la empresa? (meses y horas)
2. ¿Qué categorías generan los ingresos? (principio de Pareto)
3. ¿Las entregas tardías bajan la calificación del cliente?
4. ¿Los clientes vuelven a comprar?
5. ¿Cómo pagan los clientes? (opcional)

Cierran con una **matriz de hallazgos → beneficios → riesgos** y un **pitch** de un minuto para el gerente.

### Semana 7 · Cazando datos
Trabajan una fuente de cada tipo y la ubican en la clasificación del capítulo 3:

| Fuente | Tipo | Herramienta |
|---|---|---|
| Pedidos de Olist | Estructurado · transacciones | `read_csv`, `info`, valores faltantes |
| SECOP II en datos.gov.co | Semiestructurado · JSON desde una API | `requests`, `json_normalize` |
| Comentarios de clientes | No estructurado · texto libre | procesamiento de texto con `.str` |
| Geolocalización (≈1 millón de filas) | Volumen | memoria, `chunksize`, CSV frente a Parquet |

También discuten datos personales (Ley 1581 de 2012) y terminan con un **inventario de fuentes** y una propuesta de fuentes que la empresa no está aprovechando.

---

## Estructura del repositorio

```
taller-bigdata-pandas/
├── README.md
├── requirements.txt          # Solo si se trabaja fuera de Colab
├── documentacion.md          # Glosario con enlaces a la documentación oficial
├── notebooks/                # Versión para estudiantes (con espacios ___ por completar)
│   ├── semana06_costo_de_no_mirar_los_datos.ipynb
│   └── semana07_cazando_datos.ipynb
├── datos/
│   └── README.md             # Cómo obtener el dataset de Olist
└── docente/
    ├── guia_docente.md       # Agenda, preparación, respuestas esperadas y rúbrica
    └── soluciones/           # Notebooks resueltos
```

> **Sobre las soluciones:** si el repositorio es público, los estudiantes podrán ver la carpeta `docente/soluciones/`. Si no quiere eso, bórrela antes de subir el repositorio y guárdela aparte, o mantenga una copia privada del repositorio para usted.

---

## Cómo usarlo

### Estudiantes (Google Colab, recomendado)
1. Haga clic en el botón **Abrir en Colab** de la semana correspondiente.
2. **Archivo → Guardar una copia en Drive.**
3. Ejecute las celdas en orden. Complete las celdas marcadas **COMPLETE AQUÍ** y responda las preguntas numeradas.

No hay que instalar nada: Colab ya trae pandas, matplotlib y requests.

### Trabajo local (Jupyter o VS Code)
```bash
git clone https://github.com/USUARIO/taller-bigdata-pandas.git
cd taller-bigdata-pandas
pip install -r requirements.txt
jupyter notebook
```

### Documentación para consultar
Cada sección de los notebooks termina con una tabla de los términos usados (`.dt`, `merge`, `groupby`, `json_normalize`…) y el enlace a su documentación oficial. El glosario completo está en [`documentacion.md`](documentacion.md).

### Datos
Los notebooks buscan los archivos de Olist automáticamente (carpeta `datos/`, Google Drive o descarga desde Kaggle). Vea [`datos/README.md`](datos/README.md).

---

## Cómo subir este repositorio a GitHub

**Opción A · Desde el navegador (sin instalar nada)**
1. Entre a [github.com/new](https://github.com/new), nombre el repositorio `taller-bigdata-pandas` y créelo **sin** README.
2. Haga clic en **uploading an existing file**.
3. Arrastre **el contenido** de esta carpeta (no la carpeta misma) y confirme con **Commit changes**.
4. Edite este README y reemplace `USUARIO` por su nombre de usuario.

**Opción B · Con git**
```bash
cd taller-bigdata-pandas
git init
git add .
git commit -m "Taller práctico de Big Data con pandas, semanas 6 y 7"
git branch -M main
git remote add origin https://github.com/USUARIO/taller-bigdata-pandas.git
git push -u origin main
```

---

## Créditos y licencias

- **Dataset:** [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce), publicado en Kaggle bajo licencia CC BY-NC-SA 4.0. Los datos no se incluyen en este repositorio.
- **Datos abiertos:** [SECOP II – Contratos Electrónicos](https://www.datos.gov.co/Gastos-Gubernamentales/SECOP-II-Contratos-Electr-nicos/jbjy-vk9h), Portal de Datos Abiertos de Colombia.
- **Lectura base:** Joyanes Aguilar, L. *Big Data: Análisis de grandes volúmenes de datos en organizaciones*. Alfaomega.
