## 3. Widgets Interactivos

Los **widgets** permiten que el usuario interactúe con la aplicación y cambie dinámicamente lo que se muestra en pantalla. Streamlit ofrece varios widgets comunes:

- **`st.button("Texto del Botón")`**
- **`st.radio("Título", opciones)`**
- **`st.selectbox("Etiqueta", opciones)`**
- **`st.text_input("Etiqueta")`**
- **`st.slider("Etiqueta", valor_inicial, valor_final)`**

Estos widgets capturan la entrada del usuario y, **cada vez que el usuario interactúa**, la aplicación se vuelve a ejecutar de arriba a abajo, actualizando el contenido en tiempo real.

### Ejemplo: Uso de Widgets Interactivos

```python
import streamlit as st

st.title("Demo de Widgets Interactivos")

# 1. Botón
if st.button("Presióname"):
    st.write("¡Botón Presionado!")

# 2. Radio
opcion_radio = st.radio("Elige una opción:", ["Opción A", "Opción B", "Opción C"])
st.write(f"Has seleccionado: {opcion_radio}")

# 3. Selectbox
opcion_select = st.selectbox("Selecciona un valor:", ["Rojo", "Verde", "Azul"])
st.write(f"Seleccionaste el color: {opcion_select}")

# 4. Text Input
nombre = st.text_input("Ingresa tu nombre", "John Doe")
st.write(f"Hola, {nombre}!")

# 5. Slider
valor_slider = st.slider("Selecciona un número", 0, 100, 50)
st.write(f"Valor del slider: {valor_slider}")
```

## Recursos Adicionales

**Documentación Oficial de widgets:**
[Streamlit widgets](https://docs.streamlit.io/develop/api-reference/widgets)
