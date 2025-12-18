# 🔬 Cirrhosis Dataset (Cirrosis Hepática)

## Descripción

Este dataset contiene información clínica de pacientes con **cirrosis hepática**, una enfermedad crónica del hígado. Es un problema de **clasificación multiclase** para predecir el estado de progresión de la enfermedad.

## 📊 Características del Dataset

### Variables Predictoras

#### Datos Demográficos
- **Age** (Edad): Edad del paciente en años
- **Sex** (Sexo): M = Masculino, F = Femenino

#### Datos Clínicos
- **Ascites** (Ascitis): Acumulación de líquido en el abdomen (Y/N)
- **Hepatomegaly** (Hepatomegalia): Agrandamiento del hígado (Y/N)
- **Spiders** (Arañas Vasculares): Lesiones vasculares en la piel (Y/N)
- **Edema**: Retención de líquidos
  - N: Sin edema
  - S: Edema sin diuréticos
  - Y: Edema a pesar de diuréticos

#### Parámetros de Laboratorio
- **Bilirubin** (Bilirrubina): Nivel en sangre (mg/dl)
- **Cholesterol** (Colesterol): Nivel sérico (mg/dl)
- **Albumin** (Albúmina): Proteína sérica (g/dl)
- **Copper** (Cobre): Nivel en orina (μg/día)
- **Alk_Phos** (Fosfatasa Alcalina): Enzima hepática (U/L)
- **SGOT** (AST): Transaminasa (U/ml)
- **Tryglicerides** (Triglicéridos): Nivel en sangre (mg/dl)
- **Platelets** (Plaquetas): Recuento (por mm³)
- **Prothrombin** (Protrombina): Tiempo de coagulación (segundos)

#### Tratamiento
- **Drug** (Medicamento): D-penicilamina o Placebo

### Variable Objetivo (Status)

- **C - Censored**: Paciente vivo al final del estudio
- **CL - Censored due to liver transplant**: Trasplante hepático
- **D - Death**: Fallecimiento

## 📈 Estadísticas del Dataset

- **Total de registros**: ~418 pacientes
- **Período de seguimiento**: Varios años
- **Valores faltantes**: Presentes en algunas variables de laboratorio
- **Distribución de clases**: Desbalanceada (mayoría censurados)

## 🔬 Preprocesamiento Aplicado

1. ✅ Imputación de valores faltantes
2. ✅ Codificación de variables categóricas
3. ✅ Normalización de parámetros de laboratorio
4. ✅ Manejo de outliers en valores extremos
5. ✅ Balanceo de clases para entrenamiento

## 📓 Notebooks

### [01_proyecto_integrador_cirrosis.ipynb](01_proyecto_integrador_cirrosis.ipynb)
**Análisis Exploratorio de Datos (EDA)**
- Análisis de parámetros hepáticos
- Visualización de progresión de la enfermedad
- Correlaciones entre marcadores clínicos
- Análisis de supervivencia

### [02_entrenar_modelos_cirrosis.ipynb](02_entrenar_modelos_cirrosis.ipynb)
**Entrenamiento y Evaluación de Modelos**
- Clasificación multiclase del estado del paciente
- Validación cruzada estratificada
- Análisis de importancia de biomarcadores
- Predicción de progresión de la enfermedad

## 🎯 Resultados Destacados

### Características Más Importantes
1. **Bilirubin** (Bilirrubina): Indicador clave de función hepática
2. **Albumin** (Albúmina): Marcador de síntesis hepática
3. **Prothrombin** (Protrombina): Función de coagulación
4. **Age** (Edad): Factor de riesgo importante
5. **Ascites** (Ascitis): Signo de descompensación

### Desafíos del Dataset
- **Valores faltantes**: Común en datos clínicos reales
- **Desbalanceo**: Pocos eventos de muerte comparado con censurados
- **Censura**: Pacientes perdidos en el seguimiento
- **Heterogeneidad**: Diferentes estadios de la enfermedad

## 📚 Contexto Médico

### ¿Qué es la Cirrosis Hepática?

La cirrosis es la **cicatrización irreversible del hígado** causada por daño crónico. El tejido sano es reemplazado por tejido cicatricial, impidiendo el funcionamiento normal del hígado.

### Causas Principales
- **Alcoholismo crónico**
- **Hepatitis B y C**
- **Enfermedad del hígado graso no alcohólico (NAFLD)**
- **Enfermedades autoinmunes**
- **Cirrosis biliar primaria (CBP)** - Relevante para este dataset

### Estadios de la Cirrosis

#### Cirrosis Compensada
- El hígado aún funciona relativamente bien
- Pocos o ningún síntoma
- Puede detectarse en análisis de sangre o imágenes

#### Cirrosis Descompensada
- Función hepática severamente deteriorada
- Síntomas: ascitis, ictericia, encefalopatía
- Complicaciones graves
- Puede requerir trasplante hepático

### Marcadores Clínicos Importantes

#### Bilirrubina Elevada
- Indica incapacidad del hígado para procesar bilirrubina
- Causa ictericia (coloración amarillenta)
- Niveles altos = peor pronóstico

#### Albúmina Baja
- El hígado produce albúmina
- Niveles bajos indican función sintética deteriorada
- Asociado con ascitis y edema

#### Tiempo de Protrombina Prolongado
- El hígado produce factores de coagulación
- Prolongación indica riesgo de sangrado
- Componente del score de Child-Pugh

### Score de Child-Pugh

Sistema de clasificación que evalúa la severidad de la cirrosis usando:
1. Bilirrubina
2. Albúmina
3. Tiempo de protrombina (INR)
4. Ascitis
5. Encefalopatía

### Importancia del Machine Learning

- **Predicción de supervivencia**: Identificar pacientes de alto riesgo
- **Priorización de trasplantes**: Asignar órganos a quienes más lo necesitan
- **Personalización del tratamiento**: Ajustar terapias según el riesgo
- **Detección temprana de descompensación**: Intervenir antes de complicaciones

## 🔗 Referencias

- Dataset original: [UCI Machine Learning Repository - Cirrhosis](https://archive.ics.uci.edu/ml/datasets/Cirrhosis+Patient+Survival+Prediction)
- Fleming & Harrington (1991). Counting Processes and Survival Analysis.

## 📊 Archivos de Resultados

Los archivos `.txt` contienen:
- Resultados de clasificación de estado del paciente
- Métricas de predicción de supervivencia
- Importancia de biomarcadores
- Análisis de factores de riesgo

---

**Nota**: Este análisis es con fines educativos y de investigación. Las decisiones clínicas sobre pacientes con cirrosis deben ser tomadas por hepatólogos y equipos médicos especializados.
