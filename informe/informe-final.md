# B) Informe final

## 1. Título

**Sistema de apoyo a decisiones para movilidad inteligente basado en datos de videovigilancia urbana en el Callao**

Autores: H. Herrera, R. Portilla
Afiliación: Universidad Nacional Mayor de San Marcos — Facultad de Ingeniería de Sistemas e Informática, Lima, Perú.

## 2. Qué datos abiertos se usaron

- **Dataset:** *Registro de incidencias observadas mediante la central de monitoreo de cámaras de videovigilancia de la Municipalidad Provincial del Callao*.
- **Publicador:** Plataforma Nacional de Datos Abiertos (PNDA) del Perú, bajo responsabilidad de la Municipalidad Provincial del Callao.
- **Recorte usado:** categoría *Tránsito y Seguridad Vial*, periodo abril de 2026.
- **Volumen:** 62,916 incidencias válidas después del proceso de depuración.
- **Variables disponibles:** fecha, hora, ubicación geográfica, zona, base de monitoreo y tipo de incidencia.
- **Calidad verificada:** 99.93% de coordenadas geográficas válidas y 99.93% de tiempos de atención válidos tras el preprocesamiento.

## 3. Cuál es la brecha digital que cubre

La Municipalidad ya cuenta con la infraestructura de videovigilancia y publica los registros como datos abiertos, pero esa información se usa casi exclusivamente con **fines operativos inmediatos** (atender el incidente puntual), no para decisiones tácticas o estratégicas. Existe entonces una brecha entre **generar/publicar datos** y **aprovecharlos analíticamente**.

La revisión de literatura del artículo confirma esta brecha a nivel de investigación: hay propuestas de DSS para movilidad, de videovigilancia con visión computacional, y de arquitecturas cloud para datos abiertos, pero **poca evidencia de trabajos que integren las tres cosas** — registros históricos de videovigilancia publicados como datos abiertos + indicadores temporales/espaciales/operativos + arquitectura cloud escalable — para apoyar decisiones de movilidad inteligente. El artículo cubre justamente ese vacío.

## 4. Resumen del artículo

La movilidad inteligente es un componente clave de las ciudades inteligentes para mejorar la gestión del tránsito mediante datos urbanos. En el Callao, los registros de la central de videovigilancia se usan sobre todo operativamente, limitando su aprovechamiento para la toma de decisiones. El trabajo propone un **sistema de apoyo a decisiones (DSS)** basado en el análisis de datos abiertos de incidencias de tránsito y seguridad vial de la Municipalidad Provincial del Callao, usando la metodología **Design Science Research** para diseñar una **arquitectura cloud** de procesamiento, análisis y generación de indicadores temporales, espaciales y operativos. La propuesta se validó con una prueba de concepto sobre 62,916 registros de abril de 2026, identificando patrones útiles para priorizar recursos y planificar acciones de movilidad urbana. Los resultados muestran el potencial de reutilizar datos abiertos ya existentes para fortalecer la gestión de ciudades inteligentes.

## 5. Caso de Estudio

**Contexto:** la Provincia Constitucional del Callao es una de las principales zonas logísticas del Perú (Puerto del Callao, Aeropuerto Jorge Chávez, red vial que conecta con Lima Metropolitana), lo que genera alta demanda sobre la infraestructura vial.

**Marco normativo que respalda la propuesta:** Gobierno Digital del Estado peruano (Decreto Legislativo N.° 1412 y su reglamento) y Política Nacional de Transformación Digital al 2030.

**Resultados obtenidos con los 62,916 registros analizados:**

- **Temporal:** pico de incidencias a las 18:00 h (4,229 casos, 6.72%), seguido de 19:00 h (4,080, 6.48%) y 20:00 h (3,821, 6.07%) — coincide con la hora punta vehicular.
- **Espacial:** mayor concentración en Zona 3 / Sector 11 – Cía. Oquendo (20,291 registros, 32.25%), seguida de Zona 2 / Sector 7 – Playa Rímac (11,477, 18.24%).
- **Operativo:** la Base Descentralizada C–Oquendo concentra el mayor volumen (21,506 casos, 34.18%), seguida de la Base C–Quilca (16,184, 25.72%). Tiempo promedio de atención: 14.51 min (mediana 14.52 min), con baja dispersión.

**Limitaciones declaradas:** el análisis depende de la cobertura de la central de videovigilancia y de la disponibilidad de datos publicados; cubre un único mes; y no incorpora datos en tiempo real (solo históricos).

## 6. A qué ODS aporta el trabajo / Cómo apoya a la responsabilidad social

- **ODS 11 — Ciudades y Comunidades Sostenibles**, en particular la **meta 11.2** (acceso a sistemas de transporte seguros, accesibles y sostenibles, y mejora de la seguridad vial). El artículo lo referencia explícitamente como marco de contribución.
- **Responsabilidad social:** el sistema reutiliza información pública ya generada por el Estado para mejorar la seguridad vial y la gestión del tránsito, sin requerir inversión adicional en infraestructura. Esto apoya la priorización de recursos municipales (por ejemplo, reforzar monitoreo en las horas y zonas de mayor incidencia) y una gestión pública más transparente y basada en evidencia, alineada con el marco de Gobierno Digital y la Política Nacional de Transformación Digital al 2030 del Perú.

## 7. Cómo aporta a I+D+i

- **Investigación:** aplica formalmente la metodología Design Science Research a un problema no resuelto en la literatura — la falta de DSS que integren datos abiertos de videovigilancia urbana con indicadores multinivel y arquitectura cloud — llenando la brecha identificada en el estado del arte.
- **Desarrollo:** diseña y valida una arquitectura cloud concreta por capas (Amazon S3 en zonas Raw/Clean/Curated, AWS Glue, Amazon Athena, Amazon RDS PostgreSQL, Amazon QuickSight) junto con un motor DSS que interpreta indicadores en tres niveles de decisión (operativo, táctico, estratégico).
- **Innovación:** demuestra que es posible generar información de valor para movilidad inteligente **reutilizando infraestructura y datos públicos ya existentes**, sin las grandes inversiones tecnológicas que requieren otras experiencias internacionales (p. ej. Río de Janeiro, Anyang) — un modelo reproducible y de bajo costo, aplicable a otras entidades públicas peruanas con datos abiertos similares.

## 8. Conclusiones

El trabajo presenta una propuesta de DSS para movilidad inteligente basada en datos de la central de videovigilancia del Callao. El análisis de 62,916 incidencias permitió identificar patrones temporales, espaciales y operativos relevantes para planificar y priorizar acciones de gestión de la movilidad urbana. Se evidencia que los registros históricos de videovigilancia pueden transformarse en indicadores útiles para la toma de decisiones (horarios pico, zonas críticas, distribución de carga operativa entre bases), demostrando el potencial de aprovechar datos abiertos ya disponibles sin infraestructura tecnológica adicional.

**Trabajo futuro:** ampliar el sistema incorporando datos en tiempo real de sensores de tránsito e IoT, e integrar técnicas de analítica predictiva para anticipar patrones de movilidad y fortalecer la toma de decisiones en ciudades inteligentes.
