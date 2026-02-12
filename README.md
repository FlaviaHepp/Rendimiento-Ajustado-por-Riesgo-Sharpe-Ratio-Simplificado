# 📈Rendimiento Ajustado por Riesgo – Sharpe Ratio Simplificado

## 📌Descripción del Proyecto

Este proyecto implementa un análisis de rendimiento ajustado por riesgo para acciones individuales, utilizando un proxy simplificado del Ratio de Sharpe basado exclusivamente en datos de precios diarios.

El objetivo es identificar qué activos ofrecieron el mejor rendimiento relativo al riesgo asumido en el corto plazo (últimos 7 días), permitiendo priorizar oportunidades con una mejor relación retorno/volatilidad.

## 🌟Motivación

No todo rendimiento es igual:
- Dos acciones pueden subir lo mismo, pero una hacerlo con mucha más volatilidad.
- El riesgo importa tanto como el retorno, especialmente en estrategias tácticas o de trading activo.

Este análisis responde a la pregunta clave:
- ¿Qué ticker ofreció el mayor rendimiento semanal por cada unidad de riesgo tomada?

## 🧩Metodología

Para cada ticker:

*Se calcula el rendimiento diario:*

(close - open) / open


Se obtiene:

Rendimiento promedio en el período

Desviación estándar de los retornos (proxy de volatilidad)

*Se calcula el Sharpe simplificado:*

Sharpe = Rendimiento Promedio / Volatilidad
	​

⚠️ Nota:
Este no es un Sharpe Ratio académico (no incluye tasa libre de riesgo), sino una métrica operativa, útil para comparación rápida entre activos.

## 📊Interpretación de Resultados

*Proxy Sharpe alto*
👉 Buen retorno con baja volatilidad → activo eficiente.

*Proxy Sharpe bajo o negativo*
👉 Retornos pobres o excesivamente volátiles.

*Ranking descendente*
Permite detectar rápidamente los mejores candidatos para:
- Rotación de capital
- Selección de activos líderes
- Filtrado previo a estrategias más complejas

## 🔧Casos de Uso

- Screen inicial de activos para trading semanal
- Comparación objetiva entre acciones de distintos sectores
- Validación cuantitativa de “buen rendimiento”
- Inputs para modelos de asignación de capital

*Requisitos de Datos*

Tablas necesarias:
- precios_diarios
- ticker_id
- fecha
- open
- close

## ⚠️Limitaciones

- No contempla tasa libre de riesgo
- Usa datos intradía simples (open/close)
- Sensible a outliers en períodos cortos
- Aun así, es rápido, robusto y extremadamente útil como filtro inicial.

## ✒️Conclusión

Este proyecto transforma precios diarios en una métrica clara de eficiencia riesgo-retorno, ideal para decisiones rápidas y comparativas.
Es una pieza fundamental en cualquier pipeline cuantitativo orientado a selección de activos.

## 👤Autora
Flavia Hepp Proyecto de SQL aplicó un análisis de riesgo basado en eventos.
