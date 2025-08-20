# 📊 Alura-Challenge-Telecom-X-Parte-2 — Predicción de Cancelación (Churn)

Este proyecto forma parte de un desafío de *Machine Learning aplicado a negocios*, donde el objetivo fue **predecir qué clientes tienen mayor probabilidad de cancelar sus servicios (churn)** en la empresa ficticia **Telecom X**.  

El trabajo se desarrolló en **dos etapas**:  
1. **Análisis exploratorio (EDA)**: limpieza, estandarización de datos, análisis de churn y visualizaciones iniciales.  
2. **Modelado predictivo**: entrenamiento de modelos de clasificación, evaluación comparativa y obtención de insights estratégicos para retención de clientes.  

---

## 🚀 Objetivos
- Preparar los datos con encoding, balanceo y normalización.  
- Explorar correlaciones y variables clave asociadas al churn.  
- Entrenar distintos modelos de clasificación: **Random Forest, Regresión Logística, KNN**.  
- Evaluar el rendimiento con métricas (Accuracy, F1, matriz de confusión).  
- Identificar las variables más influyentes en la predicción de cancelación.  
- Proponer **estrategias de retención basadas en los resultados**.  

---

## 📂 Estructura del Proyecto
📁 TelecomX-Churn
├── 
TelecomX_clean.csv # Dataset limpio (Parte 1)
├── 
TelecomX_balanced.csv # Dataset balanceado (oversampling)
├── 
notebook.ipynb # Notebook principal con el análisis completo
├── README.md # Este archivo
└── figs/ # Carpeta con visualizaciones
├── 00_distribucion_churn_pre_balanceo.png
├── 02_correlacion_top20.png
├── 03_tasa_por_contrato.png
├── 04_box_totalcharges_churn.png
├── 05_rf_importancias.png
└── 06_lr_coef_top15.png
---

## 🔧 Tecnologías Utilizadas
- **Python 3.10+**
- **Pandas / NumPy** → manipulación y limpieza de datos  
- **Matplotlib** → visualización  
- **Scikit-learn** → modelos de clasificación y métricas  
- **Jupyter Notebook** → flujo interactivo y presentación  

---

## 📊 Resultados de Modelos

| Modelo               | Accuracy | F1 (train) | F1 (test) |
|-----------------------|----------|------------|-----------|
| Random Forest         | 0.8937   | 0.9979     | 0.8986    |
| Regresión Logística   | 0.7900   | 0.7804     | 0.7900    |
| KNN                   | 0.7588   | 0.8031     | 0.7795    |

👉 **Random Forest** fue el mejor modelo, aunque mostró cierto *overfitting*.  
👉 **Regresión Logística** confirmó los drivers principales con buena interpretabilidad.  
👉 **KNN** tuvo el rendimiento más bajo.

---

## 🔍 Variables más importantes

**Random Forest (Top 5):**
- `total_charges`
- `tenure_months`
- `monthly_charges`
- `Cuentas_Diarias`
- `contract_Two year`

**Regresión Logística (Top 5):**
- `tenure_months`
- `internet_service_Fiber optic`
- `total_charges`
- `contract_Two year`
- `internet_service_No`

---

## 📈 Ejemplos de Visualizaciones

### Distribución de Churn (antes del balanceo)
![Distribución de churn](figs/00_distribucion_churn_pre_balanceo.png)

### Matriz de Correlación (Top 20)
![Correlación](figs/02_correlacion_top20.png)

### Importancia de Variables — Random Forest
![RF Importancias](figs/05_rf_importancias.png)

### Coeficientes — Regresión Logística
![LR Coefs](figs/06_lr_coef_top15.png)

---

## 🎯 Conclusiones y Estrategias
- **Clientes nuevos (tenure bajo, total_charges bajo)** son los más propensos a cancelar.  
- **Contratos mensuales** presentan mayor churn → incentivar contratos anuales/bianuales.  
- **Internet Fiber Optic** aparece vinculado a cancelaciones → revisar calidad/precio.  
- **Cargos mensuales altos + baja antigüedad** generan riesgo → ofrecer descuentos/promos iniciales.  

**Estrategias recomendadas:**
1. **Onboarding y fidelización** en los primeros meses.  
2. **Campañas de retención proactivas** con alertas del modelo.  
3. **Bundles de servicios** (ej. seguridad/soporte) a precios promocionales.  
4. **Migración de métodos de pago** y mejora de experiencia en fibra óptica.  

---
