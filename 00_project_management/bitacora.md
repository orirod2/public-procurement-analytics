# Bitácora del proyecto: riesgo de pérdida de recursos en SECOP II

## Hecho (21 de noviembre de 2026)

- [x] Estructura de carpetas `00_project_management` a `06_reports` (se corrigieron los nombres que terminaban en ":")
- [x] Entorno virtual `.venv` con polars, pandas, duckdb, httpx, pyarrow y matplotlib
- [x] Notebook `03_notebooks/01_exploracion_metadatos.ipynb`:
  - [x] Consulta a la API de metadatos del dataset `jbjy-vk9h` (SECOP II - Contratos Electrónicos)
  - [x] Exploración de las 95 columnas (name, fieldName, tipo, descripción)
  - [x] Diccionario de datos: 47 variables clave en 5 grupos (entidad, contrato, fechas, proveedores, información presupuestal), cada una con su descripción
  - [x] Borrador de indicadores de riesgo en 4 módulos (hecho con apoyo de IA, por revisar)
- [x] Tema definido: pérdida de recursos, riesgo de corrupción y contratos inconclusos ("elefantes blancos")

## Falta

### Próxima sesión
- [x] Configurar Git: nombre y correo, `git init`, `.gitignore`, `requirements.txt` y primer commit
- [x] Publicar en GitHub: https://github.com/orirod2/public-procurement-analytics (público)
- [ ] Agregar descripción al repositorio en GitHub
- [ ] Activar Auto Save en VS Code
- [ ] Decidir el alcance: se recomienda empezar con los módulos 2 (riesgo financiero) y 3 (favoritismo y planeación)
- [ ] Escribir con mis palabras, para cada bandera roja elegida: qué significa, por qué indica riesgo y qué explicación inocente podría tener

### Datos
- [ ] Descargar una muestra pequeña con la API (pocos miles de filas, solo las 47 columnas) y guardarla en Parquet en `02_data/raw`
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
