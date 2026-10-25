```markdown
# Clasificación del reporte de incidente

## Categoría principal

**Incidente de seguridad — Acceso no autorizado a cuenta (posible compromiso de credenciales)**

## Subcategoría

**Phishing / Ingeniería social / Cuenta de correo comprometida** (por confirmar)

## Nivel de severidad

**MEDIA** (potencialmente ALTA si se confirma el acceso)

| Criterio | Evaluación |
|---|---|
| Confidencialidad | Posible exposición de correo y contactos |
| Integridad | Riesgo de envío de correos maliciosos desde la cuenta |
| Disponibilidad | No afectada aparentemente |
| Alcance | Cuenta individual (podría escalar si hay reutilización de contraseña) |

## Indicadores clave en el reporte

- ✅ **Aviso "raro"** recibido → posible alerta de inicio de sesión o correo de phishing
- ⚠️ **Desconoce la fecha del acceso** → ventana de exposición indeterminada
- ✅ **Ya cambió la contraseña** → contención parcial ya realizada por el usuario
- ❓ **No menciona MFA** → factor de riesgo importante
- ❓ **No indica si usaba la misma contraseña en otros servicios**

## Clasificación según tipo de reporte

- **Origen:** Usuario final (no técnico)
- **Canal:** Probablemente mesa de ayuda / correo de soporte
- **Urgencia:** Media-alta (requiere verificación pronta, pero el usuario ya contuvo parcialmente)

## Acciones recomendadas de triage

1. **Verificar** en logs de acceso del proveedor (IPs, dispositivos, ubicaciones, fechas).
2. **Confirmar** si el "aviso raro" era legítimo del proveedor o un phishing.
3. **Revisar** reglas de reenvío automático, firmas y respuestas automáticas creadas.
4. **Habilitar MFA** si no está activo.
5. **Indagar** reutilización de contraseña en otros servicios.
6. **Revisar** actividad de envío (posible uso para spam/phishing a contactos).
7. **Clasificar formalmente** como incidente y abrir ticket con seguimiento.

## Etiquetas sugeridas

`#account-takeover` `#credential-compromise` `#phishing-suspected` `#email-security` `#user-report` `#medium-severity`

> **Nota:** La clasificación es preliminar; debe confirmarse tras revisar los logs de acceso y la naturaleza del "aviso raro". Si se confirma acceso desde IP desconocida, escalar a **ALTA**.
```

Puedes copiar todo el bloque anterior (sin las triples comillas invertidas que lo delimitan) y pegarlo directamente en un archivo `.md` en tu repositorio de GitHub.


# Clasificación del incidente

- **Tipo:** Posible acceso no autorizado a una cuenta de correo electrónico.
- **Severidad:** Media (provisional).
- **Estado:** En investigación.
- **Prioridad:** Alta.
- **Impacto:** Posible pérdida de confidencialidad de la información.
- **Datos faltantes:** Fecha del incidente, origen del acceso y evidencia de actividad sospechosa.

## Acciones recomendadas

1. Cerrar las sesiones activas en todos los dispositivos.
2. Activar la autenticación de dos factores.
3. Revisar los accesos recientes y los dispositivos conectados.
4. Verificar que no existan reglas de reenvío o cambios desconocidos en la cuenta.
5. Reportar el incidente al área de soporte o seguridad informática.

## Justificación

Aunque la persona ya cambió su contraseña, es necesario verificar que el acceso no autorizado haya sido detenido y que la cuenta sea segura.

```markdown
# Clasificación de incidente: sospecha de acceso no autorizado al correo

## Reporte original

> Hola, creo que alguien entró a mi correo porque me llegó un aviso raro. No sé desde cuándo. Ya cambié la contraseña. ¿Qué hago?

## Clasificación

| Campo | Valor |
|-------|-------|
| **Tipo** | Incidente de seguridad: sospecha de acceso no autorizado a una cuenta de correo (compromiso de cuenta) |
| **Estado** | Sospechado, no confirmado. Falta verificar si el aviso es legítimo o phishing |
| **Severidad** | Media-alta |
| **Prioridad** | Alta (atender hoy) |
| **Contención** | Parcial |

**Justificación de la severidad:** el correo suele ser la llave para restablecer contraseñas de otros servicios (banco, redes sociales, compras), por lo que el impacto potencial es mayor que el de la cuenta en sí.

**Justificación de la contención:** cambiar la contraseña no basta si hay sesiones abiertas, reglas de reenvío o una contraseña reutilizada.

## Datos que faltan

- [ ] Qué decía el aviso y quién lo envió
- [ ] Desde cuándo ocurre
- [ ] Si usa verificación en dos pasos
- [ ] Si reutiliza esa contraseña en otros sitios
- [ ] Si notó correos enviados, borrados o reglas que no creó

## Acciones recomendadas

1. **Revisar el aviso sin hacer clic en enlaces.** Si viene de Google, Microsoft u otro proveedor, entrar directamente desde la app o el sitio oficial, no desde el correo.
2. **Cerrar todas las sesiones activas** en la configuración de seguridad de la cuenta.
3. **Activar la verificación en dos pasos**, de preferencia con app de autenticación o llave de seguridad en lugar de SMS.
4. **Revisar la actividad reciente de inicio de sesión:** dispositivos, ubicaciones y horarios desconocidos.
5. **Revisar reglas de reenvío o filtros, direcciones de recuperación y teléfonos asociados**, y eliminar los que no reconozca.
6. **Cambiar la contraseña en otros servicios** donde use la misma, y revisar sobre todo banco y redes sociales.
7. **Avisar a sus contactos** si se enviaron correos sospechosos desde su cuenta.
