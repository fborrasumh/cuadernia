# CuadernIA

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22035491.svg)](https://doi.org/10.5281/zenodo.22035491)

**Aplicación:** https://fborrasumh.github.io/cuadernia/

Genera un **cuaderno Jupyter** de análisis estadístico a partir de un fichero de datos y una descripción del estudio. Cada celda se **ejecuta en el navegador** con tus datos, se corrige si falla y la revisa un agente estadístico. El cuaderno sale ya ejecutado, con sus resultados dentro. Aplicación de un solo fichero, sin servidor.

## Novedades de la versión 2.0

- Interfaz guiada con el estilo de Forja y tres ejemplos con datos simulados: dos grupos, antes y después, y respuesta binaria.
- **Ejecución real** con Pyodide (Python 3.12, pandas 2.2, SciPy 1.12, statsmodels 0.14, matplotlib) en un Web Worker. Detecta errores, bucles infinitos y celdas sin salida.
- **Cadena de agentes**: el planificador y el revisor del plan trabajan antes de programar; después, el programador, la comprobación sin IA, el depurador con el error real, el revisor estadístico con la salida real y el auditor final con ocho criterios fijos.
- **Cuaderno ejecutado** (nbformat 4.5, con identificadores de celda), con un informe de verificación dentro y metadatos que lee NarrativIA.
- Papeles de las variables por clic, tipos corregibles, modo «Solo revisar» y descarga en `.zip`.

## Qué hace

1. **Datos.** CSV (coma, punto y coma o tabulador, con decimales españoles) o Excel, perfilado en local.
2. **Estudio.** Objetivo, diseño, papel de cada variable, α y notas.
3. **Plan.** Entre 7 y 10 secciones, revisadas antes de escribir código y editables.
4. **Verificación.** Cada sección se programa, se comprueba, se ejecuta, se depura y se revisa.
5. **Cuaderno.** `.ipynb` ejecutado, `datos.csv` e informe de verificación.

## Salida para NarrativIA

El cuaderno está pensado como entrada de [NarrativIA](https://fborrasumh.github.io/narrativia/), que redacta la sección de Resultados a partir de las salidas. Con la versión 2.0 ya llega ejecutado.

## Privacidad

Los datos se procesan y se ejecutan en el navegador. Al modelo solo llegan el perfil estadístico, el contexto del estudio, el código y sus salidas; las filas de ejemplo son configurables y admiten 0 para datos sensibles. La clave se guarda en `localStorage` (`ia_openai_key`). La primera ejecución descarga el motor de Python, unos 30 MB que quedan en caché.

## Cómo citar

Borrás Rocher, F. (2026). *CuadernIA* (versión 2.0.0) [Software]. Universidad Miguel Hernández de Elche. https://doi.org/10.5281/zenodo.22035491

El DOI anterior es el de concepto: apunta siempre a la última versión. El DOI de cada versión concreta está en [Zenodo](https://doi.org/10.5281/zenodo.22035491). GitHub ofrece la cita en formato APA y BibTeX con el botón *Cite this repository*, a partir de `CITATION.cff`.

Forma parte del catálogo [Herramientas IA para la academia](https://fborrasumh.github.io/ia/).

## Licencia

MIT © 2026 Fernando Borrás Rocher · Universidad Miguel Hernández de Elche.
