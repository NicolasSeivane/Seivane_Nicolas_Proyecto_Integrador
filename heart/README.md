# 🫀 Heart Disease Dataset

## Descripción

Este dataset contiene información médica de 746 pacientes para predecir la presencia de enfermedad cardíaca. Es un problema de **clasificación binaria** ampliamente utilizado en machine learning médico.

## 📊 Características del Dataset

### Variables Predictoras (11 atributos)

1. **Age** (Edad): Edad del paciente en años
2. **Sex** (Sexo): M = Masculino, F = Femenino
3. **ChestPainType** (Tipo de Dolor Torácico):
   - ATA: Angina Típica Asintomática
   - NAP: Dolor No Anginoso
   - ASY: Asintomático
   - TA: Angina Típica
4. **RestingBP** (Presión Arterial en Reposo): En mm Hg
5. **Cholesterol** (Colesterol): En mg/dl
6. **FastingBS** (Azúcar en Sangre en Ayunas): 1 si > 120 mg/dl, 0 en caso contrario
7. **RestingECG** (Electrocardiograma en Reposo):
   - Normal
   - ST: Anormalidad de onda ST-T
   - LVH: Hipertrofia ventricular izquierda
8. **MaxHR** (Frecuencia Cardíaca Máxima): Alcanzada durante prueba de esfuerzo
9. **ExerciseAngina** (Angina Inducida por Ejercicio): Y = Sí, N = No
10. **Oldpeak** (Depresión del ST): Inducida por ejercicio relativo al reposo
11. **ST_Slope** (Pendiente del Segmento ST):
    - Up: Ascendente
    - Flat: Plano
    - Down: Descendente

### Variable Objetivo

- **HeartDisease**: 0 = Sin enfermedad, 1 = Con enfermedad

## 📈 Estadísticas del Dataset

- **Total de registros**: 746 pacientes (después de limpieza)
- **Distribución de clases**:
  - Sin enfermedad: ~52%
  - Con enfermedad: ~48%
- **Valores nulos**: Ninguno (después de preprocesamiento)
- **Duplicados**: Eliminados

## 🔬 Preprocesamiento Aplicado

1. ✅ Eliminación de duplicados
2. ✅ Eliminación de registros con Colesterol = 0 (valores inválidos)
3. ✅ Codificación de variables categóricas (Label Encoding)
4. ✅ Normalización de variables numéricas (Z-score)

## 📓 Notebooks

### [01_proyecto_integrador_corazon.ipynb](01_proyecto_integrador_corazon.ipynb)
**Análisis Exploratorio de Datos (EDA)**
- Carga y limpieza del dataset
- Análisis estadístico descriptivo
- Visualización de distribuciones
- Análisis de correlaciones
- Identificación de outliers

### [02_entrenar_modelos.ipynb](02_entrenar_modelos.ipynb)
**Entrenamiento y Evaluación de Modelos**
- Implementación de 4 algoritmos:
  - Random Forest
  - Naive Bayes Gaussiano
  - Support Vector Machine (SVM)
  - Regresión Logística
- Validación cruzada estratificada (k=5)
- Comparación de métricas de rendimiento
- Análisis de importancia de características
- Generación de visualizaciones

## 🎯 Resultados Destacados

### Mejores Modelos
1. **Random Forest**: ~85% accuracy, ROC-AUC ~0.90
2. **SVM (RBF kernel)**: ~83% accuracy, ROC-AUC ~0.88
3. **Regresión Logística**: ~81% accuracy, ROC-AUC ~0.86

### Características Más Importantes
1. **ST_Slope** (Pendiente del segmento ST) - Indicador clave de isquemia
2. **ChestPainType** (Tipo de dolor torácico) - Síntoma primario
3. **ExerciseAngina** (Angina por ejercicio) - Indicador de esfuerzo cardíaco
4. **Oldpeak** (Depresión del ST) - Medida de cambios en ECG
5. **MaxHR** (Frecuencia cardíaca máxima) - Capacidad cardiovascular

## 📚 Contexto Médico

### ¿Qué es la Enfermedad Cardíaca?

La enfermedad cardíaca se refiere a varias condiciones que afectan el corazón, principalmente la **enfermedad arterial coronaria** (EAC), que puede llevar a ataques cardíacos.

### Importancia del Diagnóstico Temprano

- Las enfermedades cardiovasculares son la **principal causa de muerte** a nivel mundial
- La detección temprana puede salvar vidas mediante intervenciones preventivas
- El machine learning puede ayudar a identificar patrones que los médicos podrían pasar por alto

### Pruebas Diagnósticas Clave

- **ECG (Electrocardiograma)**: Mide la actividad eléctrica del corazón
- **Prueba de Esfuerzo**: Evalúa cómo responde el corazón al ejercicio
- **Análisis de Sangre**: Colesterol, azúcar en sangre, etc.

## 🔗 Referencias

- Dataset original: [UCI Machine Learning Repository - Heart Disease](https://archive.ics.uci.edu/ml/datasets/heart+disease)
- Fedesoriano. (2021). Heart Failure Prediction Dataset. Kaggle.

## 📊 Archivos de Resultados

Los archivos `.txt` en esta carpeta contienen:
- Resultados detallados de cada modelo
- Métricas de validación cruzada
- Importancia de características
- Matrices de confusión

---

**Nota**: Este análisis es con fines educativos y no debe utilizarse para diagnósticos médicos reales sin la supervisión de profesionales de la salud.
