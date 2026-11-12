# Ejemplos

## Consultar el catálogo

```bash
curl 'https://api.demo.paso.sys.ar/api/v1/recursos' \
  -H 'Authorization: Bearer TU_CLAVE'
```

## Listar clientes

```bash
curl 'https://api.demo.paso.sys.ar/api/v1/datos/clientes?q=ejemplo&limite=50&offset=0' \
  -H 'Authorization: Bearer TU_CLAVE'
```

## Crear un cliente

```bash
curl -X POST 'https://api.demo.paso.sys.ar/api/v1/datos/clientes' \
  -H 'Authorization: Bearer TU_CLAVE' \
  -H 'Content-Type: application/json' \
  -d '{"datos":{"codigo":"CLI-001","nombre":"Cliente de ejemplo","pais":"Argentina"}}'
```

Antes de escribir, consultá `/recursos`: los campos y referencias disponibles pueden evolucionar. Los identificadores de los ejemplos son ficticios.
