# Conclusiones

Realizado este trabajo pude confirmar que es posible anticipar con un desempeño razonable la probabilidad de un monoplaza haga una parada en pits en la vuelta siguiente usando variables de contexto de carrera, estado de neumáticos y rendimiento de vuelta.

El modelo con mejor equilibrio se seleccionó usando F1-score, porque la clase positiva (`PitNextLap = 1`) es a mi parecer la más importante para la toma de decisiones estratégicas. En este problema, no basta con acertar muchas vueltas sin parada: lo valioso es detectar correctamente cuándo la parada se acerca.

Desde el análisis no supervisado, los clusters separan vueltas tempranas, vueltas avanzadas con neumáticos usados y vueltas de rendimiento intermedio. Esto aporta una lectura estratégica adicional, porque permite describir perfiles de carrera sin depender de una etiqueta previa.

Limitaciones:
- El dataset no incluye clima, safety car, tráfico, degradación real por equipo ni información de rivales cercanos.
- Los tiempos de vuelta extremos fueron filtrados para mejorar estabilidad, pero podrían representar eventos importantes de carrera.
- El modelo se debe validar con nuevas carreras antes de utilizarse como herramienta operacional.

Mejora futura:
Incorporar variables de clima, circuito, distancia respecto al rival, ventanas de parada y datos históricos por piloto/equipo para construir un modelo más cercano a una estrategia real de Fórmula 1.
