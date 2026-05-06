# Ratio Stability Theory (RST)

Este repositorio contiene las herramientas de ingesta, procesamiento y modelado para evaluar la **Teoría de Estabilidad por Ratios**. El proyecto busca analizar la inflación no como un fenómeno nominal, sino como una distorsión en la convergencia de los precios relativos.

## 🧠 Concepto Técnico
La **RST** postula que la estabilidad económica es una propiedad emergente de un sistema de ratios de precios. En equilibrio, los ratios entre bienes de la canasta básica (ej. Carne/Trigo) convergen en conjuntos finitos de valores o **atractores**. 

El modelo trata los precios como un **sistema de partículas ("bolas de pool")**, donde:
*   **Impulso:** El cambio inicial en un precio clave.
*   **Transferencia:** El impacto distribuido hacia otros precios mediante una matriz de interdependencias.
*   **Desplazamiento:** La inflación se define como el movimiento neto del tablero de ratios en un intervalo $[t_0, t_1]$.

## 🛠️ Arquitectura y Stack
El proyecto prioriza un enfoque **Local-First** para garantizar soberanía de datos y costo cero de infraestructura:

*   **Engine:** [DuckDB](https://duckdb.org/) para procesamiento analítico in-process.
*   **Storage:** Archivos **Parquet** para persistencia de series temporales.
*   **Ingesta:** Notebooks de Python para scraping y normalización de microdatos (INDEC y CABA).

## 📂 Estructura del Proyecto
```text
├── data/
│   ├── raw/            # Datos crudos (CSV/XLSX)
│   ├── processed/      # Series temporales normalizadas (Parquet)
│   └── database/       # Base de datos DuckDB
├── notebooks/
│   ├── 01_ingesta.ipynb      # Captura de datos de fuentes abiertas
│   └── 02_analisis_matriz.ipynb # Deducción de la matriz de interdependencia
└── requirements.txt
