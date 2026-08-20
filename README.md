# CuadernIA

Genera un **cuaderno Jupyter** de análisis estadístico a partir de un fichero de datos y una descripción del estudio. Aplicación web de un solo fichero (HTML + JS, sin backend): los datos se procesan íntegramente en el navegador y la clave de OpenAI se guarda solo en `localStorage`.

**App:** https://fborrasumh.github.io/cuadernia/

## Qué hace

1. **Datos.** Lee CSV (coma, punto y coma o tabulador, con decimales españoles) y Excel con selector de hoja. Perfila cada variable en local: tipo inferido, valores ausentes, únicos, cuartiles, asimetría y filas duplicadas.
2. **Estudio.** Recoge título, objetivo, diseño, variables respuesta, predictores, nivel de significación y notas del analista.
3. **Plan de análisis.** El modelo propone entre 7 y 10 secciones —preparación y calidad de datos, descriptivo univariante y bivariante, comprobación de supuestos, análisis inferencial, modelización, diagnóstico y síntesis— que se pueden editar, reordenar o eliminar antes de generar nada.
4. **Cuaderno.** Escribe las celdas sección a sección y descarga dos ficheros: el `.ipynb` (nbformat 4) y un `datos.csv` normalizado que el cuaderno carga con `pd.read_csv('datos.csv')`.

El código generado usa pandas, numpy, scipy.stats, statsmodels y matplotlib, e informa en cada prueba de n, estimación puntual, intervalo de confianza, estadístico, valor p y tamaño del efecto.

## Salida para NarrativIA

El cuaderno está pensado como entrada de [NarrativIA](https://fborrasumh.github.io/ia/), que redacta la sección de Resultados a partir de las salidas de las celdas. **Hay que ejecutarlo entero** (Jupyter o Colab) antes de subirlo: sin salidas, no hay Resultados.

## Uso

Abre la app, guarda tu clave de OpenAI en Ajustes (modelo por defecto `gpt-4o-mini`) y sigue los cuatro pasos. Solo se envían al modelo el perfil estadístico y el contexto del estudio; las filas de ejemplo son configurables y admiten 0 para datos sensibles.

## Privacidad

Sin servidor propio y sin telemetría. El fichero de datos nunca sale del navegador salvo las filas de muestra que decidas enviar. La clave se almacena en `localStorage` bajo `ia_openai_key` y viaja únicamente a `api.openai.com`.

## Licencia

MIT © Fernando Borrás Rocher — Universidad Miguel Hernández de Elche.
