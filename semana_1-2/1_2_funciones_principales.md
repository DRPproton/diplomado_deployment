# Funciones Principales de Streamlit

En esta sección aprenderás cómo **mostrar texto** y cómo se organiza la **disposición básica** de una aplicación en Streamlit. También discutiremos la **mecánica de recarga** del script, es decir, cómo cada vez que un usuario interactúa con la aplicación, Streamlit vuelve a ejecutar tu archivo de Python de arriba a abajo.

---

## Mostrar Texto: `st.title`, `st.header`, `st.write`, `st.markdown`

Streamlit ofrece diversas funciones para mostrar texto y encabezados en tu aplicación:

1. **`st.title("Título de la Aplicación")`:**

   - Muestra un texto grande y destacado, usualmente utilizado para el título principal de la app.

2. **`st.header("Encabezado de Sección")`:**

   - Muestra un texto en tamaño mediano, ideal para secciones o subtítulos.

3. **`st.write("Texto")`:**

   - Funciona como un “comodín” para mostrar texto plano, DataFrames, gráficos y más.
   - Es muy versátil y se adapta a múltiples formatos de datos.

4. **`st.markdown("Texto con **Markdown**")`:**
   - Permite incluir sintaxis de Markdown para dar formato al texto (negritas, itálicas, enlaces, etc.).

### Ejemplo de Código

```python
import streamlit as st

# Título principal de la app
st.title("Mi Aplicación de Ejemplo")

# Encabezado de sección
st.header("Sección Introductoria")

# Texto simple
st.write("¡Hola! Esta es mi primera sección de texto en Streamlit.")

# Texto con Markdown para resaltar o formatear
st.markdown("Este texto puede incluir **negritas**, *itálicas* o incluso [enlaces](https://www.streamlit.io).")
```

## Disposición Básica de la Aplicación

Por defecto, Streamlit muestra los elementos (títulos, textos, gráficos, etc.) en orden vertical de arriba a abajo, tal como aparecen en tu script de Python. Cada vez que le pides a Streamlit que muestre algo (por ejemplo, con `st.write()`), ese elemento se imprime en la interfaz.

## Mecánica de Recarga del Script

Una de las particularidades más importantes de Streamlit es que **cada vez que un usuario interactúa con la aplicación**, el script completo (por ejemplo, `app.py`) se **vuelve a ejecutar de arriba a abajo**. Esto implica:

1. **Reactividad:** Cualquier cambio de un widget (ej. mover un slider, pulsar un botón) ocasiona que los cálculos se reinicien, actualizando la vista.
2. **Uso de Widgets y Variables:** Si no usas ninguna técnica de almacenamiento (como `st.session_state` o `st.cache_data`/`st.cache_resource`), los valores se reiniciarán en cada recarga.
3. **Simplicidad:** No necesitas gestionar manualmente las rutas o el ciclo de vida de la app; Streamlit se encarga de todo, pero debes recordar que tu código se ejecuta por completo cada vez que hay una interacción.

### Ejemplo Ilustrativo

```python
import streamlit as st

st.title("Ejemplo de Interacción")

boton_presionado = st.button("¡Haz Clic Aquí!")

if boton_presionado:
    st.write("¡Has hecho clic en el botón!")
```

## Recursos Adicionales

- **Documentación Oficial de Streamlit:**
  [https://docs.streamlit.io/](https://docs.streamlit.io/)

- **Galería de Aplicaciones de Streamlit:**
  [https://streamlit.io/gallery](https://streamlit.io/gallery)
  Inspírate con ejemplos de la comunidad.

- **Uso de Markdown en Streamlit:**
  [Guía Básica de Markdown](https://www.markdownguide.org/basic-syntax/)

```

```
