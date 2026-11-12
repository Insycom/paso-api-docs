# PASO API

Documentación pública de la API REST de **PASO — Plataforma de Administración y Seguimiento de Operaciones**.

- Producción: `https://api.paso.sys.ar/api/v1`
- Sandbox: `https://api.demo.paso.sys.ar/api/v1`
- Contrato: [`openapi.json`](openapi.json)
- Sitio: [paso.sys.ar](https://paso.sys.ar)

PASO permite integrar viajes, maestros, documentación CRT/MIC-DTA, operaciones internas, gastos e informes. Las capacidades efectivas dependen del tenant, rol, licencia y alcance de la credencial.

## Inicio rápido

Solicitá una credencial de sandbox al equipo de PASO. Nunca publiques la clave ni la incluyas en una URL.

```bash
curl 'https://api.demo.paso.sys.ar/api/v1/datos/clientes?limite=20' \
  -H 'Authorization: Bearer TU_CLAVE'
```

Las escrituras de documentos y operaciones requieren `Idempotency-Key`:

```bash
curl -X POST 'https://api.demo.paso.sys.ar/api/v1/operaciones/comprobantes' \
  -H 'Authorization: Bearer TU_CLAVE' \
  -H 'Content-Type: application/json' \
  -H 'Idempotency-Key: integracion-orden-123' \
  --data @comprobante.json
```

## Guías

- [Autenticación y permisos](docs/autenticacion.md)
- [Sandbox y paso a producción](docs/sandbox.md)
- [Errores, concurrencia e idempotencia](docs/errores.md)
- [Ejemplos](docs/ejemplos.md)

## Alcance

Los comprobantes son internos y no implican emisión fiscal electrónica. La gestión documental no constituye una presentación oficial ante autoridades aduaneras. Las rutas de sesión web, superadministración, secretos y configuración interna no forman parte de este contrato público.

## Soporte

Para solicitar acceso de sandbox o informar un problema, utilizá el canal de contacto publicado en [paso.sys.ar/contacto](https://paso.sys.ar/contacto).

Copyright © INSYCOM. Ver [licencia de la documentación](LICENSE.md).
