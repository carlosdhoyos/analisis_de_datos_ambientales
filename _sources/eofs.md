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


## Python

```{code-cell} python
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

```

### Python: Matplotlib Interactive I

```{code-cell} python
import numpy as np
import plotly.graph_objects as go
from plotly.offline import init_notebook_mode

# Initialize Plotly to work in notebook mode for Jupyter environments
init_notebook_mode(connected=True)

# Define ranges for temperature (T) and pressure (P)
T = np.linspace(300, 700, 50)  # Temperature from 300K to 700K
P = np.linspace(1, 10, 50)     # Pressure from 1 to 10 atm
T, P = np.meshgrid(T, P)

# Equation for volume V, using the ideal gas law: PV = nRT
R = 0.0821  # Ideal gas constant in L·atm/mol·K
n = 1       # Assume 1 mole of gas
V = (n * R * T) / P  # Rearranged ideal gas law to V = nRT / P

# Create an interactive 3D surface plot with Plotly
fig = go.Figure(data=[go.Surface(z=V, x=P, y=T, colorscale="Plasma")])

# Update layout for the plot
fig.update_layout(
    title="Ideal Gas Law: Volume as a Function of Pressure and Temperature",
    scene=dict(
        xaxis_title="Pressure (P) [atm]",
        yaxis_title="Temperature (T) [K]",
        zaxis_title="Volume (V) [L]",
        camera=dict(eye=dict(x=1.2, y=1.2, z=0.8))  # Set view angle
    ),
    coloraxis_colorbar=dict(
        title="Volume [L]",
        titleside="right"
    )
)

# Show plot
fig.show()
```
