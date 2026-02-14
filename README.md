
Desafío IronKaggle: Predicción de Ventas 🛒
Este proyecto fue desarrollado por Alejandro de Tuero y Marta Carballo como parte del desafío IronKaggle. El objetivo principal es predecir las ventas diarias de una cadena de tiendas utilizando técnicas de análisis de datos y modelos de Machine Learning.

📋 Objetivo del Proyecto
Construir un modelo predictivo capaz de estimar las ventas (sales) de diversas tiendas, considerando factores como promociones, festivos y estacionalidad.

🛠️ Tecnologías Utilizadas
Python (Carga y procesamiento de datos)

Pandas / NumPy (Manipulación de datos y Feature Engineering)

XGBoost (Algoritmo de Gradient Boosting para regresión)

Matplotlib / Seaborn (Visualización de resultados)

Scikit-learn (Métricas de evaluación: MAE y R²)

🚀 Etapas del Proyecto
1. Limpieza y Preparación de Datos
Unificación de Festivos: Se limpió la columna state_holiday para asegurar consistencia entre valores numéricos y cadenas.

Codificación: Se aplicó One-Hot Encoding a las variables categóricas de festivos (holiday_a, holiday_b, holiday_c).

Tratamiento de Nulos: Se verificó la ausencia de valores faltantes en el dataset original.

2. Ingeniería de Variables (Feature Engineering)
Se crearon nuevas variables para capturar patrones temporales y de comportamiento:

Variables Temporales: Descomposición de la fecha en Año, Mes, Día, Semana del año y Estación.

Indicadores de Calendario: Identificación de fines de semana (is_weekend), inicio y fin de mes.

Variables de Interacción: Combinación de promociones con vacaciones escolares y fines de semana.

ADN de Tienda: Cálculo de la media de ventas por tienda y día de la semana (store_dow_mean) para capturar el comportamiento específico de cada establecimiento.

3. Modelo de Machine Learning
Se utilizó un modelo XGBRegressor con los siguientes detalles técnicos:

Transformación de la Target: Se aplicó log1p a las ventas para normalizar la distribución durante el entrenamiento.

Configuración: learning_rate=0.03, max_depth=10, y 1000 estimadores con early stopping.

Validación: Split temporal (80% entrenamiento, 20% prueba) para evitar el uso de datos del futuro.

📊 Resultados y Evaluación
El modelo final demostró una alta precisión en las predicciones:

R² Score (Precisión): ~0.95 (El modelo explica el 95% de la variabilidad de las ventas).

MAE (Error Absoluto Medio): ~534.34 € de desviación promedio por predicción.

Regla de Negocio: El modelo fuerza las ventas a 0 si la tienda está cerrada (open == 0), garantizando coherencia lógica.

Visualización Principal
El proyecto incluye un análisis de la importancia de las variables, destacando que el "ADN de la tienda" (medias históricas) y las promociones son los factores que más influyen en las ventas.

📂 Archivos Generados
sales_procesado.csv: Dataset con todas las nuevas variables calculadas.

entrega_final_sales.csv: Archivo final con las predicciones para la competición.

predicciones_con_columnas.csv: Detalle completo de las predicciones alineadas con los datos de entrada.
