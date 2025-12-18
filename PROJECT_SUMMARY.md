# 🎓 Proyecto Integrador - Resumen Ejecutivo

## Información del Proyecto

**Título:** Análisis de Datos Médicos con Machine Learning  
**Autor:** Nicolás Seivane  
**Institución:** Universidad Nacional de Hurlingham  
**Programa:** Tecnicatura en Inteligencia Artificial  
**Fecha:** 2024

---

## 📌 Resumen

Este proyecto integrador aplica técnicas de **Machine Learning supervisado** para el análisis y clasificación de cuatro datasets médicos diferentes. Se implementaron y compararon cuatro algoritmos de clasificación (Random Forest, SVM, Naive Bayes, Regresión Logística) utilizando validación cruzada estratificada y métricas exhaustivas de evaluación.

---

## 🎯 Objetivos Alcanzados

✅ **Análisis Exploratorio de Datos (EDA)** completo para cada dataset  
✅ **Preprocesamiento** robusto (limpieza, codificación, normalización)  
✅ **Implementación** de 4 algoritmos de clasificación  
✅ **Validación Cruzada Estratificada** (k=5) para evaluación robusta  
✅ **Comparación exhaustiva** de modelos con múltiples métricas  
✅ **Análisis de importancia** de características  
✅ **Visualizaciones** interpretables de resultados  
✅ **Documentación** completa del proyecto

---

## 📊 Datasets Analizados

| Dataset | Tipo | Registros | Clases | Aplicación |
|---------|------|-----------|--------|------------|
| **Heart Disease** | Binario | 746 | 2 | Predicción de enfermedad cardíaca |
| **Cardiotocography** | Multiclase | ~2,126 | 3 | Clasificación de estado fetal |
| **Cirrhosis** | Multiclase | ~418 | 3 | Predicción de progresión de cirrosis |
| **Vertebral Column** | Multiclase | 310 | 3 | Clasificación de patologías vertebrales |

---

## 🤖 Algoritmos Implementados

### 1. Random Forest
- **Ventajas:** Robusto, maneja no-linealidad, calcula importancia de características
- **Rendimiento:** Generalmente el mejor en todos los datasets
- **Hiperparámetros optimizados:** n_estimators, max_depth, min_samples_split

### 2. Support Vector Machine (SVM)
- **Ventajas:** Efectivo en alta dimensionalidad, versátil con kernels
- **Rendimiento:** Segundo mejor en la mayoría de datasets
- **Kernels probados:** Linear, RBF, Polynomial

### 3. Regresión Logística
- **Ventajas:** Interpretable, rápido, baseline sólido
- **Rendimiento:** Competitivo, especialmente en datos linealmente separables
- **Regularización:** L1, L2

### 4. Naive Bayes Gaussiano
- **Ventajas:** Rápido, eficiente con pocos datos
- **Rendimiento:** Variable según el dataset
- **Limitación:** Asume independencia entre características

---

## 📈 Resultados Principales

### Heart Disease (Enfermedad Cardíaca)
- **Mejor Modelo:** Random Forest (~85% accuracy, ROC-AUC ~0.90)
- **Características Clave:** ST_Slope, ChestPainType, ExerciseAngina
- **Insight:** La pendiente del segmento ST es el predictor más importante

### Cardiotocography (Cardiotocografía Fetal)
- **Mejor Modelo:** Random Forest
- **Desafío:** Desbalanceo de clases (9% patológico)
- **Insight:** Variabilidad de frecuencia cardíaca y desaceleraciones son críticas

### Cirrhosis (Cirrosis Hepática)
- **Mejor Modelo:** Random Forest
- **Desafío:** Valores faltantes en datos de laboratorio
- **Insight:** Bilirrubina y albúmina son los biomarcadores más predictivos

### Vertebral Column (Columna Vertebral)
- **Mejor Modelo:** Random Forest / SVM
- **Insight:** Degree of Spondylolisthesis discrimina perfectamente la espondilolistesis
- **Observación:** Relación matemática PI = PT + SS se verifica en los datos

---

## 🔬 Metodología

### 1. Análisis Exploratorio (EDA)
- Estadísticas descriptivas
- Visualización de distribuciones
- Análisis de correlaciones
- Identificación de outliers y valores faltantes

### 2. Preprocesamiento
- Limpieza de datos (duplicados, nulos, valores inválidos)
- Codificación de variables categóricas (Label Encoding)
- Normalización de variables numéricas (Z-score)
- Manejo de desbalanceo (Stratified K-Fold)

### 3. Validación Cruzada
- **Método:** Stratified K-Fold (k=5)
- **Ventaja:** Preserva distribución de clases
- **Resultado:** Estimación robusta del rendimiento

### 4. Evaluación
- **Métricas binarias:** Accuracy, Precision, Recall, F1, ROC-AUC, MCC, Kappa
- **Métricas multiclase:** Macro/Micro averaging, Confusion Matrix
- **Análisis:** Permutation Importance, Feature Importance

---

## 💡 Aprendizajes Clave

### Técnicos
1. **No Free Lunch Theorem:** Ningún algoritmo es superior en todos los datasets
2. **Importancia del Preprocesamiento:** La calidad de los datos determina el rendimiento
3. **Validación Cruzada:** Esencial para evitar overfitting y obtener métricas confiables
4. **Desbalanceo de Clases:** Requiere técnicas especiales (stratification, métricas balanceadas)
5. **Interpretabilidad:** Feature importance ayuda a entender decisiones del modelo

### Dominio Médico
1. **Contexto Clínico:** Entender el significado médico de las variables mejora el análisis
2. **Recall vs Precision:** En medicina, minimizar falsos negativos puede ser crítico
3. **Explicabilidad:** Los médicos necesitan entender *por qué* un modelo predice algo
4. **Validación Clínica:** Los modelos deben validarse con profesionales de la salud

---

## 🛠️ Stack Tecnológico

### Lenguajes y Herramientas
- **Python 3.x**
- **Jupyter Notebook**
- **Git & GitHub**

### Librerías Principales
- **pandas:** Manipulación de datos
- **numpy:** Operaciones numéricas
- **scikit-learn:** Algoritmos de ML y métricas
- **matplotlib:** Visualización
- **seaborn:** Visualización estadística

---

## 📁 Estructura del Repositorio

```
Seivane_Nicolas_Proyecto_Integrador/
│
├── README.md                          # Documentación principal
├── NOTEBOOK_INDEX.md                  # Índice de notebooks
├── PROJECT_SUMMARY.md                 # Este archivo
├── requirements.txt                   # Dependencias
│
├── heart/                             # Dataset de Enfermedad Cardíaca
│   ├── README.md
│   ├── 01_proyecto_integrador_corazon.ipynb
│   ├── 02_entrenar_modelos.ipynb
│   └── heart.csv
│
├── cardiografia/                      # Dataset de Cardiotocografía
│   ├── README.md
│   ├── 01_proyecto_integrador_cardiografia.ipynb
│   ├── 02_entrenar_modelos.ipynb
│   └── cardiotocography.csv
│
├── cirrhosis/                         # Dataset de Cirrosis
│   ├── README.md
│   ├── 01_proyecto_integrador_cirrosis.ipynb
│   ├── 02_entrenar_modelos_cirrosis.ipynb
│   └── cirrhosis.csv
│
├── columna_vertebral/                 # Dataset de Columna Vertebral
│   ├── README.md
│   ├── 01_proyecto_integrador_columna_vertebral.ipynb
│   ├── 02_entrenar_modelos_vertebras.ipynb
│   └── vertebral_column.csv
│
├── visualizaciones/                   # Gráficos generados
│   ├── evolucion_metrica_*.png
│   ├── permutacion_*.png
│   └── mejores_modelos_*.png
│
└── Tex/                               # Documentación LaTeX
    └── Presentación.pdf
```

---

## 🎓 Competencias Desarrolladas

### Machine Learning
- ✅ Implementación de algoritmos de clasificación supervisada
- ✅ Validación cruzada y evaluación de modelos
- ✅ Optimización de hiperparámetros
- ✅ Análisis de importancia de características
- ✅ Manejo de desbalanceo de clases

### Ciencia de Datos
- ✅ Análisis exploratorio de datos (EDA)
- ✅ Preprocesamiento y limpieza de datos
- ✅ Visualización de datos
- ✅ Interpretación de resultados
- ✅ Comunicación de insights

### Programación
- ✅ Python para Data Science
- ✅ Uso de librerías científicas (pandas, numpy, scikit-learn)
- ✅ Jupyter Notebooks
- ✅ Control de versiones (Git)
- ✅ Documentación de código

### Dominio Médico
- ✅ Comprensión de datasets médicos
- ✅ Interpretación de variables clínicas
- ✅ Contexto de aplicaciones en salud
- ✅ Consideraciones éticas en ML médico

---

## 🔮 Trabajo Futuro

### Mejoras Técnicas
- [ ] Implementar técnicas de ensemble (Voting, Stacking, Boosting)
- [ ] Explorar redes neuronales (MLP, TabNet)
- [ ] Optimización bayesiana de hiperparámetros
- [ ] Cross-validation anidado
- [ ] Análisis de curvas de aprendizaje

### Explicabilidad
- [ ] Implementar SHAP (SHapley Additive exPlanations)
- [ ] Implementar LIME (Local Interpretable Model-agnostic Explanations)
- [ ] Análisis de dependencia parcial (PDP)
- [ ] Visualización de árboles de decisión

### Despliegue
- [ ] API REST con Flask/FastAPI
- [ ] Interfaz web con Streamlit
- [ ] Containerización con Docker
- [ ] Despliegue en la nube (AWS/GCP/Azure)

### Validación Clínica
- [ ] Colaboración con profesionales médicos
- [ ] Validación en datos externos
- [ ] Estudio de casos clínicos
- [ ] Análisis de impacto en decisiones médicas

---

## 📚 Referencias Bibliográficas

### Datasets
- UCI Machine Learning Repository
- Kaggle Medical Datasets

### Libros y Artículos
- Hastie, T., Tibshirani, R., & Friedman, J. (2009). *The Elements of Statistical Learning*
- Géron, A. (2019). *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow*
- Scikit-learn Documentation

### Contexto Médico
- Artículos de cardiología, obstetricia, hepatología y traumatología
- Guías clínicas de interpretación de pruebas diagnósticas

---

## 🏆 Logros del Proyecto

✅ **Análisis completo** de 4 datasets médicos diferentes  
✅ **Implementación exitosa** de 4 algoritmos de clasificación  
✅ **Documentación exhaustiva** con contexto médico  
✅ **Código reproducible** y bien organizado  
✅ **Visualizaciones profesionales** de resultados  
✅ **Insights médicos** relevantes identificados  
✅ **Repositorio listo para CV** y portfolio profesional  

---

## 👤 Sobre el Autor

**Nicolás Seivane**  
Estudiante de Tecnicatura en Inteligencia Artificial  
Universidad Nacional de Hurlingham

**Habilidades demostradas en este proyecto:**
- Machine Learning supervisado
- Análisis de datos médicos
- Python para Data Science
- Documentación técnica
- Pensamiento crítico y analítico

---

## 📞 Contacto

- **GitHub:** [@NicolasSeivane](https://github.com/NicolasSeivane)
- **LinkedIn:** [Nicolás Seivane](https://linkedin.com/in/nicolas-seivane)
- **Email:** [seivanenicolas@gmail.com](mailto:seivanenicolas@gmail.com)

---

## 📜 Licencia

Este proyecto es parte de un trabajo académico para la Universidad Nacional de Hurlingham.  
Desarrollado con fines educativos y de investigación.

---

**⭐ Si este proyecto te resulta útil o interesante, considera darle una estrella en GitHub!**

---

*Última actualización: Diciembre 2024*
