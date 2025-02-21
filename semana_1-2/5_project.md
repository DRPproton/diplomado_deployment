## 5. Ejercicio de Mini-Panel (Dashboard)

En este ejercicio, combinarás lo aprendido para crear un **mini-dashboard** interactivo. Utilizarás un conjunto de datos de ejemplo, mostrarás estadísticas básicas y añadirás filtros para que el usuario pueda explorar la información.

### Pasos del Ejercicio

1. **Cargar un Conjunto de Datos de Ejemplo**  
   Puedes usar cualquier dataset de tu preferencia. Como ejemplo, el clásico [Iris dataset](https://archive.ics.uci.edu/ml/datasets/Iris):

   ```python
    import streamlit as st
    import pandas as pd

    st.title("Mini-Dashboard con Iris Dataset")

    @st.cache_data
    def load_data():
        url = "https://raw.githubusercontent.com/mwaskom/seaborn-data/master/iris.csv"
        return pd.read_csv(url)

    # 1. Cargar el Dataset
    df = load_data()

    # 2. Vista Previa
    st.write("## Vista Previa del Dataset")
    st.dataframe(df.head())

    # 3. Estadísticas Básicas
    st.write("## Estadísticas Básicas")
    st.write(df.describe())

    # 4. Distribución de Especies
    st.write("## Distribución de Especies")
    st.bar_chart(df['species'].value_counts())

    # 5. Filtro Interactivo
    especie_filtrada = st.selectbox("Selecciona una especie:", df['species'].unique())
    df_filtrado = df[df['species'] == especie_filtrada]

    st.write(f"### Filtrado por especie: {especie_filtrada}")
    st.dataframe(df_filtrado)

    st.write("## Estadísticas de la especie filtrada")
    st.write(df_filtrado.describe())
   ```

## Recursos Adicionales

- **Documentación de `st.cache_data`:**  
  [https://docs.streamlit.io/library/api-reference/performance/st.cache_data](https://docs.streamlit.io/library/api-reference/performance/st.cache_data)

- **Otros ejemplos de componentes interactivos:**  
  [https://docs.streamlit.io/library/api-reference/widgets](https://docs.streamlit.io/library/api-reference/widgets)

- **Galería de Aplicaciones en Streamlit (para más inspiración):**  
  [https://streamlit.io/gallery](https://streamlit.io/gallery)
