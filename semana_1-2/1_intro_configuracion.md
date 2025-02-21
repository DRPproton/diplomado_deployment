# Módulo: Introducción a Streamlit

En este módulo, conocerás los fundamentos de **Streamlit**, aprenderás cómo instalarlo y, finalmente, crearás tu primera aplicación “Hola Mundo”. Streamlit es una herramienta poderosa y sencilla que te permite crear aplicaciones web interactivas para visualizar datos, crear dashboards y mostrar resultados de tus modelos de Machine Learning sin necesidad de ser experto en desarrollo web.

---

## 1. ¿Qué es Streamlit?

**Streamlit** es un framework de Python que facilita la construcción de aplicaciones web para ciencia de datos y machine learning. A diferencia de frameworks más tradicionales como Flask o Django, Streamlit está diseñado específicamente para la **visualización de datos y la interacción con modelos** de ML. Algunas de sus ventajas principales:

- **Fácil de Usar:** Puedes convertir un script de Python en una aplicación web con tan solo unas pocas líneas de código.
- **Actualización Inmediata:** Cada vez que el usuario interactúa con la aplicación (por ejemplo, con un slider o un botón), la app se recarga y refleja los cambios en tiempo real.
- **Integraciones con Librerías de Datos y Gráficos:** Funciona de manera óptima con `pandas`, `numpy`, `matplotlib`, `plotly`, etc.
- **Prototipado Rápido:** Ideal para crear prototipos de dashboards y paneles de control sin tener que aprender HTML, CSS o JavaScript.

### ¿Por Qué Usar Streamlit?

1. **Menos Código Repetitivo:** En lugar de escribir el front-end desde cero, usas funciones como `st.write()`, `st.title()`, `st.slider()`, etc. para manejar la interfaz.
2. **Orientado a la Colaboración:** Los equipos de ciencia de datos pueden compartir fácilmente prototipos de aplicaciones con otros miembros (desarrolladores, analistas, gerentes, etc.).
3. **Aprendizaje Fácil:** La curva de aprendizaje es muy suave si ya trabajas con Python.

---

## 2. Instalación de Streamlit

Para comenzar a usar Streamlit, primero debes **instalar Python** (versión 3.7 o superior recomendada). Asegúrate de tener un entorno virtual configurado para mantener tus dependencias organizadas (por ejemplo, usando `venv` o `conda`).

1. **Crea y/o activa tu entorno virtual** (opcional pero muy recomendado):

   ```bash
   # macOS/Linux:
   python3 -m venv venv
   source venv/bin/activate

   # Windows:
   python -m venv venv
   venv\Scripts\activate
   ```

2. **Instala Streamlit mediante pip**

   ```bash
   pip install streamlit
   ```

3. **Verifica la instalación**
   ```bash
   streamlit --version
   ```

## 3. Ejecución de tu Primera App “Hola Mundo”

Ahora que tienes Streamlit instalado, crearás tu primer script de Python y lo ejecutarás como aplicación web.

1. **Crea un archivo** llamado `app.py` (puedes darle cualquier nombre, pero `app.py` es un estándar frecuente):

   ```python
   import streamlit as st

   # Título de la aplicación
   st.title("Mi Primera App en Streamlit")

   # Mensaje de saludo
   st.write("¡Hola Mundo! Bienvenido a Streamlit.")
   ```

2. **Ejecuta la aplicación**

Con el archivo `app.py` creado, abre tu terminal (asegúrate de estar dentro de la carpeta que contiene el archivo) y ejecuta:

```bash
streamlit run app.py
```

- You can now view your Streamlit app in your browser.

> Network URL: http://192.168.0.10:8501 <br>
> External URL: http://203.0.113.5:8501
