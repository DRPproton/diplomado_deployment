## 4. Visualización de Datos

Streamlit facilita la visualización de datos y la creación de gráficos de forma intuitiva. A continuación, se describen algunas funciones clave:

1. **Mostrar DataFrames**

   - `st.dataframe(df)`: Muestra un DataFrame con opciones para hacer scroll y ordenarlo.
   - `st.table(df)`: Muestra el DataFrame como una tabla estática sin opciones de interacción.

2. **Gráficos Rápidos**

   - `st.line_chart(data)`: Genera un gráfico de líneas rápido a partir de un DataFrame o array.
   - `st.bar_chart(data)`: Genera un gráfico de barras rápido.
   - `st.map(data)`: Muestra un mapa con puntos basados en coordenadas (latitud, longitud).

3. **Integración con Librerías Externas**  
   Streamlit se integra sin problemas con librerías como **Matplotlib**, **Seaborn** o **Plotly**.
   - **Matplotlib:** Usa `st.pyplot(fig)` para mostrar un gráfico creado con matplotlib.
   - **Seaborn:** Normalmente, Seaborn genera gráficos con matplotlib, por lo que también se usan `matplotlib.pyplot` y luego `st.pyplot(fig)`.
   - **Plotly:** Usa `st.plotly_chart(fig)` para renderizar gráficos interactivos.

### Ejemplo de Visualización

```python
import streamlit as st
import pandas as pd
import numpy as np

st.title("Ejemplo de Visualización de Datos")

# 1. Mostrar un DataFrame
df = pd.DataFrame({
    'Columna A': [1, 2, 3, 4],
    'Columna B': ['X', 'Y', 'Z', 'W']
})
st.write("## Tabla de Datos")
st.dataframe(df)

# 2. Gráficos Rápidos
st.write("## Gráfico de Líneas Aleatorio")
random_data = pd.DataFrame(np.random.randn(20, 3), columns=['A', 'B', 'C'])
st.line_chart(random_data)

# 3. Mapa
st.write("## Mapa Aleatorio")
map_data = pd.DataFrame(
    np.random.randn(100, 2) / [50, 50] + [37.76, -122.4],
    columns=['lat', 'lon']
)
st.map(map_data)

```

## Recursos Adicionales

**Recursos de Visualización en Streamlit:**

- [Documentación Oficial de Streamlit (Elementos de Datos)](https://docs.streamlit.io/library/api-reference/data)
- [Introducción a Plotly](https://plotly.com/python/) para gráficos más avanzados e interactivos
- [Guía de Seaborn](https://seaborn.pydata.org/) para visualizaciones estadísticas
- [Referencia de Matplotlib](https://matplotlib.org/stable/contents.html) para gráficos personalizados
