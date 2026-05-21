# Proyecto Final EA2 - De los datos al conocimiento

## Tema
Análisis de estrategia de Fórmula 1 para predecir si un piloto realizará una parada en pits en la vuelta siguiente (`PitNextLap`).

## Objetivo
Construir un flujo completo de ciencia de datos: exploración, limpieza, modelado supervisado, modelado no supervisado, optimización, evaluación, visualización y conclusiones.

## Dataset
- Archivo base: `f1_strategy_dataset_v4.csv`
- Registros originales: 101,371
- Variables originales: 16
- Registros después de limpieza: 99,343
- Valores faltantes detectados en `Compound`: 66

## Decisiones de preparación
1. Se imputó `Compound` con `UNKNOWN` para no eliminar registros útiles.
2. Se filtraron tiempos de vuelta extremos usando percentiles 1 y 99 (`70.185` a `139.838` segundos), porque valores muy altos distorsionan el análisis.
3. Se codificaron variables categóricas con One-Hot Encoding.
4. Se escalaron variables numéricas para los modelos sensibles a magnitud.

## Modelado supervisado
Variable objetivo: `PitNextLap`.

Modelos comparados:
- Regresión Logística
- Árbol de Decisión Base
- Árbol de Decisión Optimizado con GridSearchCV

Mejor modelo por F1-score: **Árbol Base**.

## Modelado no supervisado
Se aplicó K-Means para segmentar vueltas según variables de carrera y luego PCA para visualizar los grupos en dos dimensiones.

## Estructura
```
Dataset/
  Antes/
  Despues/
Notebook/
  notebook_f1_strategy_final.ipynb
Visualizaciones/
Documentacion/
  README.md
  Conclusiones.md
scripts/
  requirements.txt
```

## Ejecución
```bash
pip install -r scripts/requirements.txt
jupyter notebook Notebook/notebook_f1_strategy_final.ipynb
```
