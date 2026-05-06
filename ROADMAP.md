# Proyecto RST: Hoja de Ruta (ROADMAP.md)

Este roadmap detalla las fases de desarrollo para validar la teoría de convergencia de ratios y la matriz de interdependencias.

## 📍 Fase 1: Cimientos e Ingesta (Q2 2026)
- [ ] **Configuración del entorno:** Repo, venv y esquema inicial de DuckDB.
- [ ] **Scraper INDEC:** Automatización de descarga de "Precios promedio de elementos de la canasta del IPC".
- [ ] **Scraper CABA:** Ingesta de la serie histórica detallada de CABA.
- [ ] **Normalización:** Creación de un diccionario maestro de productos para unificar categorías entre fuentes.

## 📍 Fase 2: Motor de Ratios y Estacionariedad
- [ ] **Pipeline de Ratios:** Desarrollo de la lógica SQL para generar todas las combinaciones de ratios posibles entre $N$ productos.
- [ ] **Análisis de Atractores:** Identificación de rangos de convergencia históricos para ratios clave (ej. Proteína/Carbohidrato).
- [ ] **Detección de Desvíos:** Script para comparar ratios en intervalos $[t_0, t_1]$ y medir el desplazamiento vectorial.

## 📍 Fase 3: La Matriz de "Bolas de Pool"
- [ ] **Correlaciones Laggeadas:** Mapear la latencia de impacto entre precios (ej. cuánto tarda el combustible en mover el pan).
- [ ] **Visualización de Grafos:** Generar un grafo dirigido donde los nodos son productos y las aristas son la fuerza de impacto.
- [ ] **Identificación de Impulsores:** Determinar los productos que inician las ondas inflacionarias en el sistema.

## 📍 Fase 4: Optimización y Estabilidad
- [ ] **Simulador de Convergencia:** Modelo que busca el ajuste porcentual mínimo para estabilizar el sistema.
- [ ] **Validación Histórica:** Testear el modelo con datos de crisis pasadas para ver si predice el punto de ruptura de los ratios.

---
*Nota: Este roadmap es iterativo y se ajustará según los hallazgos en la matriz de interdependencias.*