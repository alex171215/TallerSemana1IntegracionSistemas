# Contrato CRUD de /productos

| Operación | Verbo | URI | Éxito / Error |
| :--- | :--- | :--- | :--- |
| **Listar** | `GET` | `/api/v1/productos` | 200 |
| **Obtener uno** | `GET` | `/api/v1/productos/{id}` | 200 / 404 |
| **Crear** | `POST` | `/api/v1/productos` | 201 + Location |
| **Reemplazar** | `PUT` | `/api/v1/productos/{id}` | 204 |
| **Actualizar parcial** | `PATCH` | `/api/v1/productos/{id}` | 200 |
| **Eliminar** | `DELETE` | `/api/v1/productos/{id}` | 204 / 404 |


## Bitácora

**¿Qué le falta a tu Swagger para que otro equipo (frontend) la use sin haber visto tu código?**
1. **Modelos Reutilizables (DTOs/Entities):** Actualmente definimos el esquema de la respuesta "inline" directo en el controlador. Lo ideal es definir clases (como `ProductoDto`) y documentarlas con `@ApiProperty()` para que Swagger genere modelos reutilizables.
2. **Códigos de error documentados:** Faltan documentar todos los posibles errores de negocio y validación (ej. `400 Bad Request` si se enviaran datos inválidos).
3. **Autenticación/Seguridad:** Si la API estuviera protegida, faltaría configurar e indicar cómo enviar el token en Swagger (ej. `@ApiBearerAuth()`).
4. **Ejemplos en peticiones:** Para endpoints de creación (POST) faltaría el ejemplo del `body` esperado.


### Declaración de uso de IA
- **Herramienta(s):** Gemini (Antigravity IDE)
- **Nivel de uso:** Nivel 2–3 (borrador / revisor)
- **Qué se le pidió:** Se le pidió estructurar el contrato CRUD, explicar y resolver errores de TypeScript (importaciones faltantes y `import type`), generar el esqueleto de un nuevo endpoint de búsqueda con validaciones (`class-validator`), y explicar conceptualmente el código de estado 204 en Postman.
- **Qué se modificó/verificó manualmente:** Se verificó que las importaciones agregadas resolvieran los errores de compilación, se probaron los endpoints CRUD en Swagger/Postman, se adaptó el código del esqueleto del nuevo endpoint en el controlador, y se comprobó que el comportamiento de los códigos de estado coincidiera con las explicaciones.
