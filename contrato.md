# Mini-contrato API

## Endpoint: GET /productos

| Propiedad | Detalles |
| :--- | :--- |
| **Recurso** | `/productos` |
| **Verbo** | `GET` |
| **Respuesta 200 (Éxito)** | Lista de objetos con el formato `{ id, nombre, precio }` |
| **Respuesta de error** | `500 Internal Server Error` (si falla el servidor) |


## Bitácora

**¿Qué le falta a tu Swagger para que otro equipo (frontend) la use sin haber visto tu código?**
1. **Modelos Reutilizables (DTOs/Entities):** Actualmente definimos el esquema de la respuesta "inline" directo en el controlador. Lo ideal es definir clases (como `ProductoDto`) y documentarlas con `@ApiProperty()` para que Swagger genere modelos reutilizables.
2. **Códigos de error documentados:** Faltan documentar todos los posibles errores de negocio y validación (ej. `400 Bad Request` si se enviaran datos inválidos).
3. **Autenticación/Seguridad:** Si la API estuviera protegida, faltaría configurar e indicar cómo enviar el token en Swagger (ej. `@ApiBearerAuth()`).
4. **Ejemplos en peticiones:** Para endpoints de creación (POST) faltaría el ejemplo del `body` esperado.
