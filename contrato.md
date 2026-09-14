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


### Declaración de uso de IA
- **Herramienta(s):** Gemini (Antigravity IDE)
- **Nivel de uso:** Nivel 2–3 (borrador / revisor)
- **Qué se le pidió:** Se le pidió formatear el mini-contrato, explicar y corregir el error de TypeScript al usar una interfaz en un método decorado ("A type referenced in a decorated signature..."), agregar los decoradores `@ApiOkResponse` para la documentación en Swagger y añadir comentarios TSDoc.
- **Qué se modificó/verificó manualmente:** Se verificó que el cambio a `import type` solucionara el error del compilador, se comprobó visualmente en el editor que los TSDocs funcionaran correctamente, se revisó que Swagger UI reflejara los schemas en `/api/docs`, y se gestionó la exclusión de node_modules en Git.
