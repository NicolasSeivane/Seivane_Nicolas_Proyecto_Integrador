# 🏥 Medical Data Analysis with Machine Learning

**Proyecto Integrador - Tecnicatura en Inteligencia Artificial**  
Universidad Nacional de Hurlingham  
**Autor:** Nicolás Seivane  

---

## 📋 Descripción del Proyecto

Este proyecto integrador aplica técnicas de **Machine Learning** para el análisis y clasificación de datos médicos, utilizando cuatro datasets diferentes relacionados con la salud cardiovascular, fetal y vertebral. El objetivo es comparar el rendimiento de diversos algoritmos de clasificación en problemas médicos reales.

### 🎯 Objetivos

- Aplicar y comparar algoritmos de clasificación supervisada en contextos médicos
- Evaluar el rendimiento de modelos mediante validación cruzada estratificada
- Analizar la importancia de características en la predicción de enfermedades
- Implementar técnicas de preprocesamiento y normalización de datos
- Generar visualizaciones interpretables de resultados

---

## 📊 Datasets Analizados

### 1. 🫀 Heart Disease (Enfermedad Cardíaca)
- **Objetivo:** Predecir la presencia de enfermedad cardíaca
- **Características:** 11 atributos (edad, sexo, tipo de dolor torácico, presión arterial, colesterol, etc.)
- **Clases:** Binario (0: Sin enfermedad, 1: Con enfermedad)
- **Registros:** 746 pacientes (después de limpieza)

### 2. 👶 Cardiotocography (Cardiotocografía Fetal)
- **Objetivo:** Clasificar el estado fetal durante el embarazo
- **Características:** Múltiples mediciones de frecuencia cardíaca fetal
- **Clases:** Multiclase (Normal, Sospechoso, Patológico)
- **Aplicación:** Monitoreo prenatal

### 3. 🔬 Cirrhosis (Cirrosis Hepática)
- **Objetivo:** Predecir el estado de pacientes con cirrosis
- **Características:** Datos clínicos y de laboratorio
- **Clases:** Multiclase (diferentes estados de progresión)
- **Relevancia:** Diagnóstico temprano y seguimiento

### 4. 🦴 Vertebral Column (Columna Vertebral)
- **Objetivo:** Clasificar patologías de la columna vertebral
- **Características:** Mediciones biomecánicas de la pelvis y columna
- **Clases:** Multiclase (Normal, Hernia, Espondilolistesis)
- **Registros:** Datos de pacientes con y sin patologías

---

## 🤖 Algoritmos Implementados

### 1. **Random Forest (Bosques Aleatorios)**
- Ensemble de árboles de decisión
- Robusto ante overfitting
- Permite calcular importancia de características
- Hiperparámetros optimizados: n_estimators, max_depth, min_samples_split

### 2. **Naive Bayes Gaussiano**
- Basado en el teorema de Bayes
- Asume independencia condicional entre características
- Rápido y eficiente
- Ideal para datasets pequeños

### 3. **Support Vector Machine (SVM)**
- Búsqueda del hiperplano óptimo de separación
- Kernels: lineal, RBF, polinomial
- Efectivo en espacios de alta dimensionalidad
- Parámetros optimizados: C, gamma, kernel

### 4. **Logistic Regression (Regresión Logística)**
- Modelo lineal para clasificación
- Interpretable y eficiente
- Regularización L1/L2
- Baseline para comparación

---

## 📁 Estructura del Repositorio

```
Seivane_Nicolas_Proyecto_Integrador/
│
├── 📂 heart/                          # Dataset de Enfermedad Cardíaca
│   ├── heart.csv                      # Datos originales
│   ├── 01_proyecto_integrador_corazon.ipynb    # Análisis exploratorio
│   ├── 02_entrenar_modelos.ipynb      # Entrenamiento y evaluación
│   └── resultados/                    # Archivos de resultados
│
├── 📂 cardiografia/                   # Dataset de Cardiotocografía
│   ├── cardiotocography.csv
│   ├── 01_proyecto_integrador_cardiografia.ipynb
│   ├── 02_entrenar_modelos.ipynb
│   └── resultados/
│
├── 📂 cirrhosis/                      # Dataset de Cirrosis
│   ├── cirrhosis.csv
│   ├── 01_proyecto_integrador_cirrosis.ipynb
│   ├── 02_entrenar_modelos_cirrosis.ipynb
│   └── resultados/
│
├── 📂 columna_vertebral/              # Dataset de Columna Vertebral
│   ├── vertebral_column.csv
│   ├── 01_proyecto_integrador_columna_vertebral.ipynb
│   ├── 02_entrenar_modelos_vertebras.ipynb
│   └── resultados/
│
├── 📂 Tex/                            # Documentación LaTeX
│   ├── Presentación.pdf               # Presentación del proyecto
│   └── ...
│
├── 📊 visualizaciones/                # Gráficos generados
│   ├── evolucion_metrica_*.png
│   ├── permutacion_*.png
│   └── ...
│
├── 📄 informe_base_de_datos.pdf       # Informe técnico
└── 📄 README.md                       # Este archivo
```

---

## 🔬 Metodología

### 1. **Preprocesamiento de Datos**
```python
- Eliminación de duplicados y valores nulos
- Codificación de variables categóricas (Label Encoding)
- Normalización/Estandarización de características numéricas
- Tratamiento de valores atípicos (ej: colesterol = 0)
```

### 2. **Validación Cruzada Estratificada**
```python
- K-Fold Stratified (k=5)
- Preserva la distribución de clases
- Reduce sesgo en la evaluación
- Permite estimación robusta del rendimiento
```

### 3. **Métricas de Evaluación**
- **Accuracy:** Precisión general del modelo
- **Precision:** Proporción de verdaderos positivos
- **Recall:** Sensibilidad del modelo
- **F1-Score:** Media armónica de precision y recall
- **ROC-AUC:** Área bajo la curva ROC
- **Confusion Matrix:** Matriz de confusión
- **Matthews Correlation Coefficient (MCC)**
- **Cohen's Kappa**

### 4. **Análisis de Importancia de Características**
- Permutation Importance
- Feature Importance (Random Forest)
- Identificación de variables predictivas clave

---

## 📈 Resultados Principales

### Comparación de Modelos (Heart Disease)

| Modelo | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|--------|----------|-----------|--------|----------|---------|
| **Random Forest** | ~85% | ~84% | ~86% | ~85% | ~0.90 |
| **SVM (RBF)** | ~83% | ~82% | ~84% | ~83% | ~0.88 |
| **Logistic Regression** | ~81% | ~80% | ~82% | ~81% | ~0.86 |
| **Naive Bayes** | ~79% | ~78% | ~80% | ~79% | ~0.84 |

*Nota: Los valores son aproximados y varían según el dataset y configuración.*

### Características Más Importantes (Heart Disease)
1. **ST_Slope** (Pendiente del segmento ST)
2. **ChestPainType** (Tipo de dolor torácico)
3. **ExerciseAngina** (Angina inducida por ejercicio)
4. **Oldpeak** (Depresión del ST)
5. **MaxHR** (Frecuencia cardíaca máxima)

---

## 🛠️ Tecnologías Utilizadas

### Lenguajes y Frameworks
- **Python 3.x**
- **Jupyter Notebook**

### Librerías Principales
```python
- pandas          # Manipulación de datos
- numpy           # Operaciones numéricas
- scikit-learn    # Algoritmos de ML y métricas
- matplotlib      # Visualización
- seaborn         # Visualización estadística
```

### Herramientas de Desarrollo
- Git & GitHub
- Jupyter Lab/Notebook
- LaTeX (para documentación)

---

## 🚀 Cómo Ejecutar el Proyecto

### Requisitos Previos
```bash
Python 3.8+
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

### Instalación
```bash
# Clonar el repositorio
git clone https://github.com/NicolasSeivane/Seivane_Nicolas_Proyecto_Integrador.git
cd Seivane_Nicolas_Proyecto_Integrador

# Instalar dependencias
pip install -r requirements.txt  # (crear este archivo si no existe)
```

### Ejecución de Notebooks

#### Opción 1: Análisis Exploratorio
```bash
# Navegar a cualquier carpeta de dataset
cd heart/
jupyter notebook 01_proyecto_integrador_corazon.ipynb
```

#### Opción 2: Entrenamiento de Modelos
```bash
# Ejecutar notebook de entrenamiento
jupyter notebook 02_entrenar_modelos.ipynb
```

### Orden Recomendado de Ejecución

Para cada dataset:
1. **Notebook 01:** Análisis exploratorio de datos (EDA)
   - Carga y limpieza de datos
   - Visualizaciones
   - Estadísticas descriptivas

2. **Notebook 02:** Entrenamiento y evaluación
   - Preprocesamiento
   - Validación cruzada
   - Comparación de modelos
   - Análisis de resultados

---

## 📚 Índice de Notebooks

### 🫀 Heart Disease
1. **[01_proyecto_integrador_corazon.ipynb](heart/proyecto_integrador_corazon.ipynb)**
   - Análisis exploratorio del dataset de enfermedad cardíaca
   - Visualización de distribuciones
   - Correlaciones entre variables

2. **[02_entrenar_modelos.ipynb](heart/entrenar_modelos.ipynb)**
   - Implementación de 4 algoritmos de clasificación
   - Validación cruzada estratificada (k=5)
   - Comparación exhaustiva de métricas
   - Análisis de importancia de características

### 👶 Cardiotocography
1. **[01_proyecto_integrador_cardiografia.ipynb](cardiografia/proyecto_integrador_cardiografia.ipynb)**
   - EDA de datos de cardiotocografía fetal
   - Análisis de clases (Normal, Sospechoso, Patológico)

2. **[02_entrenar_modelos.ipynb](cardiografia/entrenar_modelos.ipynb)**
   - Clasificación multiclase
   - Evaluación de modelos en contexto médico prenatal

### 🔬 Cirrhosis
1. **[01_proyecto_integrador_cirrosis.ipynb](cirrhosis/proyecto_integrador_cirrosis.ipynb)**
   - Análisis de datos clínicos de cirrosis hepática
   - Exploración de variables de laboratorio

2. **[02_entrenar_modelos_cirrosis.ipynb](cirrhosis/entrenar_modelos_cirrosis.ipynb)**
   - Predicción de estados de progresión
   - Optimización de hiperparámetros

### 🦴 Vertebral Column
1. **[01_proyecto_integrador_columna_vertebral.ipynb](columna_vertebral/proyecto_integrador_columna_vertebral.ipynb)**
   - Análisis biomecánico de la columna vertebral
   - Visualización de mediciones pélvicas

2. **[02_entrenar_modelos_vertebras.ipynb](columna_vertebral/entrenar_modelos_vertebras.ipynb)**
   - Clasificación de patologías vertebrales
   - Comparación de rendimiento en datos biomecánicos

---

## 📊 Visualizaciones Destacadas

El proyecto incluye múltiples visualizaciones generadas:

- **Evolución de Métricas:** Comparación de accuracy, F1-score y ROC-AUC entre modelos
- **Matrices de Confusión:** Análisis detallado de predicciones
- **Importancia de Características:** Gráficos de permutation importance
- **Distribuciones:** Histogramas y boxplots de variables clave
- **Curvas ROC:** Análisis de sensibilidad vs especificidad

---

## 🎓 Aprendizajes Clave

1. **Importancia del Preprocesamiento:** La limpieza y normalización de datos médicos es crucial
2. **No Free Lunch Theorem:** Ningún algoritmo es superior en todos los datasets
3. **Validación Cruzada:** Esencial para evitar overfitting y obtener métricas confiables
4. **Interpretabilidad:** En medicina, entender *por qué* un modelo predice es tan importante como la precisión
5. **Desbalanceo de Clases:** Técnicas como stratified k-fold son fundamentales en datos médicos

---

## 🔮 Trabajo Futuro

- [ ] Implementar técnicas de ensemble (Voting, Stacking)
- [ ] Explorar redes neuronales (MLP, CNN para datos tabulares)
- [ ] Aplicar técnicas de explicabilidad (SHAP, LIME)
- [ ] Optimización bayesiana de hiperparámetros
- [ ] Análisis de curvas de aprendizaje
- [ ] Implementar cross-validation anidado
- [ ] Despliegue de modelos con Flask/FastAPI

---

## 📄 Documentación Adicional

- **[Informe Técnico](informe_base_de_datos.pdf):** Análisis detallado de los datasets
- **[Presentación](Tex/Presentación.pdf):** Slides del proyecto

---

## 👤 Autor

**Nicolás Seivane**  
Estudiante de Tecnicatura en Inteligencia Artificial  
Universidad Nacional de Hurlingham

---

## 📜 Licencia

Este proyecto es parte de un trabajo académico para la Universidad Nacional de Hurlingham.

---

## 🙏 Agradecimientos

- **Andrea Rey** - Docente y guía del proyecto
- **Universidad Nacional de Hurlingham** - Por la formación en IA
- **Comunidad de Scikit-learn** - Por las excelentes herramientas de ML

---

## 📞 Contacto

Para consultas sobre este proyecto, puedes contactarme a través de:
- GitHub: [@NicolasSeivane](https://github.com/NicolasSeivane)
- LinkedIn: [Nicolás Seivane](https://linkedin.com/in/nicolas-seivane)

---

**⭐ Si este proyecto te resulta útil, considera darle una estrella en GitHub!**