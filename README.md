 Energía Hidroeléctrica vs. Clima — Paraguay

 Summary

This project analyzes the relationship between hydroelectric power generation in Paraguay (Itaipú) and hydro-climatic variability, using 24 years of monthly data (2000–2023). After testing local rainfall and the El Niño/La Niña index (ONI) both weak predictors the strongest signal came from ENA (Energia Natural Afluente), a basin-wide inflow-energy indicator from Brazil's grid operator (ONS): a moderate correlation (r ≈ 0.36) that holds even after removing seasonality, peaking at a 1-month lag. The findings highlight that Itaipú's output depends on a large, regional watershed rather than localized or global climate signals and that generation itself is shaped by operational decisions as much as by water availability.


 Objetivo

Analizar la relación entre la generación de energía hidroeléctrica en Paraguay (Itaipú, con datos de Yacyretá como referencia complementaria) y las variables climáticas e hidrológicas que la afectan, para identificar patrones, riesgos de sequía y tendencias a lo largo del tiempo.

Pregunta central

¿Cómo varía la generación hidroeléctrica en función de la disponibilidad hídrica (lluvia, caudal afluente) y de índices climáticos globales, y qué tan vulnerable es Paraguay a períodos de sequía en términos de producción energética?


Fuentes de datos

| Fuente | Variable | Período | Granularidad |

| ONS Dados Abertos (Brasil) | Generación Itaipú | 2000–2026 | Horaria → agregada a mensual |
| ONS Dados Abertos (Brasil) | ENA (Energía Natural Afluente) | 2000–2023 | Diaria → agregada a mensual |
| CAMMESA (Argentina) | Generación Yacyretá | 2005–2025 | Anual |
| DINAC / SIA Paraguay | Precipitación (Encarnación) | 1990–2023 | Mensual |
| NOAA CPC | Índice ONI (El Niño/La Niña) | 1990–2026 | Mensual |

## Metodología

1. **Recolección**: identificación y descarga de las 5 fuentes de datos públicas listadas arriba.
2. **Limpieza**: corrección de corrupción numérica en el dataset de Itaipú (causada por apertura en Excel con configuración regional), validada mediante ecuaciones físicas (Total = 60Hz + 50Hz; Total = BR + PY).
3. **Unificación**: consolidación de las series en una única tabla mensual, con ventana de análisis común 2000–2023.
4. **Análisis exploratorio**: series de tiempo, estacionalidad mensual, comparación visual generación vs. lluvia acumulada.
5. **Correlación**: prueba de tres variables explicativas (lluvia local, ONI, ENA) con distintos retrasos temporales (lags), y con anomalías (removiendo estacionalidad) para aislar la señal real.

## Hallazgos principales

- La correlación entre generación de Itaipú y disponibilidad hídrica real (ENA) es moderada (r = 0.36), incluso después de remover el efecto estacional el predictor más fuerte de los tres evaluados.
- La relación es ligeramente más fuerte con 1 mes de retraso, sugiriendo un breve tiempo de respuesta entre la hidrología de la cuenca y el impacto en generación.
- La **lluvia puntual de una sola estación** (Encarnación, r ≈ 0.25) y el **índice ONI** (El Niño/La Niña, r ≈ 0.00–0.03) son predictores mucho más débiles — Itaipú depende de la hidrología de una cuenca extensa y regional (sur de Brasil), no de eventos climáticos localizados o globales aislados.
- La **sequía de 2020–2022** fue el evento más severo del período analizado, con caída de generación de ~13.000 MW a menos de 7.000 MW.
- La generación hidroeléctrica combina señal física (agua disponible) y señal operativa (contratos, demanda, mantenimiento) — lo que limita cuánto puede explicar el clima por sí solo.

## Herramientas

Python (pandas, matplotlib), Jupyter Notebook (vía VS Code), Git/GitHub.

## Estructura del repositorio