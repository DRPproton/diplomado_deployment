# Caché y Rendimiento

A medida que tus aplicaciones de Streamlit crecen en complejidad, es fundamental pensar en el rendimiento y en la **optimización** de operaciones costosas. Streamlit ofrece mecanismos de **caché** que evitan la recarga innecesaria de datos o la reejecución de funciones pesadas en cada interacción.

---

## `st.cache_data` vs `st.cache_resource`

En versiones recientes, Streamlit introdujo nuevos decoradores para el manejo de caché. Los dos más relevantes son:

1. **`st.cache_data`**

   - Orientado a **datos** que se recalculan con frecuencia o que pueden variar.
   - Adecuado para lectura de CSV, creación de DataFrames, etc.
   - Permite invalidar el caché cuando cambian los argumentos de la función.

2. **`st.cache_resource`**
   - Orientado a **recursos** que no cambian con frecuencia, como la carga de un modelo de ML en memoria.
   - Permite reutilizar objetos costosos sin necesidad de recalcular o volver a cargar.

### Ejemplo: `st.cache_data` para Datos

```python
import streamlit as st
import pandas as pd
import time

@st.cache_data
def cargar_datos():
    # Simulamos una operación costosa con sleep
    time.sleep(3)
    url = "https://raw.githubusercontent.com/mwaskom/seaborn-data/master/iris.csv"
    return pd.read_csv(url)

st.title("Ejemplo de st.cache_data")

inicio = time.time()
df = cargar_datos()
fin = time.time()

st.write(f"Tiempo de carga: {fin - inicio:.2f} segundos")
st.write(df.head())
```

### Ejemplo: `st.cache_resource` para Modelos de ML

```python
import streamlit as st
import pickle
import time

@st.cache_resource
def cargar_modelo():
    # Simula una carga costosa de un modelo
    time.sleep(5)
    with open("modelo_entrenado.pkl", "rb") as f:
        modelo = pickle.load(f)
    return modelo

st.title("Ejemplo de st.cache_resource")

inicio = time.time()
modelo = cargar_modelo()
fin = time.time()

st.write(f"Tiempo de carga del modelo: {fin - inicio:.2f} segundos")

# Uso del modelo de ejemplo
# prediccion = modelo.predict(...)
# st.write(prediccion)
```

## Mejores Prácticas para Guardar en Caché

1. **Identifica Funciones Costosas:**

   - Carga de grandes archivos CSV o bases de datos.
   - Descarga de datos desde un servidor externo.
   - Carga de modelos de ML pesados.
   - Procesamiento de datos extenso (limpieza, agregaciones, etc.).

2. **Decora Estratégicamente:**

   - Usa `@st.cache_data` cuando la función devuelva **datos** que podrían cambiar si cambian los parámetros de entrada.
   - Usa `@st.cache_resource` para objetos que **no** cambian, como modelos entrenados o resultados muy estáticos.

3. **Controla la Invalidación de Caché:**

   - Streamlit invalida el caché si cambian los argumentos o el código de la función.
   - Evita operaciones con variables globales que puedan cambiar de forma impredecible.

4. **Evita el Uso Excesivo de Caché:**

   - No marques con caché funciones que se ejecutan rápido o que no requieren almacenamiento (podrías consumir memoria innecesariamente).
   - Decorar demasiado puede obstaculizar el rendimiento en lugar de mejorarlo.

5. **Atención al Consumo de Memoria:**
   - Ten en cuenta el tamaño de los objetos almacenados en caché, especialmente si manejas múltiples datasets grandes.

### Ejemplo Completo: Carga de Datos + Carga de Modelo

```python
import streamlit as st
import pandas as pd
import pickle
import numpy as np
import time

@st.cache_data
def load_data(url):
    time.sleep(3)  # simular carga costosa
    return pd.read_csv(url)

@st.cache_resource
def load_model(path):
    time.sleep(5)  # simular carga costosa
    with open(path, "rb") as f:
        model = pickle.load(f)
    return model

st.title("Caché y Rendimiento: Datos + Modelo")

# Cargamos un dataset de ejemplo
iris_url = "https://raw.githubusercontent.com/mwaskom/seaborn-data/master/iris.csv"
df = load_data(iris_url)
st.write("## Muestra del Dataset de Iris")
st.dataframe(df.head())

# Cargamos un modelo (simulado)
modelo = load_model("modelo_entrenado.pkl")
st.write("## Modelo cargado con st.cache_resource")

# Supongamos que realizamos una predicción
dummy_input = np.array([[5.1, 3.5, 1.4, 0.2]])
# prediccion = modelo.predict(dummy_input)
# st.write("Predicción:", prediccion)

```

## Recursos Adicionales

- **Documentación Oficial sobre Caché de Datos (`st.cache_data`):**  
  [https://docs.streamlit.io/library/api-reference/performance/st.cache_data](https://docs.streamlit.io/library/api-reference/performance/st.cache_data)

- **Documentación Oficial sobre Caché de Recursos (`st.cache_resource`):**  
  [https://docs.streamlit.io/library/api-reference/performance/st.cache_resource](https://docs.streamlit.io/library/api-reference/performance/st.cache_resource)

- **Mejores Prácticas de Rendimiento en Streamlit:**  
  [https://docs.streamlit.io/library/advanced-features/performance](https://docs.streamlit.io/library/advanced-features/performance)
