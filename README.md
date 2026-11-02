# Forecasting Toolkit in R

*A reproducible R toolkit for univariate time-series forecasting, model comparison, and residual diagnostics.*

## Descripción

Este proyecto implementa una caja de herramientas para analizar series temporales y comparar métodos clásicos de pronóstico. Incluye funciones reutilizables, ejemplos reproducibles y un informe técnico con ocho métodos principales y un contraejemplo estacional.

## ¿Qué incluye?

- Lectura y preparación de series univariadas.
- Gráficos de series, ACF y correlogramas.
- Ocho métodos de pronóstico: media simple, media móvil, suavizamiento exponencial simple, doble media móvil, tendencias lineal/cuadrática/exponencial y método de Holt.
- Optimización de parámetros y evaluación fuera de muestra.
- Diagnósticos de residuos: Ljung–Box, Jarque–Bera y Durbin–Watson.
- Métricas de error y comparación contra el pronóstico ingenuo.
- Informe reproducible en Quarto (`informe/informe.qmd`).

## Herramientas

`R` · `ggplot2` · `dplyr` · `tidyr` · `purrr` · `tibble` · `patchwork` · `Quarto`

## Cómo ejecutarlo

```r
install.packages(c(
  "dplyr", "tidyr", "purrr", "tibble",
  "ggplot2", "patchwork"
))

source("ejemplos/ejemplos.R")
```

Para renderizar el informe:

```bash
quarto render informe/informe.qmd
```

## Hallazgos y evaluación

El repositorio compara cada método con un pronóstico ingenuo usando MASE y documenta convenciones de inicialización, grados de libertad y cálculo de diagnósticos. El contraejemplo con `nottem` muestra que un método que funciona bien en una serie puede tener un desempeño deficiente en una serie estacional.

## Autoría e historial

Proyecto individual. Se conserva el historial original de siete commits del desarrollo.

## Estructura

- `R/`: funciones de lectura, gráficos, métodos y evaluación.
- `ejemplos/`: ejecución integral de los casos.
- `figs/`: visualizaciones generadas.
- `informe/`: fuente Quarto y PDF del informe.
