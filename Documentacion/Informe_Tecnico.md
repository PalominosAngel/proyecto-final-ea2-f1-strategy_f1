# Informe Técnico - Proyecto Final EA2

## 1. Contexto del proyecto

El proyecto trabaja con un dataset de Fórmula 1 orientado al análisis de estrategia de carrera. El objetivo principal es anticipar si un piloto realizará una parada en pits en la siguiente vuelta (`PitNextLap`) a partir de variables como piloto, equipo, circuito, compuesto de neumático, vida del neumático, posición, tiempo de vuelta y progreso de carrera.

## 2. Preparación de datos

Se cargó el dataset original desde `Dataset/Antes`. Luego se revisaron dimensiones, tipos de datos, valores nulos, duplicados y comportamiento general de las variables numéricas y categóricas.

Las principales decisiones de preprocesamiento fueron:

- Imputar valores faltantes de `Compound` con `UNKNOWN`.
- Filtrar valores extremos de `LapTime (s)` usando percentiles 1% y 99%.
- Separar variables numéricas y categóricas.
- Aplicar imputación y normalización a variables numéricas.
- Aplicar imputación y codificación One-Hot a variables categóricas.

## 3. Modelado supervisado

La variable objetivo fue `PitNextLap`, planteada como un problema de clasificación binaria. Se compararon modelos supervisados y se evaluaron usando métricas como accuracy, F1-score y AUC.

El F1-score se consideró especialmente importante porque el interés principal no es solo acertar vueltas sin parada, sino detectar correctamente las vueltas donde sí podría ocurrir una parada.

## 4. Optimización

Se aplicó `GridSearchCV` sobre un árbol de decisión, ajustando hiperparámetros como profundidad máxima y cantidad mínima de muestras por hoja. Esto permitió mejorar el rendimiento y documentar una decisión técnica basada en evidencia.

## 5. Modelado no supervisado

Se aplicó K-Means para segmentar vueltas de carrera y PCA para visualizar los grupos en dos dimensiones. Esta parte complementa el análisis predictivo, permitiendo observar patrones generales de comportamiento estratégico.

## 6. Visualizaciones

El proyecto incluye gráficos para:

- Distribución de compuestos.
- Tasa de parada en pits por compuesto.
- Relación entre vida del neumático y tiempo de vuelta.
- Comparación de métricas de modelos.
- Matriz de confusión.
- Visualización de clusters con PCA.

## 7. Conclusión técnica

El flujo implementado cumple con las fases principales de un proyecto de ciencia de datos: exploración, limpieza, preparación, modelado, optimización, evaluación, visualización y documentación. Además, la estructura de carpetas permite una entrega ordenada y reproducible.
