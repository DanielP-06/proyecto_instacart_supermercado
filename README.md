# Proyecto_Instacart_Supermercado
Análisis de Instacart: ¿Qué, Cuándo y Por Qué Compran los Clientes?

(El CSV de Order_products esta en mi drive como comprimido. Link para descarga https://drive.google.com/file/d/1_tAqlgmkSSdAFJCuUd45HP8jFByaSV75/view?usp=sharing )

Aqui tnemos un análisis exploratorio de datos (EDA) realizado sobre un conjunto de datos del negocio Instacart, una plataforma de entrega de comestibles.

## EL problema
Comprender el comportamiento de compra de los clientes en una plataforma de comestibles (tipo Instacart) para responder preguntas clave del negocio:

¿Qué productos son los más demandados y cuáles se re-ordenan con más frecuencia?

¿Cuándo compran los clientes (hora/día) y cómo afecta eso al tamaño del carrito?

¿Qué productos suelen agregarse primero al carrito (impulsos / básicos)?

El objetivo es extraer insights accionables que sirvan para merchandising, promociones y optimización de inventario.

**Objetivos del Proyecto:**

*   Cargar y comprender la estructura de múltiples tablas de datos relacionadas.
*   Realizar una limpieza de datos completa, identificando y manejando valores ausentes y duplicados.
*   Explorar los patrones temporales de pedidos como la hora del día, día de la semana etc.
*   Analizar el comportamiento del cliente: frecuencia de pedidos, tamaño del carrito y tasa de re-ordenamiento por cliente.
*   Identificar los productos más populares y aquellos con alta tasa de re-ordenamiento.
*   Descubrir qué productos suelen ser los primeros en agregarse al carrito.

## Datos
Dataset base: tablas típicas de Instacart (orders, products, order_products, aisles, departments, users/customers en su versión adaptada).

Archivo comprimido del CSV order_products (descarga):
https://drive.google.com/file/d/1_tAqlgmkSSdAFJCuUd45HP8jFByaSV75/view?usp=sharing

Nota: Los datos fueron intencionalmente modificados para incluir valores faltantes y duplicados (simulación de escenarios reales) — esto permite practicar limpieza y robustez del pipeline.

Columnas relevantes usadas (ejemplos): order_id, user_id, product_id, add_to_cart_order, reordered, order_dow, order_hour_of_day, order_number, product_name, aisle_id, department_id, order_time

**Tecnologías y Bibliotecas Utilizadas:**

*   Python
*   Pandas 
*   Matplotlib 

## Metodo
Método

Carga de tablas

Lectura de CSVs con pandas (posible uso de chunks si el archivo es grande).

Preprocesamiento / ETL

Descompresión y colocación de archivos en data/.

Normalización de nombres, conversión de fechas, tipos y renombrado de columnas.

Detección y tratamiento de duplicados y valores ausentes (imputación o eliminación según caso).

Filtrado de outliers básicos en métricas numéricas (si aplica).

Feature engineering

Calcular order_age / order_number por cliente, is_repeat por producto, proporción reorder_rate por producto.

Crear variables temporales (hour_of_day, day_of_week, is_weekend).

Calcular first_add_rate = % veces que un producto aparece con add_to_cart_order == 1.

Análisis exploratorio (EDA)

Distribuciones de pedidos por día y hora.

Tamaño de carrito (items por pedido) y distribución por cliente.

Top-N productos por volumen y por tasa de reorden.

Segmentación de clientes por frecuencia (ocasional / recurrente / top-buyers).

Visualización


**KPIs:**

*   Se identificaron patrones claros en las horas y días de mayor actividad de pedidos por ejemplo, picos los domingos y lunes, y durante ciertas horas del día.
*   Vimos que la distribución del número de pedidos por cliente muestra una mezcla de compradores ocasionales y un núcleo de clientes más frecuentes.
*   Productos básicos orgánicos como plátanos y fresas se encuentran entre los más populares y con mayor tasa de re-ordenamiento.
*   El análisis de la tasa de re-orden por cliente revela la variabilidad en la lealtad de compra de los usuarios.
*   Ciertos productos, comunmente los básicos, son en general los primeros en ser agregados a los carritos de compra.

Este proyecto demuestra habilidades en:

*   Limpieza y preprocesamiento de datos
*   Análisis exploratorio de datos (EDA)
*   Manipulación de datos con pandas
*   Visualización de datos con matplotlib
*   Identificación de insights de negocio a partir de datos transaccionales

  ## Cómo Ejecutar el Proyecto

1.  Clona este repositorio.
2.  Asegúrate de tener las librerías de Python mencionadas instaladas (pandas numpy y matplotlib).
3.  Coloca los archivos CSV en la ubicación especificada en el código o actualiza las rutas de archivo dependiendo de donde los guardes.
4.  Ejecuta el notebook en un entorno Python (como Jupyter Notebook o Google Colab).

## Autor

Daniel Pineda
