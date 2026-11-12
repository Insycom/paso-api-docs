# Errores, concurrencia e idempotencia

| Estado | Significado |
|---|---|
| `400` | Solicitud inválida. |
| `401` | Credencial ausente, inválida, vencida o revocada. |
| `402` | Licencia del tenant no disponible. |
| `403` | Permiso o tenant no autorizado. |
| `404` | Recurso inexistente o fuera del alcance. |
| `409` | Conflicto de versión, estado, saldo o idempotencia. |
| `422` | Validación de campos. |
| `429` | Límite de solicitudes. |
| `503` | Servicio temporalmente no disponible. |

El detalle se devuelve en `detail`. Los cambios utilizan la `version` leída: ante `409`, volvé a consultar el registro y revisá los cambios antes de reintentar.

Las operaciones y acciones documentales requieren una `Idempotency-Key` de 8 a 120 caracteres. Reutilizá la misma clave únicamente para repetir exactamente la misma intención y cuerpo. Para una operación nueva, generá otra clave.
