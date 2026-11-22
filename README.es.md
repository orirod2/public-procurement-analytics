[English](README.md) | **Español**

# Elipsis: indicadores de riesgo en la contratación pública colombiana
## Descripción
La contratación pública es uno de los principales canales a través de los cuales los gobiernos asignan recursos públicos. Sin embargo, las debilidades en los procesos de contratación, la competencia limitada, la concentración de proveedores y los patrones contractuales recurrentes pueden generar condiciones asociadas a una asignación ineficiente de los recursos y a posibles riesgos de pérdida de recursos públicos.

Este proyecto busca identificar y analizar indicadores de riesgo asociados a la posible pérdida de recursos públicos en la contratación pública colombiana, a partir de los datos abiertos de SECOP II, la plataforma electrónica de contratación pública del país.

La investigación examinará los patrones contractuales entre entidades públicas y proveedores, con énfasis en variables como el valor de los contratos, las modalidades de contratación, la participación de los proveedores, las relaciones contractuales recurrentes, la distribución geográfica y las tendencias en el tiempo. Mediante la extracción y el procesamiento de datos, el análisis exploratorio, métodos estadísticos y visualizaciones, el estudio busca identificar patrones que ameriten una revisión más profunda. Según la disponibilidad de los datos y su relevancia analítica, también podrían incorporarse técnicas de análisis de redes, agrupamiento (clustering) y detección de anomalías.

## Estado del proyecto
En desarrollo: exploración de datos

## Datos
- Nombre del dataset: SECOP II – Contratos Electrónicos
- Proveedor de los datos: Agencia Nacional de Contratación Pública – Colombia Compra Eficiente, Bogotá D.C.
- Propietario del dataset: Datos Abiertos CCE
- Última actualización de los datos: 21 de noviembre de 2026
- Última actualización de los metadatos: 25 de octubre de 2026
- Fecha de creación: 30 de septiembre de 2019
- Número de registros: 5,73 millones (filas)
- Número de variables: 95 (columnas)
- Enlace al dataset: https://www.datos.gov.co/Gastos-Gubernamentales/SECOP-II-Contratos-Electr-nicos/jbjy-vk9h
- Sitio web de la fuente: https://www.colombiacompra.gov.co/

## Preguntas de investigación
1. ¿Qué contratos presentan señales de riesgo de pérdida de recursos, como anticipos sin justificar o contratos vencidos que no se terminaron ni se liquidaron?
2. ¿Qué entidades y contratistas concentran más contratos con señales de riesgo y cuánto dinero público representan?
3. ¿Hay patrones de favoritismo o mala planeación, como la concentración de contratos en pocos proveedores, el fraccionamiento de contratos o prórrogas desproporcionadas?

## Estructura del proyecto
```
public-procurement-analytics/
├── 00_project_management/   # Planeación y bitácora del proyecto
├── 01_data_sources/         # Documentación de las fuentes de datos
├── 02_data/
│   ├── raw/                 # Datos originales descargados (no se suben a GitHub)
│   └── processed/           # Datos limpios y transformados (no se suben a GitHub)
├── 03_notebooks/            # Notebooks de exploración y análisis
├── 04_src/                  # Código reutilizable (funciones y scripts)
├── 05_visualizations/       # Gráficas y figuras
├── 06_reports/              # Informes y resultados finales
├── requirements.txt         # Librerías necesarias para ejecutar el proyecto
├── README.md                # Descripción del proyecto en inglés
└── README.es.md             # Descripción del proyecto en español
```

## Herramientas
- **Python 3.14**
- **httpx**: descarga de datos desde la API de datos.gov.co
- **Polars**: manipulación y limpieza de datos a gran escala
- **DuckDB**: consultas SQL sobre archivos grandes
- **PyArrow**: almacenamiento eficiente en formato Parquet
- **Matplotlib**: visualizaciones
- **Jupyter Notebooks**: exploración y documentación del análisis
- **Git y GitHub**: control de versiones

## Avances
- [x] Configuración del entorno de trabajo y de la estructura del proyecto
- [x] Exploración de los metadatos del dataset (95 columnas)
- [x] Diccionario de datos con 47 variables clave en 5 grupos: entidad, contrato, fechas, proveedores e información presupuestal
- [x] Borrador de indicadores de riesgo
- [x] Primera conexión con la API para descargar contratos
- [ ] Descarga de una muestra y evaluación de la calidad de los datos
- [ ] Limpieza y transformación de datos
- [ ] Cálculo de indicadores de riesgo
- [ ] Dashboard interactivo con los resultados

## Aviso

Este proyecto identifica **indicadores de riesgo** a partir de datos públicos. Una señal de riesgo **no es prueba de corrupción ni de irregularidad**: puede deberse a errores de registro, datos incompletos o situaciones justificadas. Los resultados buscan señalar casos que merecen revisión, no acusar a entidades ni personas. Por respeto a la privacidad, no se publican nombres ni documentos de personas naturales.
