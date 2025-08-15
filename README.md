# 📊 Predicción de Cancelación de Clientes (Churn Prediction)

Este proyecto implementa un análisis exploratorio y modelos de machine learning para predecir la cancelación de clientes en una empresa de telecomunicaciones, identificando los factores más relevantes y proponiendo estrategias de retención.

---

## 📌 Objetivos
- Analizar patrones de cancelación en los clientes.
- Identificar las variables con mayor impacto en la cancelación.
- Probar diferentes modelos de predicción y comparar su rendimiento.
- Proporcionar recomendaciones basadas en los hallazgos.

---

## 🗂 Flujo de trabajo

### 1️⃣ **Carga y Preparación de Datos**
- Limpieza de valores nulos.
- Codificación de variables categóricas.
- Creación de un diccionario de renombramiento para hacer más legibles los nombres de las variables.

### 2️⃣ **Análisis Exploratorio**
- **Análisis de Correlación**:
  - Matriz de correlación y top variables relacionadas con `Churn`.
  - Identificación de relaciones lineales más fuertes.
- **Análisis Dirigido**:
  - Comparación de *Tenure* (tiempo de contrato) vs `Churn`.
  - Comparación de *Total Charges* (gasto total) vs `Churn`.
  - Uso de boxplots y scatter plots para visualizar patrones.

### 3️⃣ **Separación de Datos**
- División de datos en **70% entrenamiento** y **30% prueba**.

### 4️⃣ **Modelado Predictivo**
Se entrenaron dos modelos:

#### 🌲 **Modelo 1: Random Forest**
- **Precisión (Accuracy):** 77.9%
- **ROC-AUC:** 0.815
- **Conclusiones**:
  - Buen balance entre precisión y recall para la clase `No Churn`.
  - Variables más importantes:
    1. *Total Charges*
    2. *Tenure*
    3. *Monthly Charges*
    4. Tipo de contrato (Contract Two Year, Contract One Year)
    5. *Electronic Check* como método de pago

#### 📈 **Modelo 2: Regresión Logística (con normalización)**
- **Precisión (Accuracy):** 73.7%
- **ROC-AUC:** 0.795
- **Conclusiones**:
  - Mejor identificación de la clase `Churn` que Random Forest, aunque con menor precisión general.
  - Coeficientes más influyentes:
    - *Monthly Charges* (positivo → más gasto mensual, mayor riesgo de cancelación)
    - *Tenure* (negativo → más tiempo en la empresa, menor riesgo)
    - *Electronic Check* (positivo → mayor riesgo)
    - Ausencia de *Tech Support* o *Online Security* aumenta el riesgo

---

## 📊 Resultados Globales

| Modelo              | Accuracy | ROC-AUC | Mejor en... |
|---------------------|----------|---------|-------------|
| Random Forest       | 0.779    | 0.815   | Variables más claras y buen balance |
| Regresión Logística | 0.737    | 0.795   | Interpretabilidad y detección de Churn |

---

## 📌 Principales Factores de Cancelación
1. **Antigüedad baja** (*Tenure* bajo) → Clientes nuevos tienden a cancelar más.
2. **Altos cargos mensuales** (*Monthly Charges*).
3. **Bajo gasto total acumulado** (*Total Charges*).
4. **Método de pago "Electronic Check"** asociado a mayor tasa de cancelación.
5. **Ausencia de servicios extra** como *Tech Support* o *Online Security*.

---

## 💡 Recomendaciones de Retención
- Implementar **programas de fidelización** para clientes nuevos.
- Ofrecer **descuentos progresivos** en cargos mensuales.
- Incentivar métodos de pago automáticos (tarjeta).
- Promocionar servicios extra como *Tech Support* y *Online Security*.

---

## 📂 Visualizaciones
En el cuaderno se incluyen:
- Matriz de correlación.
- Boxplots de Tenure y Total Charges vs Churn.
- Gráficos de importancia de variables por modelo.
- Matrices de confusión y curvas ROC para ambos modelos.

---

## ⚙️ Tecnologías Usadas
- Python (Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn)
- Google Colab
- Git + GitHub

---

✒️ **Autor:** *RAFAEL AHUMADA*  
📅 **Fecha:** *14-08-2025*  
