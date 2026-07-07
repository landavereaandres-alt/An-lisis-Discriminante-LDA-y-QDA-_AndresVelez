# Comparación de LDA y QDA sobre el Wine Dataset

Taller de la materia **Aprendizaje Automático** — Ciencia de Datos e Inteligencia Artificial, Universidad de Guayaquil.

Este repositorio contiene la implementación y comparación del **Análisis Discriminante Lineal (LDA)** y el **Análisis Discriminante Cuadrático (QDA)** utilizando el *Wine Dataset* de scikit-learn, sin ningún tratamiento previo.

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `LDA_vs_QDA_Wine_Andres.ipynb` | Cuaderno de Google Colab / Jupyter con las 9 secciones solicitadas: descripción del dataset, exploración, visualización, preparación de datos, implementación de LDA, implementación de QDA, comparación de modelos, fronteras de decisión y conclusiones. |
| `Informe_Tecnico_LDA_QDA.docx` | Informe técnico (investigación teórica) que responde a las preguntas sobre qué es el análisis discriminante, LDA y QDA. |
| `README.md` | Este archivo. |

## Dataset

Se utiliza el **Wine Dataset**, incluido directamente en `sklearn.datasets.load_wine()`. No es necesario descargar ningún archivo adicional: el dataset se carga automáticamente al ejecutar la primera celda de código del notebook.

- 178 observaciones
- 13 variables predictoras numéricas (resultado de análisis químicos de vinos)
- 3 clases (cultivares de uva)

## Cómo ejecutar el proyecto

### Opción 1: Google Colab (recomendado)
1. Ir a [Google Colab](https://colab.research.google.com/).
2. Subir el archivo `LDA_vs_QDA_Wine_Andres.ipynb` (`Archivo > Subir cuaderno`).
3. Ejecutar todas las celdas en orden (`Entorno de ejecución > Ejecutar todas`). No requiere instalar ninguna librería adicional, ya que Colab incluye `pandas`, `numpy`, `scikit-learn`, `matplotlib` y `seaborn` por defecto.

### Opción 2: Entorno local (Jupyter)
```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
jupyter notebook LDA_vs_QDA_Wine_Andres.ipynb
```

## Principales hallazgos

- Sobre el conjunto de prueba (25% de los datos, partición estratificada), **LDA** alcanzó un **accuracy de 95.6%** (2 errores de clasificación, concentrados en la clase 1), mientras que **QDA** alcanzó un **accuracy de 100%** (0 errores).
- Esto indica que, para este dataset, las tres clases no comparten exactamente la misma matriz de covarianza; permitir una covarianza distinta por clase (QDA) capturó mejor la dispersión real de cada cultivar.
- Las fronteras de decisión de LDA son lineales (segmentos de recta), mientras que las de QDA son curvas, tal como predice la teoría.
- LDA sigue siendo preferible cuando se dispone de pocos datos por clase o se prioriza la simplicidad e interpretabilidad del modelo, ya que estima muchos menos parámetros que QDA.

## Autor

Andres Steven Velez Landaverea — Ciencias de Datos e Inteligencia Artificial, 4.º semestre.
