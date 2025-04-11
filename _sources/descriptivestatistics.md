---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---


# Introducción a la Estadística Descriptiva en Datos Ambientales

## Objetivos del Capítulo
- Comprender la importancia de la estadística en el análisis de datos ambientales.
- Aplicar herramientas básicas de estadística descriptiva para explorar y resumir datos.
- Interpretar tendencias, patrones y variabilidad en variables climáticas, meteorológicas o ecológicas.

## ¿Por qué usar estadística en datos ambientales?

Los datos ambientales suelen ser **multivariados, extensos y variables en el tiempo y el espacio**. Desde la temperatura del aire hasta los niveles de contaminación, los datos se generan constantemente por sensores, modelos y observaciones de campo. La estadística permite:

- **Resumir grandes volúmenes de datos** en valores clave.
- **Visualizar patrones y anomalías**.
- **Comparar regiones, periodos o escenarios**.
- Tomar decisiones informadas sobre, por ejemplo, el cambio climático, gestión ambiental, riesgos, etc.

> *Pregunta ejemplo*: ¿Cuál ha sido la temperatura promedio en los últimos 30 años en Medellín? ¿Hay evidencia de un cambio significativo?

## Tipos de Datos Ambientales

- **Escala temporal**: diaria, mensual, anual (ej. precipitación diaria).
- **Escala espacial**: puntos (estaciones), celdas de grilla, cuencas.
- **Tipo de variable**: 
  - Cuantitativas: temperatura, concentración de CO₂.
  - Cualitativas: tipo de cobertura del suelo, clase de riesgo.

## Medidas de Tendencia Central

- **Media**: promedio aritmético.
- **Mediana**: valor central que divide los datos en dos mitades.
- **Moda**: valor que ocurre con mayor frecuencia.

## Medidas de Dispersión

- **Rango**: diferencia entre el valor máximo y mínimo.
- **Varianza**: medida de la dispersión cuadrática de los datos.
- **Desviación estándar**: raíz cuadrada de la varianza.
- **Coeficiente de variación**: dispersión relativa (útil para comparar regiones o variables).


## Distribuciones de Datos Ambientales

- **Distribución normal**: común en temperaturas.
- **Distribución sesgada**: frecuente en precipitaciones (lluvia concentrada en pocos días).
- **Visualización**: histogramas, boxplots, gráficos de densidad.


## Herramientas y Software

- **Python**: `pandas`, `numpy`, `matplotlib`, `seaborn`.
- **Visualización interactiva**: uso de dashboards o notebooks.


## Python

```{code-cell} python
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

# Create a figure
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

# Define ranges for temperature (T) and pressure (P)
T = np.linspace(300, 700, 50)  # Temperature from 300K to 700K
P = np.linspace(1, 10, 50)     # Pressure from 1 to 10 atm
T, P = np.meshgrid(T, P)

# Equation for volume V, assume ideal gas law: PV = nRT
R = 0.0821  # L·atm/mol·K (Ideal gas constant)
n = 1       # Assume 1 mole of gas
V = (n * R * T) / P  # Ideal gas law rearranged to V = nRT / P

# Plot the surface in color
surf = ax.plot_surface(P, T, V, cmap='plasma', edgecolor='none')

# Color bar for the surface
fig.colorbar(surf, ax=ax, shrink=0.5, aspect=5)

# Label axes with units
ax.set_xlabel('Pressure (P) [atm]', fontsize=12)
ax.set_ylabel('Temperature (T) [K]', fontsize=12)
ax.set_zlabel('Volume (V) [L]', fontsize=12)

# Rotate the plot by 90 degrees
ax.view_init(elev=40, azim=50)  # azim=90 rotates it by 90 degrees

plt.show()
```
