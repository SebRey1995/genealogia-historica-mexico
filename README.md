# Genealogía Histórica México

Repositorio de indexación manual y análisis genealógico de registros parroquiales históricos de México, con énfasis en colecciones no indexadas o con indexaciones incompletas en FamilySearch.

---

## ¿Por qué existe este proyecto?

FamilySearch alberga millones de imágenes de registros históricos mexicanos que permanecen **sin indexar** o con **indexaciones incorrectas**. Aunque FamilySearch ha comenzado a implementar búsqueda de texto completo mediante inteligencia artificial, esta herramienta aún no está disponible para todas las colecciones, y cuando lo está, puede cometer errores que un investigador humano con criterio paleográfico y genealógico puede identificar y corregir.

Este repositorio cubre ese vacío mediante:

- **Indexación manual y verificada** de imágenes de FamilySearch
- **Contexto histórico y geográfico** de cada localidad documentada
- **Análisis estadístico** de apellidos, fechas y redes sociales parroquiales
- **Visualizaciones cartográficas** de dispersión de familias y apellidos

---

## Cómo colaborar

Para participar, envía un correo a 📧 **sebastianr3y3s95@gmail.com** indicando tu nombre, la colección que te interesa documentar, y tu experiencia en genealogía o paleografía (no excluyente). Se te asignará una colección y se te indicará qué modalidad de trabajo usar.

### Modalidad A — Git (recomendada si sabes usarlo)

Haces `git clone` del repositorio, trabajas el CSV directamente desde tu computadora en Excel o LibreOffice Calc, y subes los cambios con `git push`. No requiere conexión constante a internet mientras capturas.

### Modalidad B — Google Sheets (para quienes no usan Git)

Se te compartirá el Google Sheet de la colección asignada. Trabajas directamente desde el navegador. Los datos se sincronizan automáticamente con el repositorio cada 24 horas.

---

## Instrucciones para colaboradores

### Regla principal
Los registros deben capturarse de forma **secuencial**, siguiendo el número de imagen creciente de FamilySearch. No saltes imágenes ni captures registros fuera de orden.

### Flujo de trabajo
1. Identifica el número de imagen donde termina el último registro capturado
2. Continúa desde la siguiente imagen
3. Llena todos los campos que el documento permita leer
4. Si un campo es ilegible, escribe `Ilegible`
5. Si un campo no aparece en el documento, déjalo **vacío**
6. Usa el campo `notas` para cualquier observación relevante

### Convenciones de escritura
| Situación | Qué escribir |
|---|---|
| Campo no visible en el documento | Dejar vacío |
| Campo presente pero ilegible | `Ilegible` |
| Nombre dudoso | Escribirlo con `(?)` al final, ej: `Anastasio (?)` |
| Fecha parcial | Escribir lo que se lee, ej: `1858-??-14` |
| Padre o madre fallecido/a | Marcar `TRUE` en la columna correspondiente |

### Sobre la columna `calidad_lectura`
| Valor | Significado |
|---|---|
| `buena` | La mayoría de los campos son legibles |
| `parcial` | Algunos campos son ilegibles por deterioro o tinta |
| `ilegible` | El documento está muy deteriorado; solo se captura metadata |

---

## Descripción de campos del CSV

### Metadatos del registro
| Campo | Descripción |
|---|---|
| `id` | Número consecutivo único dentro de la colección |
| `anio` | Año del registro |
| `numero_acta` | Número de acta o folio dentro del registro |
| `imagen_num` | Número de imagen en FamilySearch |
| `fecha` | Fecha en formato `AAAA-MM-DD` |
| `calidad_lectura` | `buena`, `parcial` o `ilegible` |

### Pretendiente
| Campo | Descripción |
|---|---|
| `pret_nombre` | Nombre(s) de pila |
| `pret_ap_paterno` | Apellido paterno |
| `pret_ap_materno` | Apellido materno |
| `pret_edad` | Edad al momento del matrimonio |
| `pret_estado_civil` | `soltero`, `viudo` u otro |
| `pret_origen` | Lugar de origen declarado |
| `pret_vecino_de` | Lugar de residencia al momento del registro |
| `pret_padre_nombre` | Nombre del padre |
| `pret_padre_ap_paterno` | Apellido paterno del padre |
| `pret_padre_ap_materno` | Apellido materno del padre |
| `pret_padre_difunto` | `TRUE` si el padre había fallecido |
| `pret_madre_nombre` | Nombre de la madre |
| `pret_madre_ap_paterno` | Apellido paterno de la madre |
| `pret_madre_ap_materno` | Apellido materno de la madre |
| `pret_madre_difunta` | `TRUE` si la madre había fallecido |

### Pretendienta
Mismos campos con prefijo `prta_`.

### Testigos
| Campo | Descripción |
|---|---|
| `testigo1_nombre` | Nombre del primer testigo |
| `testigo1_ap_paterno` | Apellido paterno |
| `testigo1_ap_materno` | Apellido materno |
| `testigo2_nombre` | Nombre del segundo testigo |
| `testigo2_ap_paterno` | Apellido paterno |
| `testigo2_ap_materno` | Apellido materno |
| `testigo3_nombre` | Nombre del tercer testigo (si aplica) |
| `testigo3_ap_paterno` | Apellido paterno |
| `testigo3_ap_materno` | Apellido materno |

### Campos adicionales
| Campo | Descripción |
|---|---|
| `casta_pret` | Calidad o casta declarada del pretendiente (siglos XVII–XVIII) |
| `casta_prta` | Calidad o casta declarada de la pretendienta |
| `notas` | Observaciones del indexador |

---

## Colecciones documentadas

| Estado | Municipio | Parroquia | Período | Registros capturados |
|---|---|---|---|---|
| Veracruz | Naolinco | San Mateo Apóstol |1647–1765 | En progreso |
| Puebla | Izúcar de Matamoros | Santa María de la Asunción | 1857–1858 | Pendiente |

---

## Tecnologías utilizadas

- **Captura de datos**: LibreOffice Calc / Excel / Google Sheets
- **Versionamiento**: GitHub
- **Análisis**: R (tidyverse, ggplot2, lubridate, wordcloud2)
- **Cartografía**: QGIS con capas de INEGI

---

## Créditos y licencia

Proyecto desarrollado por **Sebastian Alberto Reyes Romero**, Ingeniero en Energías Renovables, investigador genealógico independiente y colaborador del [Seminario de Genealogía Mexicana](https://gw.geneanet.org/sanchiz_w?lp=0).

Los datos capturados en este repositorio son de libre uso para fines de investigación genealógica e histórica, siempre que se cite la fuente original de FamilySearch y este repositorio. Las imágenes de FamilySearch no se redistribuyen — solo se referencian mediante número de imagen.
