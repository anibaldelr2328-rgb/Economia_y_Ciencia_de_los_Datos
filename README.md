# Economia y Ciencia de los Datos
Economía y cienca de datos
Propuesta Detallada del Proyecto
I. Descripción del Proyecto
El proyecto tiene como objetivo principal el desarrollo de una API (Interfaz de Programación de Aplicaciones) para la valoración de empresas. Su enfoque es proveer una herramienta que garantice la consistencia y trazabilidad de los resultados. La API está diseñada para que analistas, inversionistas y fundadores puedan realizar análisis rigurosos de compañías que cotizan en bolsa, utilizando una metodología de valoración reconocida en el ámbito de las finanzas corporativas.

La API se basará en los siguientes métodos de valoración financiera para ofrecer una herramienta integral de análisis:

Flujo de Caja Libre Descontado (DCF/FCFF): Un modelo intrínseco que estima el valor de una empresa a partir de la proyección y descuento de sus flujos de caja futuros a valor presente.

Múltiplos Comparables: Un análisis relativo que compara una empresa con un grupo de pares del mismo sector o país para determinar su valor de mercado.

Cálculo del WACC (Costo Promedio Ponderado de Capital): Un componente esencial del modelo DCF, que establece la tasa de descuento adecuada para los flujos de caja futuros.

Análisis de Sensibilidad: Una funcionalidad que permite evaluar cómo la variación de variables clave afecta la valoración final, proporcionando una visión del riesgo y la robustez del resultado.

II. Datos Económicos a Analizar
Para garantizar una valoración completa y precisa, la API procesará y analizará los siguientes tipos de información:

Estados Financieros Históricos: Datos de los últimos 5 a 10 años, incluyendo ingresos, costos, gastos operativos, EBITDA, impuestos, CapEx, variación del capital de trabajo, deuda y número de acciones.

Estructura de Capital y Riesgo: Información como deuda neta, costo de la deuda, tasa impositiva, beta, prima de riesgo de mercado (ERP), y tasa libre de riesgo (Rf), cruciales para el cálculo del WACC.

Datos de Mercado: Precios históricos de la acción, capitalización bursátil y Enterprise Value (EV), que sirven para comparar el valor teórico obtenido con el precio real del mercado.

Factores Macroeconómicos: Variables externas como la Tasa de Política Monetaria (TPM), inflación, tipo de cambio y PIB, que impactan tanto el costo de capital como las proyecciones de crecimiento.

Supuestos de Proyección: Expectativas futuras sobre crecimiento de ingresos, márgenes de rentabilidad, inversiones necesarias, tasas impositivas y la tasa de crecimiento terminal.

Datos de Comparables: Múltiplos de mercado como EV/EBITDA, P/E y EV/Sales de empresas similares, que permiten validar la coherencia de la valoración con el mercado.

III. Metodologías a Utilizar
DCF (Discounted Cash Flow / Flujo de Caja Descontado): Este será el método principal. Calcula el valor de la empresa a partir de los flujos de caja libres proyectados, descontados al presente utilizando el WACC.

Múltiplos Comparables: Un método de validación clave que compara a la empresa con un "peer set" para evaluar su posición en el mercado.

WACC (Weighted Average Cost of Capital): La herramienta calculará el costo promedio ponderado de financiar la empresa, basándose en el costo del capital y la deuda.

Análisis de Sensibilidad: Esta funcionalidad permitirá a los usuarios evaluar cómo los cambios en variables críticas, como el WACC o la tasa de crecimiento, influyen en la valoración.

IV. Endpoints de la API
Los endpoints se han estructurado para permitir a los usuarios obtener información relevante y ejecutar los análisis de valoración de manera secuencial y lógica.

Buscar Empresas (GET /companies/search): Permite encontrar empresas por nombre o ticker para iniciar el análisis.

Ficha de Empresa (GET /companies/{id}): Devuelve información general y de contextualización sobre una empresa.

Estados Financieros (GET /companies/{id}/financials): Entrega los datos financieros históricos para su uso en los modelos de valoración.

Precios de Mercado (GET /market/{ticker}/timeseries): Proporciona precios históricos de la acción y otros datos de mercado.

Indicadores Macroeconómicos (GET /macro/series): Retorna variables como inflación y tasas de interés relevantes para las proyecciones.

Noticias de la Empresa (GET /news/{ticker}): Permite acceder a noticias recientes para una comprensión cualitativa.

Calcular WACC (GET /risk/wacc): Ejecuta el cálculo del costo promedio ponderado de capital.

Valoración DCF (POST /valuation/dcf): Realiza la valoración completa de una empresa.

Análisis de Sensibilidad (POST /valuation/sensitivity): Muestra el impacto de las variaciones de las variables de entrada en el resultado final de la valoración.

V. Fuentes de Datos y APIs Externas
Para asegurar la robustez del proyecto, la API se conectará a diversas fuentes de datos financieras y macroeconómicas.

Financial Modeling Prep (FMP): Se utilizará para obtener estados financieros, múltiplos de valoración y datos históricos de betas.

Alpha Vantage & yfinance: Proporcionarán precios históricos y otros indicadores del mercado.

Banco Central de Chile (BCCh) y FRED: Fuentes de datos macroeconómicos clave, como la Tasa de Política Monetaria, inflación y tasas de bonos soberanos.

World Bank API y CMF Chile: Servirán para complementar la información con datos de desarrollo económico y estados financieros oficiales de empresas chilenas.

Esta combinación de fuentes garantiza que la API cuente con datos reales, actualizados y trazables, permitiendo un análisis financiero de alta calidad.






