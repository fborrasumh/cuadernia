# CuadernIA

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22035491.svg)](https://doi.org/10.5281/zenodo.22035491)

**Aplicación:** https://fborrasumh.github.io/cuadernia/

Genera un **cuaderno Jupyter** de análisis estadístico a partir de un fichero de datos y una descripción del estudio. Cada celda se **ejecuta en el navegador** con tus datos, se corrige si falla y la revisa un agente estadístico. El cuaderno sale ya ejecutado, con sus resultados dentro. Aplicación de un solo fichero, sin servidor.

**Idiomas:** español, inglés y portugués; selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL). El cuaderno puede generarse además en catalán y valenciano.

## Novedades de la versión 3.0

- **Tres proveedores de IA** con tu propia clave: OpenAI, Google Gemini y Anthropic Claude, con desplegable de los modelos disponibles en tu clave.
- **Interfaz en español, inglés y portugués**, incluidos los tres ejemplos con datos simulados (columnas y niveles traducidos) y el texto fijo que se escribe dentro del cuaderno y del informe.
- **Privacidad reforzada:** antes del primer envío se muestra lo que sale hacia el proveedor, y el correo, el documento de identidad y el teléfono se enmascaran.
- **Descargas sin conexión:** el `.zip` y el informe en Word se generan en el navegador, sin librerías externas. Nuevo informe de verificación en Word.
- Lectura de CSV con analizador propio (coma, punto y coma o tabulador, decimales con coma); SheetJS solo se descarga si subes un Excel.
- Mismo motor de ejecución (Pyodide, Python 3.12, pandas 2.2, SciPy 1.12, statsmodels 0.14, matplotlib) y misma cadena de agentes que la versión 2.0.

## Qué hace

1. **Datos.** CSV o Excel, perfilado en local; los tipos de variable se pueden corregir.
2. **Estudio.** Objetivo, diseño, destino, papel de cada variable, α y notas.
3. **Plan.** Entre 7 y 10 secciones, revisadas por un segundo agente antes de escribir código y editables.
4. **Verificación.** Cada sección se programa, se comprueba sin IA, se ejecuta, se depura con el error real de Python y la revisa un agente estadístico; al final, una auditoría con ocho criterios fijos.
5. **Cuaderno.** `.ipynb` ejecutado (nbformat 4.5), `datos.csv`, informe de verificación (`.md` y Word) y `.zip` con todo.

## Salida para NarrativIA

El cuaderno está pensado como entrada de [NarrativIA](https://fborrasumh.github.io/narrativia/), que redacta la sección de Resultados a partir de las salidas.

## Cómo se usa la IA

Con la propia clave de OpenAI, Google Gemini o Anthropic Claude. La clave se guarda solo en el navegador (`localStorage`; la de OpenAI es compartida con el resto del catálogo bajo `ia_openai_key`). No hace falta servidor. Cada cuaderno realiza decenas de consultas: conviene un modelo económico.

## Privacidad

- Los datos se procesan y se ejecutan en el navegador; **las filas no se guardan** (solo el estudio, el plan y los cuadernos terminados, en IndexedDB).
- Al proveedor de IA solo llegan el perfil estadístico, el contexto del estudio, el código y sus salidas, y las filas de muestra que indiques (0 = ninguna). Correo, documento de identidad y teléfono se enmascaran antes de enviar. Las columnas con datos identificativos pueden aparecer en los niveles de las variables: con datos de personas, usa datos sin identificar.
- La primera ejecución descarga el motor de Python (unos 30 MB) desde jsDelivr; después queda en la caché del navegador.

## Límites

- Los agentes de IA pueden equivocarse. La verificación automática reduce errores (código que falla, pruebas incoherentes con el diseño), pero **no sustituye el criterio del investigador**: revisa siempre las decisiones estadísticas.
- Solo están disponibles pandas, NumPy, SciPy, statsmodels y matplotlib (y scikit-learn si es imprescindible).
- Una celda que supera 90 s se detiene y se reinicia el motor.
- El texto fijo en catalán y valenciano no ha sido revisado por hablantes nativos.

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche).

ORCID: Fernando Borrás Rocher [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573)

## Cómo citar

Borrás Rocher, F. (2026). *CuadernIA* (versión 3.0.0) [Software]. Universidad Miguel Hernández de Elche. https://doi.org/10.5281/zenodo.22035491

El DOI anterior es el de concepto: apunta siempre a la última versión. GitHub ofrece la cita en formato APA y BibTeX con el botón *Cite this repository*, a partir de `CITATION.cff`.

Forma parte del catálogo [Herramientas IA para la academia](https://fborrasumh.github.io/ia/).

## Licencia

MIT © 2026 Fernando Borrás Rocher · Universidad Miguel Hernández de Elche.
