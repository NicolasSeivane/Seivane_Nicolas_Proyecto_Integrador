# 👶 Cardiotocography Dataset (Cardiotocografía Fetal)

## Descripción

Este dataset contiene mediciones de **cardiotocografía fetal** (CTG), una técnica de monitoreo prenatal que registra la frecuencia cardíaca fetal y las contracciones uterinas. Es un problema de **clasificación multiclase** para evaluar el estado de salud del feto.

## 📊 Características del Dataset

### Variables Predictoras

El dataset incluye múltiples características extraídas de exámenes de cardiotocografía:

#### Frecuencia Cardíaca Fetal (FHR)
- **LB**: Línea base de la frecuencia cardíaca fetal
- **AC**: Número de aceleraciones por segundo
- **FM**: Número de movimientos fetales por segundo
- **UC**: Número de contracciones uterinas por segundo

#### Variabilidad
- **ASTV**: Porcentaje de tiempo con variabilidad anormal a corto plazo
- **MSTV**: Valor medio de la variabilidad a corto plazo
- **ALTV**: Porcentaje de tiempo con variabilidad anormal a largo plazo
- **MLTV**: Valor medio de la variabilidad a largo plazo

#### Histograma de FHR
- **Width**: Ancho del histograma
- **Min**: Mínimo del histograma
- **Max**: Máximo del histograma
- **Nmax**: Número de picos del histograma
- **Nzeros**: Número de ceros del histograma
- **Mode**: Moda del histograma
- **Mean**: Media del histograma
- **Median**: Mediana del histograma
- **Variance**: Varianza del histograma
- **Tendency**: Tendencia del histograma

#### Desaceleraciones
- **DP**: Número de desaceleraciones prolongadas
- **DS**: Número de desaceleraciones cortas
- **DL**: Número de desaceleraciones ligeras

### Variable Objetivo (NSP - Neonatal State Pattern)

- **1 - Normal**: Feto saludable
- **2 - Sospechoso**: Requiere monitoreo adicional
- **3 - Patológico**: Posible sufrimiento fetal, requiere intervención

## 📈 Estadísticas del Dataset

- **Total de registros**: ~2,126 exámenes de CTG
- **Distribución de clases**:
  - Normal: ~77%
  - Sospechoso: ~14%
  - Patológico: ~9%
- **Desbalanceo**: Presente (clase patológica minoritaria)

## 🔬 Preprocesamiento Aplicado

1. ✅ Eliminación de duplicados y valores nulos
2. ✅ Normalización de características numéricas
3. ✅ Manejo de desbalanceo de clases (Stratified K-Fold)
4. ✅ Codificación de variable objetivo

## 📓 Notebooks

### [01_proyecto_integrador_cardiografia.ipynb](01_proyecto_integrador_cardiografia.ipynb)
**Análisis Exploratorio de Datos (EDA)**
- Análisis de distribuciones de frecuencia cardíaca fetal
- Visualización de patrones normales vs patológicos
- Correlaciones entre variables
- Análisis de desbalanceo de clases

### [02_entrenar_modelos.ipynb](02_entrenar_modelos.ipynb)
**Entrenamiento y Evaluación de Modelos**
- Clasificación multiclase con 4 algoritmos
- Validación cruzada estratificada
- Métricas específicas para clases desbalanceadas
- Análisis de confusión entre clases Sospechoso/Patológico

## 🎯 Resultados Destacados

### Desafíos del Dataset
- **Desbalanceo de clases**: La clase patológica es minoritaria pero crítica
- **Similitud entre clases**: Casos sospechosos y patológicos pueden solaparse
- **Alta dimensionalidad**: Múltiples características correlacionadas

### Métricas Importantes
- **Recall en clase Patológica**: Crucial para no perder casos de riesgo
- **Precision en clase Normal**: Evitar alarmas falsas
- **F1-Score macro**: Balance entre todas las clases

## 📚 Contexto Médico

### ¿Qué es la Cardiotocografía?

La cardiotocografía (CTG) es una técnica de monitoreo fetal que registra simultáneamente:
- **Frecuencia cardíaca fetal (FHR)**: Latidos del corazón del bebé
- **Contracciones uterinas**: Actividad del útero materno

### ¿Cuándo se Utiliza?

- Durante el **tercer trimestre** del embarazo
- En el **trabajo de parto**
- En embarazos de **alto riesgo**
- Para detectar **sufrimiento fetal**

### Interpretación Clínica

#### Patrón Normal
- Línea base: 110-160 latidos por minuto
- Variabilidad moderada (6-25 lpm)
- Presencia de aceleraciones
- Ausencia de desaceleraciones

#### Patrón Patológico
- Bradicardia (<110 lpm) o taquicardia (>160 lpm)
- Variabilidad reducida o ausente
- Desaceleraciones tardías o variables severas
- Puede indicar hipoxia fetal

### Importancia del Machine Learning

- **Reducción de errores humanos**: La interpretación manual puede ser subjetiva
- **Detección temprana**: Identificar patrones sutiles de riesgo
- **Apoyo a la decisión clínica**: Herramienta complementaria para obstetras

## 🔗 Referencias

- Dataset original: [UCI Machine Learning Repository - Cardiotocography](https://archive.ics.uci.edu/ml/datasets/cardiotocography)
- Ayres de Campos et al. (2000). SisPorto 2.0: A Program for Automated Analysis of Cardiotocograms.

## 📊 Archivos de Resultados

Los archivos `.txt` contienen:
- Resultados de clasificación multiclase
- Matrices de confusión detalladas
- Métricas por clase (Normal, Sospechoso, Patológico)
- Análisis de errores de clasificación

---

**Nota**: Este análisis es con fines educativos. Las decisiones clínicas deben ser tomadas por profesionales médicos calificados considerando el contexto completo del paciente.
