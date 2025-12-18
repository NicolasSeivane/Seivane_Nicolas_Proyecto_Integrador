# 🦴 Vertebral Column Dataset (Columna Vertebral)

## Descripción

Este dataset contiene **mediciones biomecánicas de la pelvis y columna vertebral** para clasificar pacientes en diferentes categorías de patologías vertebrales. Es un problema de **clasificación multiclase** basado en características físicas y posturales.

## 📊 Características del Dataset

### Variables Predictoras (6 atributos biomecánicos)

#### Ángulos Pélvicos
1. **Pelvic Incidence** (Incidencia Pélvica)
   - Ángulo entre la línea perpendicular al plato sacro y la línea que conecta el punto medio del plato sacro con el centro de las cabezas femorales
   - Parámetro morfológico fijo (no cambia con la postura)
   - Rango normal: 40-65°

2. **Pelvic Tilt** (Inclinación Pélvica)
   - Ángulo entre la vertical y la línea que conecta el punto medio del plato sacro con el centro de las cabezas femorales
   - Parámetro postural (varía con la posición)
   - Rango normal: 10-25°

3. **Pelvic Radius** (Radio Pélvico)
   - Distancia entre el centro de las cabezas femorales y el punto medio del plato sacro
   - Medida en milímetros

#### Ángulos Espinales
4. **Lumbar Lordosis Angle** (Ángulo de Lordosis Lumbar)
   - Curvatura hacia adelante de la columna lumbar
   - Rango normal: 40-60°
   - Lordosis excesiva o reducida puede indicar patología

5. **Sacral Slope** (Pendiente Sacra)
   - Ángulo entre el plato sacro superior y la horizontal
   - Parámetro postural
   - Rango normal: 30-50°

6. **Degree of Spondylolisthesis** (Grado de Espondilolistesis)
   - Desplazamiento anterior de una vértebra sobre otra
   - Medido en milímetros o porcentaje
   - 0 = sin desplazamiento

### Variable Objetivo (Class)

- **Normal (NO)**: Sin patología vertebral
- **Disk Hernia (DH)**: Hernia de disco
- **Spondylolisthesis (SL)**: Espondilolistesis

## 📈 Estadísticas del Dataset

- **Total de registros**: 310 pacientes
- **Distribución de clases**:
  - Normal: ~100 pacientes
  - Hernia de Disco: ~60 pacientes
  - Espondilolistesis: ~150 pacientes
- **Todas las características**: Numéricas continuas
- **Sin valores faltantes**

## 🔬 Preprocesamiento Aplicado

1. ✅ Normalización de características (Z-score)
2. ✅ Análisis de correlaciones entre parámetros
3. ✅ Validación de rangos biomecánicos
4. ✅ Balanceo de clases en validación cruzada

## 📓 Notebooks

### [01_proyecto_integrador_columna_vertebral.ipynb](01_proyecto_integrador_columna_vertebral.ipynb)
**Análisis Exploratorio de Datos (EDA)**
- Análisis de parámetros biomecánicos
- Visualización de distribuciones por clase
- Correlaciones entre ángulos pélvicos y espinales
- Identificación de patrones patológicos

### [02_entrenar_modelos_vertebras.ipynb](02_entrenar_modelos_vertebras.ipynb)
**Entrenamiento y Evaluación de Modelos**
- Clasificación multiclase de patologías
- Validación cruzada estratificada
- Análisis de importancia de parámetros biomecánicos
- Comparación de rendimiento entre algoritmos

## 🎯 Resultados Destacados

### Características Más Importantes
1. **Degree of Spondylolisthesis**: Discrimina directamente la espondilolistesis
2. **Pelvic Incidence**: Parámetro morfológico clave
3. **Lumbar Lordosis Angle**: Indica alteraciones posturales
4. **Sacral Slope**: Relacionado con la alineación espinal
5. **Pelvic Tilt**: Compensación postural

### Relaciones Biomecánicas Clave

**Ecuación de Duval-Beaupère:**
```
Pelvic Incidence = Pelvic Tilt + Sacral Slope
```

Esta relación matemática conecta parámetros morfológicos y posturales.

## 📚 Contexto Médico

### Anatomía de la Columna Vertebral

La columna vertebral tiene **curvaturas naturales**:
- **Lordosis cervical**: Curvatura hacia adelante en el cuello
- **Cifosis torácica**: Curvatura hacia atrás en la parte media
- **Lordosis lumbar**: Curvatura hacia adelante en la parte baja
- **Cifosis sacra**: Curvatura hacia atrás en el sacro

### Patologías Analizadas

#### 1. Hernia de Disco (Disk Hernia)

**¿Qué es?**
- El núcleo pulposo del disco intervertebral se desplaza a través de una fisura en el anillo fibroso
- Puede comprimir nervios espinales

**Síntomas:**
- Dolor lumbar (lumbalgia)
- Dolor irradiado a piernas (ciática)
- Hormigueo o debilidad muscular
- En casos severos: pérdida de control de esfínteres

**Factores de Riesgo:**
- Edad (degeneración discal)
- Sobrepeso
- Movimientos repetitivos de flexión/torsión
- Sedentarismo

#### 2. Espondilolistesis (Spondylolisthesis)

**¿Qué es?**
- Deslizamiento anterior de una vértebra sobre la inferior
- Más común en L5 sobre S1

**Grados de Severidad:**
- Grado I: Desplazamiento <25%
- Grado II: 25-50%
- Grado III: 50-75%
- Grado IV: 75-100%
- Grado V: >100% (espondiloptosis)

**Tipos:**
- **Ístmica**: Por defecto en la pars interarticularis (más común en jóvenes)
- **Degenerativa**: Por desgaste articular (más común en adultos mayores)
- **Traumática**: Por fractura
- **Congénita**: Malformación desde el nacimiento

**Síntomas:**
- Dolor lumbar bajo
- Rigidez en la espalda
- Dolor en glúteos y muslos
- Postura encorvada
- Dificultad para caminar

### Parámetros Espino-Pélvicos en Patología

#### En Espondilolistesis:
- ↑ **Pelvic Incidence**: Mayor que en población normal
- ↑ **Sacral Slope**: Pendiente sacra aumentada
- ↑ **Lumbar Lordosis**: Lordosis excesiva
- ↑ **Degree of Spondylolisthesis**: Por definición

#### En Hernia de Disco:
- Parámetros más variables
- Puede haber pérdida de lordosis lumbar (espalda plana)
- Inclinación pélvica puede aumentar como compensación

### Diagnóstico Clínico

**Métodos de Imagen:**
- **Radiografía lateral**: Mide ángulos espino-pélvicos
- **Resonancia Magnética (MRI)**: Visualiza discos y nervios
- **Tomografía Computarizada (CT)**: Detalles óseos

**Evaluación Física:**
- Prueba de elevación de pierna recta (Lasègue)
- Evaluación neurológica (reflejos, fuerza, sensibilidad)
- Análisis de la marcha

### Tratamiento

#### Conservador:
- Fisioterapia
- Medicamentos antiinflamatorios
- Modificación de actividades
- Ejercicios de fortalecimiento del core

#### Quirúrgico:
- **Discectomía**: Remoción de hernia de disco
- **Fusión espinal**: Para espondilolistesis severa
- **Laminectomía**: Descompresión neural

### Importancia del Machine Learning

- **Diagnóstico asistido**: Clasificación basada en mediciones objetivas
- **Screening masivo**: Identificar pacientes de riesgo en radiografías
- **Planificación quirúrgica**: Predecir necesidad de intervención
- **Seguimiento postoperatorio**: Evaluar resultados del tratamiento
- **Medicina preventiva**: Identificar factores de riesgo temprano

## 🔗 Referencias

- Dataset original: [UCI Machine Learning Repository - Vertebral Column](https://archive.ics.uci.edu/ml/datasets/vertebral+column)
- Berthonnaud et al. (2005). Analysis of the sagittal balance of the spine and pelvis using shape and orientation parameters.

## 📊 Archivos de Resultados

Los archivos `.txt` contienen:
- Resultados de clasificación multiclase
- Matrices de confusión (Normal vs DH vs SL)
- Importancia de parámetros biomecánicos
- Análisis de errores de clasificación

---

**Nota**: Este análisis es con fines educativos y de investigación. El diagnóstico y tratamiento de patologías vertebrales debe ser realizado por médicos especialistas (traumatólogos, neurocirujanos, fisiatras) con evaluación clínica completa e imágenes médicas.
