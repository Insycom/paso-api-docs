# Autenticación y permisos

La API utiliza una clave Bearer individual:

```http
Authorization: Bearer TU_CLAVE
```

La clave queda asociada a un único tenant, usuario emisor, permiso de lectura o escritura y vencimiento. PASO almacena solamente su hash. Revocarla, desactivar al usuario o cambiar sus permisos impide nuevas solicitudes.

Una clave nunca concede permisos superiores a los del usuario que la creó. En cada solicitud se validan tenant, rol, alcance y licencia vigente. No se debe enviar la clave como parámetro de URL ni compartirla entre ambientes.

Las claves de sandbox y producción son diferentes. Una credencial de sandbox no funciona en producción.
