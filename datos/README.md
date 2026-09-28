# Datos del taller

Los datos **no se incluyen** en el repositorio (pesan alrededor de 120 MB y tienen su propia licencia). Hay tres formas de obtenerlos. Los notebooks prueban las tres automáticamente, en este orden.

## Opción 1 · Carpeta `datos/` (local o en Colab)

1. Descargue el dataset desde Kaggle: <https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce> (botón **Download**; se necesita una cuenta gratuita).
2. Descomprima el ZIP.
3. **Trabajo local:** copie los CSV en esta carpeta `datos/`.
   **En Colab:** abra el panel de archivos (ícono de carpeta), cree una carpeta `datos` y suba los CSV ahí. Estos archivos se borran al cerrar la sesión.

## Opción 2 · Google Drive compartido (recomendada para clase)

1. El docente sube los CSV a una carpeta llamada **`olist`** en su Drive y la comparte con el grupo.
2. Cada estudiante agrega la carpeta a **Mi unidad** (clic derecho → *Organizar* → *Agregar acceso directo* → *Mi unidad*).
3. En Colab: panel de archivos (ícono de carpeta) → **Montar Drive**. El notebook encontrará `/content/drive/MyDrive/olist`.

## Opción 3 · Descarga automática desde Kaggle

Si no encuentra los archivos, el notebook intenta descargarlos con `kagglehub`. Si Kaggle pide credenciales o la descarga falla, use la opción 1 o 2.

## Archivos que se usan

| Archivo | Semana | Contenido |
|---|---|---|
| `olist_orders_dataset.csv` | 6 y 7 | Pedidos y fechas de compra, entrega y entrega estimada |
| `olist_order_items_dataset.csv` | 6 | Productos de cada pedido y su precio |
| `olist_order_reviews_dataset.csv` | 6 y 7 | Calificación y comentario del cliente |
| `olist_customers_dataset.csv` | 6 | Clientes (incluye `customer_unique_id`) |
| `olist_products_dataset.csv` | 6 | Productos y su categoría |
| `olist_order_payments_dataset.csv` | 6 | Medios de pago y cuotas |
| `product_category_name_translation.csv` | 6 | Traducción de categorías al inglés |
| `olist_geolocation_dataset.csv` | 7 | Códigos postales con coordenadas (≈1 millón de filas) |

## Datos de SECOP II (semana 7)

Se descargan en vivo desde la API de datos.gov.co y se guardan como `secop.json`. Si en la sala no hay internet estable, el docente puede ejecutar esa celda antes de clase y compartir el archivo `secop.json`. El notebook lo usa automáticamente si la API no responde.
