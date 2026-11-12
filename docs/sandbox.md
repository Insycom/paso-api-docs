# Sandbox y producción

El sandbox está disponible en `https://api.demo.paso.sys.ar/api/v1` y utiliza datos ficticios. Las credenciales se solicitan al equipo de PASO y pueden tener vencimiento, cuotas y límites de tasa.

Flujo recomendado:

1. Solicitar una credencial individual de sandbox.
2. Consultar `/recursos` y validar el contrato OpenAPI.
3. Implementar reintentos seguros con `Idempotency-Key`.
4. Probar errores, conflictos de versión y revocación.
5. Solicitar habilitación productiva.
6. Cambiar la URL base y utilizar una credencial nueva de producción.

No utilices información real, adjuntos sensibles ni credenciales productivas durante las pruebas.
