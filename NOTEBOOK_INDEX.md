# 📋 Índice de Notebooks - Proyecto Integrador

## Guía de Navegación

Este documento proporciona un **índice completo** de todos los notebooks del proyecto, organizados por dataset y propósito.

---

## 🗂️ Estructura General

Cada dataset tiene **2 notebooks principales**:
1. **01_proyecto_integrador_[dataset].ipynb**: Análisis Exploratorio de Datos (EDA)
2. **02_entrenar_modelos_[dataset].ipynb**: Entrenamiento y Evaluación de Modelos

---

## 📚 Notebooks por Dataset

### 🫀 1. Heart Disease (Enfermedad Cardíaca)

#### 📓 [01_proyecto_integrador_corazon.ipynb](heart/01_proyecto_integrador_corazon.ipynb)
**Propósito:** Análisis exploratorio del dataset de enfermedad cardíaca

**Contenido:**
- Carga del dataset `heart.csv` (746 pacientes)
- Limpieza de datos (eliminación de cholesterol = 0)
- Análisis estadístico descriptivo
- Visualización de distribuciones de variables
- Análisis de correlaciones
- Identificación de patrones entre pacientes con/sin enfermedad

**Duración estimada:** 15-20 minutos

---

#### 📓 [02_entrenar_modelos.ipynb](heart/02_entrenar_modelos.ipynb)
**Propósito:** Entrenamiento y comparación de modelos de clasificación binaria

**Contenido:**
- Preprocesamiento completo (codificación + normalización)
- Implementación de validación cruzada estratificada (k=5)
- Entrenamiento de 4 algoritmos:
  - Random Forest
  - Naive Bayes Gaussiano
  - Support Vector Machine (SVM)
  - Regresión Logística
- Cálculo de métricas exhaustivas (accuracy, precision, recall, F1, ROC-AUC, MCC, Kappa)
- Análisis de importancia de características (permutation importance)
- Generación de visualizaciones comparativas
- Guardado de resultados en archivos `.txt`

**Duración estimada:** 30-45 minutos (dependiendo del hardware)

**Resultados esperados:**
- Random Forest: ~85% accuracy
- SVM: ~83% accuracy
- Regresión Logística: ~81% accuracy

---

### 👶 2. Cardiotocography (Cardiotocografía Fetal)

#### 📓 [01_proyecto_integrador_cardiografia.ipynb](cardiografia/01_proyecto_integrador_cardiografia.ipynb)
**Propósito:** Análisis exploratorio de datos de monitoreo fetal

**Contenido:**
- Carga del dataset `cardiotocography.csv` (~2,126 registros)
- Análisis de variables de frecuencia cardíaca fetal
- Visualización de distribuciones por clase (Normal, Sospechoso, Patológico)
- Análisis de desbalanceo de clases
- Correlaciones entre características de CTG
- Exploración de patrones patológicos

**Duración estimada:** 20-25 minutos

---

#### 📓 [02_entrenar_modelos.ipynb](cardiografia/02_entrenar_modelos.ipynb)
**Propósito:** Clasificación multiclase del estado fetal

**Contenido:**
- Preprocesamiento de características de CTG
- Validación cruzada estratificada (preserva distribución de clases)
- Entrenamiento de 4 algoritmos de clasificación multiclase
- Métricas específicas para multiclase (macro/micro averaging)
- Análisis de matrices de confusión (especialmente Normal vs Sospechoso vs Patológico)
- Importancia de características (aceleraciones, desaceleraciones, variabilidad)
- Evaluación de recall en clase Patológica (crítica para seguridad fetal)

**Duración estimada:** 35-50 minutos

**Desafíos:**
- Desbalanceo de clases (77% Normal, 9% Patológico)
- Similitud entre clases Sospechoso y Patológico

---

### 🔬 3. Cirrhosis (Cirrosis Hepática)

#### 📓 [01_proyecto_integrador_cirrosis.ipynb](cirrhosis/01_proyecto_integrador_cirrosis.ipynb)
**Propósito:** Análisis exploratorio de datos clínicos de cirrosis

**Contenido:**
- Carga del dataset `cirrhosis.csv` (~418 pacientes)
- Análisis de parámetros hepáticos (bilirrubina, albúmina, enzimas)
- Visualización de marcadores clínicos
- Análisis de supervivencia y progresión
- Tratamiento de valores faltantes
- Correlaciones entre biomarcadores

**Duración estimada:** 20-25 minutos

---

#### 📓 [02_entrenar_modelos_cirrosis.ipynb](cirrhosis/02_entrenar_modelos_cirrosis.ipynb)
**Propósito:** Predicción del estado del paciente (Censored, Transplant, Death)

**Contenido:**
- Imputación de valores faltantes
- Preprocesamiento de variables clínicas
- Validación cruzada estratificada
- Entrenamiento de modelos multiclase
- Análisis de importancia de biomarcadores (bilirrubina, albúmina, protrombina)
- Evaluación de predicción de supervivencia
- Identificación de factores de riesgo

**Duración estimada:** 30-40 minutos

**Desafíos:**
- Valores faltantes en datos de laboratorio
- Desbalanceo de clases (pocos eventos de muerte)
- Censura en datos de supervivencia

---

### 🦴 4. Vertebral Column (Columna Vertebral)

#### 📓 [01_proyecto_integrador_columna_vertebral.ipynb](columna_vertebral/01_proyecto_integrador_columna_vertebral.ipynb)
**Propósito:** Análisis exploratorio de parámetros biomecánicos

**Contenido:**
- Carga del dataset `vertebral_column.csv` (310 pacientes)
- Análisis de ángulos espino-pélvicos
- Visualización de distribuciones por clase (Normal, Hernia, Espondilolistesis)
- Verificación de ecuación de Duval-Beaupère (PI = PT + SS)
- Correlaciones entre parámetros biomecánicos
- Identificación de rangos patológicos

**Duración estimada:** 15-20 minutos

---

#### 📓 [02_entrenar_modelos_vertebras.ipynb](columna_vertebral/02_entrenar_modelos_vertebras.ipynb)
**Propósito:** Clasificación de patologías vertebrales

**Contenido:**
- Normalización de características biomecánicas
- Validación cruzada estratificada
- Entrenamiento de 4 algoritmos
- Análisis de importancia de parámetros (degree of spondylolisthesis, pelvic incidence)
- Matrices de confusión multiclase
- Evaluación de discriminación entre patologías

**Duración estimada:** 25-35 minutos

**Resultados esperados:**
- Alta precisión en detección de espondilolistesis (degree of spondylolisthesis es muy discriminativo)
- Mayor dificultad en distinguir Normal vs Hernia de Disco

---

## 🎯 Orden Recomendado de Ejecución

### Para Aprendizaje Completo:
1. **Heart Disease** (más simple, binario)
   - 01_proyecto_integrador_corazon.ipynb
   - 02_entrenar_modelos.ipynb

2. **Vertebral Column** (multiclase, características claras)
   - 01_proyecto_integrador_columna_vertebral.ipynb
   - 02_entrenar_modelos_vertebras.ipynb

3. **Cardiotocography** (multiclase, desbalanceado)
   - 01_proyecto_integrador_cardiografia.ipynb
   - 02_entrenar_modelos.ipynb

4. **Cirrhosis** (más complejo, valores faltantes)
   - 01_proyecto_integrador_cirrosis.ipynb
   - 02_entrenar_modelos_cirrosis.ipynb

### Para Demostración Rápida:
- **Heart Disease - 02_entrenar_modelos.ipynb** (mejor documentado, resultados claros)

---

## 🔧 Requisitos Técnicos

### Dependencias:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

### Versiones Recomendadas:
- Python: 3.8+
- pandas: 1.5+
- scikit-learn: 1.2+
- numpy: 1.23+

### Hardware:
- **Mínimo**: 4GB RAM, procesador dual-core
- **Recomendado**: 8GB RAM, procesador quad-core
- **Tiempo de ejecución total**: 2-3 horas (todos los notebooks)

---

## 📊 Estructura de Notebooks de Entrenamiento

Todos los notebooks `02_entrenar_modelos_*.ipynb` siguen esta estructura:

### 1. Importación de Librerías
```python
import pandas as pd
import numpy as np
from sklearn.ensemble import RandomForestClassifier
from sklearn.naive_bayes import GaussianNB
from sklearn.svm import SVC
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score, precision_score, recall_score, f1_score, roc_auc_score
from sklearn.model_selection import StratifiedKFold
```

### 2. Carga y Preprocesamiento
- Lectura del CSV
- Eliminación de duplicados y nulos
- Codificación de variables categóricas
- Normalización de variables numéricas

### 3. Función de Validación Cruzada
```python
def validacion_cruzada(conjunto, atributos, concepto, k=5, random=False, 
                       agregar_unos=False, undersample=False, oversample=False)
```

### 4. Entrenamiento de Modelos
Para cada algoritmo:
- Configuración de hiperparámetros
- Entrenamiento en k-folds
- Predicción en conjunto de validación
- Cálculo de métricas

### 5. Comparación de Resultados
- Tablas comparativas de métricas
- Gráficos de barras (accuracy, F1, ROC-AUC)
- Matrices de confusión
- Análisis de importancia de características

### 6. Guardado de Resultados
- Archivos `.txt` con resultados detallados
- Gráficos `.png` en carpeta raíz

---

## 📈 Métricas Calculadas

### Para Clasificación Binaria (Heart Disease):
- **Accuracy**: Precisión general
- **Precision**: Proporción de verdaderos positivos
- **Recall**: Sensibilidad
- **F1-Score**: Media armónica de precision y recall
- **ROC-AUC**: Área bajo la curva ROC
- **Matthews Correlation Coefficient (MCC)**
- **Cohen's Kappa**
- **Balanced Accuracy**
- **Log Loss**

### Para Clasificación Multiclase (Cardiotocography, Cirrhosis, Vertebral Column):
- **Accuracy**: Precisión general
- **Precision (macro/micro)**: Promedio de precision por clase
- **Recall (macro/micro)**: Promedio de recall por clase
- **F1-Score (macro/micro)**: Promedio de F1 por clase
- **ROC-AUC (ovr/ovo)**: One-vs-Rest o One-vs-One
- **Confusion Matrix**: Matriz de confusión multiclase

---

## 🎨 Visualizaciones Generadas

### Gráficos de Comparación de Modelos:
- `mejores_modelos_barras_binario.png`: Comparación de métricas (Heart Disease)
- `mejores_modelos_barras_multiclase.png`: Comparación de métricas (otros datasets)
- `evolucion_metrica_*.png`: Evolución de métricas por fold

### Gráficos de Importancia:
- `permutacion_rf.png`: Importancia de características (Random Forest)
- `permutacion_svm.png`: Importancia de características (SVM)
- `permutacion_rl.png`: Importancia de características (Regresión Logística)
- `permutacion_nb.png`: Importancia de características (Naive Bayes)

### Gráficos de Distribuciones (EDA):
- Histogramas de variables numéricas
- Boxplots por clase
- Heatmaps de correlación
- Matrices de confusión

---

## 💡 Consejos para Ejecución

### 1. Ejecutar Celdas Secuencialmente
- Los notebooks dependen del estado de celdas anteriores
- No saltar celdas de preprocesamiento

### 2. Ajustar Hiperparámetros (Opcional)
- Modificar `n_estimators` en Random Forest para más/menos árboles
- Cambiar `kernel` en SVM ('linear', 'rbf', 'poly')
- Ajustar `C` y `gamma` en SVM

### 3. Guardar Resultados
- Los archivos `.txt` se sobrescriben en cada ejecución
- Renombrar si se quieren conservar resultados de diferentes configuraciones

### 4. Interpretación de Resultados
- Comparar métricas entre modelos
- Analizar matrices de confusión para entender errores
- Revisar importancia de características para insights médicos

---

## 🔍 Troubleshooting

### Error: "FileNotFoundError"
- Verificar que el archivo CSV esté en la carpeta correcta
- Actualizar la ruta en `pd.read_csv()`

### Warning: "FutureWarning: Downcasting behavior"
- Advertencia benigna de pandas
- No afecta los resultados

### Ejecución Lenta en SVM
- SVM con kernel RBF puede ser lento en datasets grandes
- Considerar reducir el número de folds o usar kernel lineal

### Métricas Muy Bajas
- Verificar que el preprocesamiento se haya ejecutado correctamente
- Asegurar que la normalización se aplicó antes del entrenamiento

---

## 📞 Contacto

Para preguntas sobre los notebooks:
- **Autor**: Nicolás Seivane
- **Institución**: Universidad Nacional de Hurlingham

---

**Última actualización**: Diciembre 2024
