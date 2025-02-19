# Fundamentos de Streamlit: Primera Sección (10 Horas)

¡Bienvenido a la **sección de Fundamentos de Streamlit** del curso de **Despliegue de Modelos de ML**!  
Esta parte abarca **dos sesiones (5 horas cada una)** y cubre cómo crear y desplegar aplicaciones de datos interactivas utilizando el framework [Streamlit](https://streamlit.io/).

---

## Tabla de Contenidos

1. [Resumen General](#resumen-general)
2. [Objetivos del Curso](#objetivos-del-curso)
3. [Desglose de las Sesiones](#desglose-de-las-sesiones)
   - [Sesión 1 (5 Horas)](#sesión-1-5-horas)
   - [Sesión 2 (5 Horas)](#sesión-2-5-horas)
4. [Proyecto: Aplicación de Predicción de Precios de Viviendas](#proyecto-aplicación-de-predicción-de-precios-de-viviendas)
5. [Prerrequisitos y Configuración de Entorno](#prerrequisitos-y-configuración-de-entorno)
   - [Creación y Configuración del Entorno Virtual](#creación-y-configuración-del-entorno-virtual)
   - [Instalación de Librerías](#instalación-de-librerías)
6. [Ejecución de la Aplicación](#ejecución-de-la-aplicación)
7. [Recursos](#recursos)

---

## Resumen General

En esta **primera sección** de nuestro curso de Despliegue de Modelos de ML, aprenderás:

- Cómo configurar Streamlit para desarrollar rápidamente aplicaciones de datos.
- Las funciones principales de Streamlit: mostrar texto, imágenes, tablas y gráficos.
- Cómo incorporar la interacción del usuario mediante widgets interactivos.
- Gestión de estado, almacenamiento en caché de datos y modelos para mejorar el rendimiento.
- Cómo estructurar la apariencia de tu aplicación y desplegarla en la web.

Al finalizar, habrás construido y desplegado una aplicación de **Aprendizaje Automatico** para practicar la integración de un modelo de ML entrenado con una interfaz de Streamlit.

---

## Objetivos del Curso

- **Fundamentos de Streamlit:**  
  Comprender el concepto “ejecutar de arriba a abajo” y los elementos básicos de la interfaz de Streamlit.
- **Interactividad:**  
  Adquirir experiencia práctica con widgets de entrada (botones, sliders, select boxes) para crear apps centradas en el usuario.
- **Visualización y Muestra de Datos:**  
  Aprender a mostrar tablas y gráficos utilizando métodos integrados de Streamlit y librerías populares de Python.
- **Optimización del Rendimiento:**  
  Implementar el uso de caché con `st.cache_data` y `st.cache_resource` para agilizar la recarga de la aplicación.
- **Despliegue:**  
  Explorar opciones para compartir aplicaciones de Streamlit, incluyendo Streamlit Community Cloud, Docker y otras.

---

## Desglose de las Sesiones

### Sesión 1 (5 Horas)

**Temas Cubiertos:**

1. **Introducción y Configuración**

   - ¿Qué es Streamlit?
   - Instalación de Streamlit
   - Ejecución de tu primera app “Hola Mundo”

2. **Funciones Principales de Streamlit**

   - Mostrar texto (`st.title`, `st.header`, `st.write`, `st.markdown`)
   - Disposición básica y mecánica de recarga del script

3. **Widgets Interactivos**

   - Widgets comunes de entrada: `st.button`, `st.radio`, `st.selectbox`, `st.text_input`, `st.slider`
   - Capturar la entrada del usuario y responder en tiempo real

4. **Visualización de Datos**

   - Mostrar DataFrames (`st.dataframe`, `st.table`)
   - Gráficos rápidos (`st.line_chart`, `st.bar_chart`, `st.map`)
   - Integración con Matplotlib/Seaborn/Plotly

5. **Ejercicio de Mini-Panel (Dashboard)**
   - Cargar un conjunto de datos de ejemplo
   - Mostrar estadísticas y crear visualizaciones básicas
   - Agregar filtros interactivos

---

### Sesión 2 (5 Horas)

**Temas Cubiertos:**

1. **Diseño Avanzado y Gestión de Estado**

   - Uso de `st.sidebar`, `st.columns`, `st.expander`
   - Persistencia de estado con `st.session_state`

2. **Caché y Rendimiento**

   - `st.cache_data` vs `st.cache_resource`
   - Mejores prácticas para guardar en caché cargas de datos y modelos de ML

3. **Personalización y Opciones de Despliegue**

   - Personalizar la apariencia de la app mediante `.streamlit/config.toml`
   - Descripción general de métodos de despliegue (Streamlit Community Cloud, Hugging Face Spaces, Docker, etc.)

4. **Implementación del Proyecto**

   - Construir la **Aplicación**
   - Integrar un modelo previamente entrenado (`model.pkl`)
   - Recopilar entradas de usuario y mostrar las predicciones

5. **Cierre y Reflexión**
   - Resumen de las características de Streamlit
   - Vista previa de las siguientes secciones del curso de Despliegue de ML

---

## Proyecto: Elegido por el estudiante

Durante la Sesión 2, aplicarás todo lo aprendido para construir una aplicación simple pero potente de **Predicción de (Proyect)**. Los pasos clave incluyen:

1. **Cargar un Modelo Entrenado**

   - Utiliza `pickle` u otro método de serialización para cargar un modelo de regresión.

2. **Construir la Interfaz de Usuario**

   - Añade widgets (por ejemplo, sliders, select boxes) para capturar las entradas del usuario (habitaciones, metros cuadrados, ubicación, etc.).

3. **Generar Predicciones**

   - Calcula el precio estimado y muéstralo en la pantalla.
   - Opcionalmente, añade métricas o visualizaciones que comparen múltiples escenarios de predicción.

4. **Desplegar la Aplicación**
   - Despliega local y con Docker.
   - Comparte el enlace para que otros puedan probar tu modelo.

---

## Prerrequisitos y Configuración

1. **Python 3.9+**  
   Asegúrate de tener Python instalado. (Recomendamos usar un entorno virtual.)

2. **Conocimientos Básicos de Python**

   - Familiaridad con `pandas`, `numpy` y manipulación básica de datos.
   - Capacidad para leer/escribir archivos CSV, manejar DataFrames, etc.

3. **Librerías Recomendadas**
   - `pandas`
   - `numpy`
   - `matplotlib` y `seaborn` (para visualización de datos)
   - `scikit-learn` (para el modelo de ML)
   - `streamlit` (para crear aplicaciones web interactivas)

---

### Creación y Configuración del Entorno Virtual

Sigue estos pasos para crear y configurar tu entorno virtual en Python, con el fin de aislar las dependencias del proyecto.

#### 1. Crear el entorno virtual

**En macOS/Linux:**

```bash
python3 -m venv venv
```

**En Windows:**

```bash
python -m venv venv
```

#### 2. Activar el entorno virtual

**En macOS/Linux:**

```bash
source venv/bin/activate
```

**En Windows:**

```bash
venv\Scripts\activate
```

#### Instalación de Librerías

**Con el entorno virtual activado, instala las librerías requeridas:**

```bash
pip install streamlit pandas numpy scikit-learn matplotlib seaborn
```

**Si deseas exportar estas dependencias a un archivo requirements.txt para facilitar la instalación en otros equipos, ejecuta:**

```bash
pip freeze > requirements.txt
```

---

### Ejecución de la Aplicación

Con todas las librerías instaladas y tu entorno virtual activo, para iniciar una aplicación de Streamlit (por ejemplo, un archivo app.py), ejecuta:

```bash
streamlit run app.py
```

En la consola aparecerá una URL local similar a `http://localhost:8501/`. Haz clic en el enlace o cópialo en tu navegador para ver la aplicación en funcionamiento.

### Recursos

- **Documentación Oficial de Streamlit:**  
  [https://docs.streamlit.io/](https://docs.streamlit.io/)

- **GitHub de Streamlit:**  
  [https://github.com/streamlit/streamlit](https://github.com/streamlit/streamlit)

- **Notas sobre Despliegue de Modelos de ML:**  
  Encontrarás recursos adicionales sobre Dockerización y CI/CD en secciones futuras de este curso.

- **Ejemplos de la Comunidad:**  
  [Galería de Aplicaciones en Streamlit](https://streamlit.io/gallery)
