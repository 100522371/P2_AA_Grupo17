# P2_AA_Grupo17

El proyecto busca identificar grupos naturales de estrellas sin utilizar las clases estelares como etiquetas objetivo. Para ello se estudia si las variables de temperatura, luminosidad, radio, magnitud absoluta, color y clase espectral permiten obtener agrupaciones coherentes con los tipos de estrellas descritos en el enunciado.

## Datos

El cuaderno carga un archivo llamado `stars_data.csv` con 240 observaciones y las siguientes columnas:

| Columna | Descripción |
| --- | --- |
| `Temperature` | Temperatura de la estrella |
| `L` | Luminosidad relativa |
| `R` | Radio relativo |
| `A_M` | Magnitud absoluta |
| `Color` | Color observado |
| `Spectral_Class` | Clase espectral |


## Metodología

El análisis sigue estas etapas:

1. **Carga y exploración:** lectura del conjunto de datos y revisión de sus variables categóricas y numéricas.
2. **Preprocesamiento:** normalización de los nombres de los colores y codificación ordinal de `Color` y `Spectral_Class`, conservando el orden relacionado con la temperatura.
3. **Comparación de algoritmos:** evaluación de distintos valores de hiperparámetros para:
   - K-Means.
   - DBSCAN.
   - Clustering jerárquico aglomerativo.
4. **Evaluación:** comparación de las particiones mediante el coeficiente de silueta y la métrica DBCV, especialmente útil para agrupaciones basadas en densidad.
5. **Visualización:** representación de los grupos y reducción a dos dimensiones mediante PCA.
6. **Modelo final:** aplicación de K-Means con 6 clústeres y `n_init=25`. Finalmente se calculan las medias de las variables de cada grupo para interpretar sus características astronómicas.

Los identificadores numéricos de los clústeres son etiquetas arbitrarias: no representan por sí mismos un tipo estelar y deben interpretarse a partir de los valores medios de cada grupo.

## Resultados principales

Seleccionamos una partición final de 6 grupos con K-Means y genera:

- métricas de calidad para comparar configuraciones;
- gráficos de los clústeres en el espacio reducido por PCA;
- una tabla con las medias de las variables de cada clúster;
- una interpretación de los grupos en términos de enanas, gigantes, supergigantes e hipergigantes, según sus propiedades.

## Autores

- Montserrat Martis Contreras — `100522371`
- Laith Basem Elbeshti — `100477240`
