# Diseño Avanzado y Gestión de Estado

A medida que desarrollas aplicaciones más complejas en Streamlit, es importante explorar **disposiciones de diseño avanzadas** y la **gestión de estado** de tu aplicación. Estas funcionalidades te permitirán organizar la interfaz de manera más profesional y mantener datos persistentes a través de las interacciones del usuario.

---

## Uso de `st.sidebar`, `st.columns`, `st.expander`

### 1. `st.sidebar`

En lugar de mostrar todos los controles y elementos en la parte central, puedes colocar elementos en una **barra lateral**. Esto ayuda a despejar la vista principal y facilita la navegación.

```python
import streamlit as st

st.title("Ejemplo de Barra Lateral")

# Agregamos un slider en la barra lateral
valor_slider = st.sidebar.slider("Selecciona un valor", 0, 100, 50)
st.write(f"El valor seleccionado es: {valor_slider}")

# Un botón en la barra lateral
boton = st.sidebar.button("Presionar Botón")
if boton:
    st.write("¡Botón presionado desde la barra lateral!")
```

### 2. `st.columns`

Esta función te permite dividir la interfaz en varias columnas. Cada columna puede contener componentes independientes.

```python
import streamlit as st

st.title("Ejemplo de Columnas")

col1, col2, col3 = st.columns(3)

with col1:
    st.header("Columna 1")
    st.write("Texto y widgets en la primera columna.")

with col2:
    st.header("Columna 2")
    numero = st.number_input("Ingresa un número")
    st.write(f"Número ingresado: {numero}")

with col3:
    st.header("Columna 3")
    if st.button("Botón en 3ra Columna"):
        st.write("¡Se presionó el botón en la columna 3!")

```

### 3. `st.expander`

`st.expander` te permite ocultar y mostrar secciones de contenido de manera opcional. Esto es útil cuando tu aplicación tiene secciones largas o información adicional que no quieres que ocupe espacio de forma permanente.

```python
import streamlit as st

st.title("Ejemplo de Expander")

with st.expander("Haz clic para ver más información"):
    st.write("Este contenido está oculto por defecto.")
    st.write("Puedes incluir tablas, imágenes o más texto aquí.")

```

## Persistencia de Estado con st.session_state

Una característica importante de Streamlit es que el script se recarga cada vez que el usuario interactúa. Si deseas guardar información entre interacciones (por ejemplo, contadores, selecciones personalizadas o resultados de operaciones pesadas), puedes usar st.session_state.

```python
import streamlit as st

st.title("Persistencia de Estado con st.session_state")

# Inicializar una variable en session_state si no existe
if "contador" not in st.session_state:
    st.session_state.contador = 0

st.write(f"Contador actual: {st.session_state.contador}")

# Botón para incrementar el contador
if st.button("Incrementar"):
    st.session_state.contador += 1
    st.write(f"Nuevo valor del contador: {st.session_state.contador}")
```

## Recursos Adicionales

- **Documentación de Layout en Streamlit:**  
  [https://docs.streamlit.io/library/api-reference/layout](https://docs.streamlit.io/library/api-reference/layout)

- **Documentación de Session State:**  
  [https://docs.streamlit.io/library/api-reference/session-state](https://docs.streamlit.io/library/api-reference/session-state)

- **Artículos y Ejemplos Avanzados:**
  - [Layouts and Containers](https://docs.streamlit.io/library/advanced-features/layouts-and-containers)
  - [Session State Example Apps](https://docs.streamlit.io/knowledge-base/using-streamlit/session-state)
