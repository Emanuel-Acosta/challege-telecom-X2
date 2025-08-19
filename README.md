# 📊 Análisis de Evasión de Clientes (Churn) en TelecomX parte 2

## 📌 Descripción

Este proyecto tiene como objetivo principal **analizar los patrones de cancelación de clientes (churn)** en la empresa **TelecomX**, del sector telecomunicaciones. La pérdida de clientes impacta directamente en los ingresos y la rentabilidad, por lo tanto, **identificar los factores que influyen en esta decisión es clave para diseñar estrategias efectivas de retención**.

A través de un proceso completo de **preprocesamiento, análisis exploratorio, modelado y evaluación**, se busca construir una base sólida para entender y predecir la cancelación de clientes, y proponer soluciones de negocio basadas en datos.

---

## 🧠 Contenido del Proyecto

### 🗃️ 1. Extracción y Carga de Datos

- Carga de datos desde GitHub en formato CSV.
- Transformación de estructuras a DataFrame utilizando `pandas`.
- Inspección de la estructura, nombres de columnas, tipos de datos y valores únicos.

### 🧼 2. Limpieza y Preprocesamiento

- Eliminación de columnas irrelevantes (como identificadores).
- Conversión de variables categóricas a formato numérico.
- Codificación binaria y One-Hot Encoding.
- Revisión y tratamiento de valores nulos.
- Verificación de la distribución de clases en la variable objetivo (`Cancelacion`).

### 📏 3. Normalización (si aplica)

- Aplicación de `StandardScaler` a variables numéricas relevantes como `Factura_Mensual`, `Cargos_Totales`, `Meses_Contrato`, etc.
- *Solo se utiliza en modelos sensibles a la escala como Regresión Logística.*

### 📊 4. Análisis Exploratorio de Datos (EDA)

- Visualización de la distribución de `Cancelacion`.
- Matriz de correlación entre variables.
- Análisis de variables clave en relación con el churn:
  - `Meses_Contrato` vs Cancelación (boxplot).
  - `Cargos_Totales` vs Cancelación (boxplot).
- Revisión del desbalanceo de clases y aplicación de **SMOTE** para balancear la muestra de entrenamiento.

### 🧪 5. Modelado

Se construyeron y evaluaron dos modelos supervisados:

- **Regresión Logística**
  - Datos normalizados
  - Usó SMOTE en el set de entrenamiento
- **Random Forest**
  - Datos sin normalizar
  - Modelo robusto a desbalanceo leve

### 📉 6. Evaluación de Modelos

Para ambos modelos se calcularon:

- Matriz de confusión
- Precisión
- Recall
- F1-score
- Exactitud (Accuracy)

Se graficaron también las matrices de confusión para mejor visualización.

### 🔍 7. Interpretación de Resultados

- **Regresión Logística**: se analizaron los coeficientes para identificar el impacto positivo o negativo de cada variable.
- **Random Forest**: se analizó la importancia relativa de las variables en la clasificación final.

### 🧾 8. Informe Final y Recomendaciones

- Identificación de los factores con mayor impacto en la cancelación:
  - Alto monto de `Factura_Mensual`
  - Contratos de corto plazo
  - Métodos de pago menos confiables (ej. electronic check)
  - Falta de servicios adicionales como seguridad o soporte técnico
- Se sugiere:
  - Fomentar contratos de mayor duración (12 o 24 meses)
  - Incentivar el uso de pagos automáticos
  - Promocionar paquetes con soporte o seguridad incluidos
  - Crear campañas específicas para perfiles en alto riesgo

---


## 🛠️ Tecnologías Utilizadas

- **Lenguaje:** Python 3
- **Librerías Principales:**  
  - `pandas`, `numpy` – manipulación de datos  
  - `matplotlib`, `seaborn` – visualización  
  - `scikit-learn` – modelado y métricas  
  - `imbalanced-learn` – balanceo de clases con SMOTE

---

## Uso y Ejecución

El análisis está diseñado para ejecutarse en un entorno de Jupyter Notebook. El flujo es el siguiente:

1. Ejecutar la extracción de datos desde la URL especificada.  
2. Realizar la normalización y limpieza del dataset.  
3. Ejecutar las celdas de análisis exploratorio para obtener insights visuales y estadísticos.  
4. Revisar el informe final para la interpretación de resultados.

## Autor

Emanuel Acosta  
Ciencia de Datos | ONE + Alura LATAM
