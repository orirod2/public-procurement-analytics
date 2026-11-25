# Bitácora del proyecto: riesgo de pérdida de recursos en SECOP II

## Hecho (21 de noviembre de 2026)

- [x] Estructura de carpetas `00_project_management` a `06_reports` (se corrigieron los nombres que terminaban en ":")
- [x] Entorno virtual `.venv` con polars, pandas, duckdb, httpx, pyarrow y matplotlib (reemplazado el 24 de noviembre, ver abajo)
- [x] Notebook `03_notebooks/01_exploracion_metadatos.ipynb`:
  - [x] Consulta a la API de metadatos del dataset `jbjy-vk9h` (SECOP II - Contratos Electrónicos)
  - [x] Exploración de las 95 columnas (name, fieldName, tipo, descripción)
  - [x] Diccionario de datos: 47 variables clave en 5 grupos (entidad, contrato, fechas, proveedores, información presupuestal), cada una con su descripción
  - [x] Borrador de indicadores de riesgo en 4 módulos (hecho con apoyo de IA, por revisar)
- [x] Tema definido: pérdida de recursos, riesgo de corrupción y contratos inconclusos ("elefantes blancos")

## Hecho (22 de noviembre de 2026)

- [x] Notebook `02_muestra_datos`: respuesta de la API convertida en tabla de polars (DataFrame)
- [x] `valor_del_contrato` convertido de texto a número (`Float64`); la API entrega todos los valores como texto
- [x] Descargas reproducibles con `$order` y `timeout` en las peticiones
- [x] Se detectó sesgo al ordenar por `id_contrato` (98 % de contratos de 2026); se ordena por `:id`, que da proporciones por año parecidas al total
- [x] Muestra de 20.000 contratos con las 47 columnas guardada en `02_data/raw/muestra_20k.parquet` (datos crudos, sin modificar; reemplazada el 25 de noviembre, ver abajo)

## Hecho (24 de noviembre de 2026)

- [x] Proyecto movido fuera de iCloud a `~/Proyectos/public-procurement-analytics` (iCloud dejaba archivos sin descargar y el kernel se colgaba)
- [x] Entorno virtual nuevo fuera del proyecto, en `~/.venvs/elipsis`, con el kernel "Elipsis (Python 3.14)"
- [x] Notebook `03_calidad_datos`: faltantes, subregistro de pagos y nota de limitaciones de SECOP II

## Hecho (25 de noviembre de 2026)

- [x] Se pausa la limpieza y se rehace el plan con fases (entorno, investigación, mapa de las 95 columnas, indicadores, limpieza reproducible, análisis y comunicación)
- [x] Primer pull request en Elipsis (#1): exploración inicial de la limpieza (`04_limpieza.ipynb`)
- [x] Fase 0 en la rama `fase0-entorno`:
  - [x] Kernel de los notebooks 01 y 02 cambiado al entorno `elipsis`
  - [x] `requirements.txt` solo con dependencias directas (polars, httpx, matplotlib, ipykernel); se quitan pandas, duckdb y pyarrow porque no se usan (duckdb podría volver en la fase 4)
  - [x] `requirements-dev.txt` con pytest y ruff
  - [x] Licencia MIT
  - [x] README corto en las carpetas vacías
- [x] Muestra nueva: volver a correr el notebook 02 sobrescribió la muestra del 22 de noviembre y no se pudo recuperar. SECOP II cambia a diario (por ejemplo, "terminado" pasó de 2.826 a 2.816). La muestra oficial es ahora `muestra_20k_2026-11-25.parquet` y el notebook 02 ya no sobrescribe un archivo existente. Las cifras de las notas se recalculan en la fase 2.

## Falta

### Pendientes inmediatos
- [x] Configurar Git: nombre y correo, `git init`, `.gitignore`, `requirements.txt` y primer commit
- [x] Publicar en GitHub: https://github.com/orirod2/public-procurement-analytics (público)
- [x] Agregar descripción y topics al repositorio en GitHub
- [x] README en inglés (README.md) y en español (README.es.md)
- [x] Notebook 02_muestra_datos: primera descarga de 5 contratos con la API (usando params)
- [x] Convertir la respuesta de la API en una tabla de polars y pasar valor_del_contrato de texto a número
- [ ] **Siguiente:** abrir la muestra desde el archivo Parquet y medir qué tan completos vienen los datos
- [ ] Activar Auto Save en VS Code
- [ ] Decidir el alcance: se recomienda empezar con los módulos 2 (riesgo financiero) y 3 (favoritismo y planeación)
- [ ] Escribir con mis palabras, para cada bandera roja elegida: qué significa, por qué indica riesgo y qué explicación inocente podría tener

### Datos
- [x] Descargar una muestra con la API (20.000 filas, las 47 columnas) y guardarla en Parquet en `02_data/raw`
- [ ] Verificar si algún `valor_del_contrato` tiene decimales (para decidir entre `Float64` e `Int64`)
- [ ] Medir qué tan completos vienen los datos, sobre todo las columnas de pagos (`valor_pagado`, `valor_facturado`, etc.)
- [ ] Verificar si `nombre_representante_legal` corresponde a la entidad o al proveedor
- [ ] Convertir `duraci_n_del_contrato` (texto, por ejemplo "87 Dia(s)") a número de días
- [ ] Definir el periodo o sector final y descargar los datos completos

### Análisis
- [ ] Limpieza de datos
- [ ] Programar las banderas rojas de los módulos elegidos
- [ ] Construir un índice de riesgo por entidad o contratista
- [ ] Visualizaciones

### Cierre
- [ ] README del proyecto: pregunta, datos, decisiones, hallazgos y limitaciones
- [ ] Subir a GitHub
- [ ] Documento corto para la profesora (contactarla idealmente al tener los primeros números reales)
- [ ] **Dashboard en Streamlit (producto principal)** para que personas que no programan vean los resultados
- [ ] Infografía de una página con los 3 a 5 hallazgos principales (LinkedIn, profesora)
- [ ] Opcional: fase 2 con análisis de redes (módulo 4)

### Preguntas que debe responder el dashboard (definir antes del análisis)
- [ ] Escribir 3 a 5 preguntas, por ejemplo: ¿qué entidades tienen más contratos con señales de riesgo?, ¿cuánto dinero hay en anticipos sin justificar?, ¿dónde se concentra la contratación directa?

## Recordatorios
- Hablar de "indicadores de riesgo", no de "corrupción".
- No publicar nombres ni documentos de personas.

