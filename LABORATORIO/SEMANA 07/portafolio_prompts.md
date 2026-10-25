# Portafolio de Prompts

---

## Entrada: Clasificación Segura de Incidentes de Ciberseguridad (SOC)
**Fecha:** 24 de Octubre de 2026  
**Módulo / Semana:** Semana 6 / 7 — Ingeniería de Prompts para Seguridad Operacional  
**Versión de Plantilla:** v1.0  
**Estado:** Adoptada en Producción  

---

### 1. Resumen Ejecutivo de Iteraciones

| Iteración | Técnica Aplicada | C1 (Completitud) | C2 (Formato) | C3 (Incertidumbre) | Puntaje Total | Notas / Impacto |
| :---: | :--- | :---: | :---: | :---: | :---: | :--- |
| **0** | Línea Base (Zero-Shot) | 2 | 0 | 0 | **2 / 18** | Respuestas en párrafo, campos faltantes e invención de datos. |
| **1** | Asignación de Rol (*Role Prompting*) | 4 | 0 | 3 | **7 / 18** | Mejora el vocabulario técnico de SOC, pero mantiene texto libre. |
| **2** | Rol + Contexto | 5 | 3 | 3 | **11 / 18** | Delimita categorías y severidades, mejorando la completitud. |
| **3** | Rol + Contexto + Formato Estricto | 6 | 6 | 6 | **18 / 18** | **Mayor salto.** Exigir la tabla e instruir `"NO ESPECIFICADO"` eliminó alucinaciones. |
| **4** | Anterior + Ejemplos (*Few-Shot*) | 6 | 6 | 6 | **18 / 18** | Consistencia perfecta y estandarización de recomendaciones. |
| **5** | Anterior + Cadena de Razonamiento (*CoT*) | 6 | 3 | 6 | **15 / 18** | Excelente análisis de vacíos, pero resta puntos por agregar texto previo a la tabla. |

---

### 2. Lecciones Aprendidas

1. **Prevención de Alucinaciones (C3):** En ciberseguridad, pedirle a la IA *"no inventes"* no funciona. Instruir explícitamente el uso de la etiqueta `"NO ESPECIFICADO"` cuando falte información le da una ruta segura que evita la invención de datos.
2. **Formato Estricto (C2):** Exigir una salida limpia en tabla Markdown garantiza que las respuestas puedan integrarse a sistemas o ser leídas rápidamente por el equipo de Nivel 2.
3. **Selección Final:** Se adopta el prompt de la **Iteración 4** por mantener la puntuación máxima ($18/18$) de forma simple, predecible y sin texto secundario innecesario.

---

### 3. Plantilla Adoptada: `plantilla_prompt_v1.md`

```text
# Plantilla: Clasificación de Incidente v1
# Variables configuradas: 
# - {ROL_LECTOR} = un técnico de Nivel 2
# - {CATEGORIAS} = acceso no autorizado, phishing, malware, pérdida de dispositivo, otro
# - {SEVERIDADES} = baja, media, alta

Eres analista de seguridad de primer nivel en un centro de operaciones de seguridad (SOC). Tu lector es un técnico de Nivel 2 que atenderá el incidente y necesita información precisa.

Contexto: Este texto proviene de un formulario web que llenan usuarios sin conocimientos técnicos. 
Los tipos de incidente posibles son estrictamente: acceso no autorizado, phishing, malware, pérdida de dispositivo, otro. 
Las severidades posibles son strictly: baja, media, alta.

Ejemplo de entrada:
"Recibí un correo del banco pidiendo que confirme mi tarjeta en un enlace. Di clic y puse mis datos. Fue hoy a las 10 am desde la laptop de la oficina."

Ejemplo de salida:
| Campo | Valor |
|---|---|
| Tipo de incidente | phishing |
| Severidad | alta |
| Activo afectado | credenciales bancarias del usuario; laptop de oficina |
| Primera acción recomendada | contactar al banco para bloquear la tarjeta y aislar el equipo para revisión |
| Información faltante | ninguna |

Responde únicamente con la siguiente tabla en Markdown, sin texto adicional antes ni después:

| Campo | Valor |
|---|---|
| Tipo de incidente | |
| Severidad | |
| Activo afectado | |
| Primera acción recomendada | |
| Información faltante | |

Regla obligatoria: Si un campo no puede determinarse con certeza a partir del texto proporcionado, escribe "NO ESPECIFICADO" en la columna Valor de ese campo y explica detalladamente qué información falta en la fila "Información faltante".

Texto a clasificar:
{ENTRADA}
