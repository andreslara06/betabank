 
# 📊 Predicción de Cancelación de Clientes – Beta Bank

## 📌 Descripción del Proyecto

Beta Bank ha detectado una pérdida progresiva de clientes mes a mes. Diversos análisis internos muestran que **retener a un cliente existente es significativamente más barato que adquirir uno nuevo**.

El objetivo de este proyecto es **predecir qué clientes tienen mayor probabilidad de cancelar** su contrato, utilizando datos históricos de comportamiento y características del cliente, para que el equipo de negocio pueda aplicar estrategias de retención de manera proactiva.

## 🎯 Objetivo

Construir un modelo de clasificación que:

* Prediga si un cliente **cancelará (churn = 1)** o **no cancelará (churn = 0)**.
* Maximice el **F1-Score**, dada la naturaleza desbalanceada del problema.
* Evalúe la capacidad general del modelo utilizando **ROC AUC**.

## 🗂️ Datos Utilizados

El dataset contiene información histórica de clientes, incluyendo:

Características demográficas

* Score crediticio
* Ubicación geográfica
* Género
* Edad
* Salario estimado
* Estado final (cancelado o activo)

Se realizó un proceso completo de:

* Limpieza de datos
* Conversión de variables categóricas
* Ingeniería de características
* Manejo del desbalance de clases

## ⚙️ Metodología

### 1. Análisis Exploratorio

* Se detectó un desbalance de clases significativo, con muchos más clientes activos que clientes que cancelaron.

### 2. Preparación de Datos

* One-Hot Encoding para variables categóricas.
* Separación en conjuntos de entrenamiento y validación.
* Estrategias de balanceo:
    * Oversampling
    * Undersampling (seleccionada como la mejor opción)

### 3. Modelos Evaluados

* Regresión Logística
* Árbol de Decisión
* Bosque Aleatorio (Random Forest)

### 4. Selección de Métricas

* F1-Score: para medir la calidad de predicción sobre la clase minoritaria (clientes que cancelan).
* ROC AUC: para evaluar la capacidad del modelo de diferenciar clientes que se irán vs. los que permanecerán.

## 🏆 Resultados

El mejor desempeño se obtuvo con un Random Forest Classifier, usando un conjunto balanceado mediante undersampling.

**Modelo final:**

* n_estimators = 20
* max_depth = 7

Resultados clave:

* **ROC AUC ≈ 0.86**

Esto significa que el modelo tiene aproximadamente un 86% de probabilidad de asignar un score de riesgo mayor a un cliente que cancelará, en comparación con uno que no lo hará.

## 📈 Conclusiones

* El desbalance de clases afectaba significativamente el rendimiento de los modelos.

* El uso de undersampling permitió que los modelos aprendieran mejor los patrones de cancelación.

* El modelo final logra una capacidad sólida de discriminación, lo que lo hace útil para priorizar clientes en riesgo.

* El enfoque es adecuado para apoyar decisiones de negocio orientadas a retención de clientes.

## 🛠️ Tecnologías Utilizadas

* Python
* Pandas / NumPy
* Scikit-learn
* Matplotlib
* Git / GitHub