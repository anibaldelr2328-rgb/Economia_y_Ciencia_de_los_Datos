# Proyecto: API de Valoración Financiera Corporativa

## I. Descripción del Proyecto

El proyecto tiene como objetivo principal el desarrollo de una **API (Interfaz de Programación de Aplicaciones)** para la **valoración de empresas**. Su enfoque es proveer una herramienta que garantice la **consistencia y trazabilidad** de los resultados. La API está diseñada para que **analistas, inversionistas y fundadores** puedan realizar un análisis riguroso de compañías que cotizan en bolsa, utilizando una metodología de valoración reconocida en el ámbito de las **finanzas corporativas**.

La API se basará en los siguientes **métodos de valoración financiera** para ofrecer una herramienta integral de análisis:

* **Flujo de Caja Libre Descontado (DCF/FCFF):** Un modelo intrínseco que estima el valor de una empresa a partir de la proyección y descuento de sus flujos de caja futuros a valor presente.
* **Múltiplos Comparables:** Un análisis relativo que compara una empresa con un grupo de pares del mismo sector o país para determinar su valor de mercado.
* **Cálculo del WACC (Costo Promedio Ponderado de Capital):** Un componente esencial del modelo DCF, que establece la tasa de descuento adecuada para los flujos de caja futuros.
* **Análisis de Sensibilidad:** Una funcionalidad que permite evaluar cómo la variación de variables clave afecta la valoración final, proporcionando una visión del riesgo y la robustez del resultado.

---

## II. Datos Económicos a Analizar

Para garantizar una valoración completa y precisa, la API procesará y analizará los siguientes tipos de información:

* **Estados Financieros Históricos:** Datos de los últimos 5 a 10 años, incluyendo ingresos, costos, gastos operativos, EBITDA, impuestos, CapEx, variación del capital de trabajo, deuda y número de acciones.
* **Estructura de Capital y Riesgo:** Información como deuda neta, costo de la deuda, tasa impositiva, **beta**, prima de riesgo de mercado (ERP) y tasa libre de riesgo (Rf).
* **Datos de Mercado:** Precios históricos de la acción, capitalización bursátil y **Enterprise Value (EV)**.
* **Factores Macroeconómicos:** Variables externas como la Tasa de Política Monetaria (TPM), inflación, tipo de cambio y PIB.
* **Supuestos de Proyección:** Expectativas futuras sobre crecimiento de ingresos, márgenes de rentabilidad, inversiones necesarias, tasas impositivas y la tasa de crecimiento terminal.
* **Datos de Comparables:** Múltiplos de mercado como EV/EBITDA, P/E y EV/Sales de empresas similares.

---

## III. Metodologías a Utilizar

* **DCF (Discounted Cash Flow / Flujo de Caja Descontado):** Es el método principal.
* **Múltiplos Comparables:** Un método de validación clave.
* **WACC (Weighted Average Cost of Capital):** La herramienta calculará el costo promedio ponderado de financiar la empresa.
* **Análisis de Sensibilidad:** Esta funcionalidad permitirá a los usuarios evaluar cómo los cambios en variables críticas influyen en la valoración.

---

## IV. Endpoints de la API

Los endpoints se han estructurado para permitir a los usuarios obtener información relevante y ejecutar los análisis de valoración de manera secuencial y lógica.

* `GET /companies/search`: Permite encontrar empresas por nombre o ticker.
* `GET /companies/{id}`: Devuelve información general sobre una empresa.
* `GET /companies/{id}/financials`: Entrega los datos financieros históricos.
* `GET /market/{ticker}/timeseries`: Proporciona precios históricos y otros datos de mercado.
* `GET /macro/series`: Retorna variables como inflación y tasas de interés.
* `GET /news/{ticker}`: Permite acceder a noticias recientes.
* `GET /risk/wacc`: Ejecuta el cálculo del costo promedio ponderado de capital.
* `POST /valuation/dcf`: Realiza la valoración completa de una empresa.
* `POST /valuation/sensitivity`: Muestra el impacto de las variaciones de las variables de entrada en el resultado final.

---

## V. Fuentes de Datos y APIs Externas

Para asegurar la robustez del proyecto, la API se conectará a diversas fuentes de datos financieras y macroeconómicas. 

* **Financial Modeling Prep (FMP):** Se utilizará para obtener estados financieros, múltiplos de valoración y datos históricos de betas.
* **Alpha Vantage & yfinance:** Proporcionarán precios históricos y otros indicadores del mercado.
* **Banco Central de Chile (BCCh) y FRED:** Fuentes de datos macroeconómicos clave.
* **World Bank API y CMF Chile:** Servirán para complementar la información con datos de desarrollo económico y estados financieros oficiales de empresas chilenas.






