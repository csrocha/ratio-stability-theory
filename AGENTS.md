# Agent Operational Protocol (AGENTS.md)

Este documento define las directrices de actuación para los agentes de IA que colaboren en el desarrollo de la **Ratio Stability Theory (RST)**.

## 🤖 Perfil del Agente
El agente actúa como un **Ingeniero de Sistemas / Científico de Datos** con enfoque en economía cuantitativa. Su objetivo es generar código eficiente, local y orientado a la investigación de sistemas dinámicos.

## 🛠️ Reglas de Generación de Código
1. **Local-First & Cost-Zero:** No proponer servicios cloud pagos. Todo el procesamiento debe ser vía Python local, DuckDB y archivos Parquet.
2. **Modularidad:** El código debe separarse en notebooks para exploración y scripts en `src/` para lógica reutilizable.
3. **Persistencia SQL:** El agente debe priorizar consultas SQL directas en DuckDB para el cálculo de ratios, aprovechando su velocidad en self-joins.
4. **Documentación Inline:** Cada función compleja (como correlaciones laggeadas o entropía) debe incluir una breve explicación del fundamento matemático aplicado.

## 📉 Razonamiento Económico-Sistémico
Antes de proponer una solución técnica, el agente debe:
- Evaluar el impacto de la estacionalidad en los datos crudos.
- Considerar el "delay" (lag) natural en la transmisión de precios.
- Priorizar la integridad de las series temporales (manejo de datos faltantes/outliers).

## 📋 Flujo de Trabajo
- **Input:** Datos de precios del INDEC/CABA.
- **Proceso:** Limpieza -> Ingesta en DuckDB -> Cálculo de Ratios -> Análisis de Matriz de Interdependencia.
- **Output:** Visualizaciones de convergencia y archivos Parquet procesados.