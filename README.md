# Series de Tiempo - Repositorio de Consultas

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-1.3%2B-150458?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-1.21%2B-013243?logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.4%2B-11557c?logo=matplotlib&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-0.11%2B-4c72b0?logo=python&logoColor=white)
![statsmodels](https://img.shields.io/badge/statsmodels-0.13%2B-5c5c5c?logo=statsmodels&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-1.7%2B-8c9e6e?logo=scipy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0%2B-F7931E?logo=scikitlearn&logoColor=white)
![mlforecast](https://img.shields.io/badge/mlforecast-0.9%2B-2c5f2d?logo=python&logoColor=white)
![statsforecast](https://img.shields.io/badge/statsforecast-1.0%2B-ff7f0e?logo=python&logoColor=white)
![pmdarima](https://img.shields.io/badge/pmdarima-2.0%2B-2c5f2d?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)

> **Propósito:** Este repositorio es mi **cuaderno de referencia personal** para futuros proyectos de análisis y modelado de series temporales. Contiene código y explicaciones organizadas por etapas: desde el preprocesamiento hasta modelos avanzados como ARIMA, SARIMA, ARIMAX y SARIMAX.

Lo uso como una **guía rápida** para recordar pasos clave, funciones útiles y manejo de problemas comunes (datos faltantes, outliers, etc.).  

---

## Contenido por etapa

### 1. Preprocesamiento
- Carga de datos (`pandas`, `datetime`).
- Conversión a índice temporal (`df.set_index('fecha').asfreq('D/M/Y')`).
- Verificación de frecuencia y regularidad.
- Remuestreo (`resample`, `interpolate`).

### 2. Datos faltantes
- Detección: `df.isnull().sum()`, `missingno` visual.
- Imputación:
  - `interpolate(method='linear')`
  - `fillna(method='ffill')`
  - Regresión o modelos sencillos.
- Evaluación del impacto.

### 3. Outliers
- Detección estadística: z-score, IQR.
- Método visual: boxplots, series plots.
- Tratamiento: winsorización, reemplazo por mediana/valores vecinos.
- Consideración para series con estacionalidad.

### 4. Análisis Exploratorio (EDA)
- Descomposición aditiva/multiplicativa (`seasonal_decompose`).
- Autocorrelación (ACF) y autocorrelación parcial (PACF).
- Pruebas de estacionariedad: Dickey-Fuller (ADF), KPSS.
- Transformaciones: diferenciación, logaritmo, Box-Cox.

### 5. Modelos ARIMA (p,d,q)
- Enfoque Box-Jenkins:
  - Identificar `p` (PACF), `d` (diferencias), `q` (ACF).
- Auto-ARIMA (`pmdarima` o `statsmodels`).
- Evaluación: AIC/BIC, residuos (ruido blanco), predicción.

### 6. Modelos SARIMA (P,D,Q,m)
- Incorporar estacionalidad: parámetros `P,D,Q` y `m` (periodo).
- Diagnóstico igual que ARIMA + visualización de residuos estacionales.

### 7. Modelos ARIMAX y SARIMAX (con exógenas)
- Incluir variables externas (`exog` en `statsmodels`).
- Precauciones: la exógena debe conocerse para el horizonte de predicción.
- Interpretación de coeficientes.

---
