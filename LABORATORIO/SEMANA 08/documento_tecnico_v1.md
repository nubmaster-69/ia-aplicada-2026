# Introducción, alcance y requisitos

**Nombre del proyecto:** Sistema Inteligente de Detección y Respuesta Temprana ante Incendios en Edificios Inteligentes mediante IoT e Inteligencia Artificial  
**Materia:** Inteligencia Artificial Aplicada  
**Carrera:** Ingeniería en Ciberseguridad | Global University  
**Integrantes:**  
* Ana Camila Salazar Baltazar  
* Regina Villaseñor Talamantes  
* Michel Alejandro Guzmán Gómez  
* Joshua Leonardo Sánchez Grajales  

---

### Datos del Proyecto (Línea Base)

* **Problema que resuelve:** Deficiencia y lentitud en la detección de incendios en edificios que carecen de tecnología avanzada, abordando la problemática en México donde el sector residencial concentra el 70% de los incidentes urbanos, registra un aumento anual del 10% en siniestros y donde el 82.7% de las muertes estructurales ocurren en viviendas.
* **Usuarios:** Operadores de centros de monitoreo de seguridad (BMS), administradores del inmueble, personal técnico de respuesta y residentes.
* **Tipo de IA propuesto:** Visión computacional con Redes Neuronales Convolucionales (CNN) para detección por video (VFD) combinada con modelos de IA sobre sensores IoT multicriterio (humo óptico, temperatura y COV).
* **Restricciones de datos:** Manejo estricto de ubicación geográfica a nivel de zona/alcaldía (evitando datos personales como calles o coordenadas exactas); prohibición de almacenar cuentas bancarias, nombres o teléfonos; cifrado en almacenamiento centralizado bajo control de acceso por roles; y firma de convenios de privacidad/encargo para compartición de datos con servicios en la nube y bomberos.

---

### 1. Introducción

El presente documento técnico establece la arquitectura y requisitos preliminares para el despliegue de un sistema de protección contra incendios asistido por Inteligencia Artificial e Internet de las Cosas (IoT) en edificios. Ante la alta incidencia de fuegos estructurales en México y la rápida propagación de los materiales sintéticos modernos, la solución integra visión artificial mediante Redes Neuronales Convolucionales (CNN) y sensores IoT multicriterio para reconocer patrones anómalos de humo y calor en milisegundos. El sistema automatiza acciones de contención inmediata y notificaciones de emergencia, reduciendo la tasa de falsas alarmas y garantizando la protección de los ocupantes.

---

### 2. Alcance

* **Qué incluye:**
  * Captura y procesamiento analógico continuo de variables ambientales (temperatura, humo óptico y compuestos orgánicos volátiles) mediante sensores IoT.
  * Análisis de video en tiempo real con cámaras VFD para la identificación incipiente de humo y llamas.
  * Integración con el sistema de gestión del edificio (BMS) para respuesta automática coordinada (desactivación de HVAC, presurización de escaleras e iluminación dinámica de rutas de evacuación).
  * Clasificación automatizada del nivel de severidad y tipo de incidente a partir de reportes ingresados en texto libre.
  * (DATO PENDIENTE: Proveedor específico y especificaciones del hardware de los sensores IoT multicriterio a desplegar)
* **Qué no incluye:**
  * Instalación o sustitución de la infraestructura física eléctrica, hidráulica o del sistema de rociadores del inmueble.
  * Reemplazo total de los protocolos de intervención presencial ni de la toma de decisiones final del cuerpo de bomberos oficial.
  * (DATO PENDIENTE: Presupuesto asignado para la adquisición de hardware e instalación de red local redundante)

---

### 3. Requisitos funcionales

* **RF-1:** El sistema deberá recibir y procesar flujos de datos continuos de sensores IoT y texto libre ingresado por usuarios para la clasificación automatizada del incidente.
* **RF-2:** El modelo de IA basado en CNN deberá clasificar el tipo de amenaza y asignar un nivel de severidad (baja, media, alta) antes de emitir cualquier orden de actuación.
* **RF-3:** El sistema generará una recomendación operativa de primera respuesta para el personal de monitoreo en un tiempo no mayor a 3 segundos tras la confirmación del riesgo.
* **RF-4:** Las lecturas y reportes de ubicación deberán anonimizarse a nivel de código de zona o alcaldía para proteger la privacidad de los residentes.
* **RF-5:** (DATO PENDIENTE: Frecuencia exacta de reentrenamiento periódico y actualización de parámetros del modelo predictivo)

---

### 4. Requisitos no funcionales

* **RNF-1:** El sistema garantizará una disponibilidad operativa ininterrumpida del 99.9% mediante respaldos de energía (UPS) y operabilidad offline local ante caídas de red.
* **RNF-2:** El almacenamiento y transferencia de datos hacia la nube o servicios de emergencia cumplirá con la LFPDPPP y LPDPPSOCDMX mediante cifrado punto a punto.
* **RNF-3:** (DATO PENDIENTE: Plazo máximo estipulado en meses para la retención y purga automatizada de bitácoras de auditoría)

---

### Declaración de generación asistida

* **Modelo usado:** Gemini (Google AI) / ChatGPT  
* **Fecha de generación:** 1 de noviembre de 2026  
* **Prompt usado:**  
  > *"Eres redactor técnico. Escribe la sección 'Introducción, alcance y requisitos' de un documento técnico para el proyecto de Protección contra incendios en Edificios Inteligentes... Usa únicamente la información proporcionada; si necesitas un dato que no está, escribe (DATO PENDIENTE) en lugar de inventarlo..."*  
* **Número de correcciones aplicadas:** 3 correcciones documentadas (1 dato inventado corregido en RF-2, 1 contradicción aclarada en Alcance y 1 ambigüedad/frase vaga precisada en RNF-1).
