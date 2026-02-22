# Proyecto: API de Gestión de Servicios - Exámenes de Laboratorio Clínico

**Estudiante:** Carolina Martínez Mesa  
**Base URL:** `https://6987733c8bacd1d773ed6319.mockapi.io/servicio`

---

## 1. Modelo de Datos

El recurso `servicio` está definido con la siguiente estructura de datos:

```json
{
  "NombreExamen": "alanina aminotransferasa",
  "abreviatura": "ALT",
  "Precio": 10000,
  "Parametros": {
    "lectura": "450",
    "maxcon": "500"
  },
  "urgencia": ["leve", "normal", "alta"],
  "remitido": false,
  "id": "1"
}

```

## 2. Bitácora de Operaciones CRUD (Respuestas de Postman)
### A. Obtener todos los registros (GET)
Status Code: `200 OK`


Respuesta de Postman:
```json
[
  {
    "NombreExamen": "alanina aminotransferasa",
    "abreviatura": "ALT",
    "Precio": 10000,
    "Parametros": {
      "lectura": "450",
      "maxcon": "500"
    },
    "urgencia": ["leve", "normal", "alta"],
    "remitido": false,
    "id": "1"
  },
  {
    "NombreExamen": "creatinina",
    "abreviatura": "cr",
    "Precio": 15000,
    "Parametros": {
      "lectura": "450",
      "maxcon": "500"
    },
    "urgencia": ["leve", "normal", "alta"],
    "remitido": true,
    "id": "2"
  }
]
```

### B. Crear un nuevo registro

Método: POST
Endpoint: /servicio
Status Code: `201 Created`

Cuerpo enviado en Postman:
```json
{
  "NombreExamen": "NombreExamen 3",
  "abreviatura": "abreviatura 3",
  "Precio": 73,
  "Parametros": {},
  "urgencia": [],
  "remitido": false
}
```
Respuesta de postman:
```json
{
  "NombreExamen": "NombreExamen 3",
  "abreviatura": "abreviatura 3",
  "Precio": 73,
  "Parametros": {},
  "urgencia": [],
  "remitido": false,
  "id": "3"
}
```

### C. Consulta de registro individual (GET)
Método: GET
Endpoint: /servicio/3

Status Code: `200 OK`

Respuesta de Postman:
```json
{
  "NombreExamen": "NombreExamen 3",
  "abreviatura": "abreviatura 3",
  "Precio": 73,
  "Parametros": {},
  "urgencia": [],
  "remitido": false,
  "id": "3"
}
```
### D. Actualización de un registro (PUT)

Status Code: `200 OK`

Modificación: Se actualizó la abreviatura y el precio del registro con ID 3.

Respuesta de Postman:
```json
{
  "NombreExamen": "NombreExamen 3",
  "abreviatura": "ggt",
  "Precio": 12000,
  "Parametros": {},
  "urgencia": [],
  "remitido": false,
  "id": "3"
}
```
### E. Eliminación de un registro (DELETE)
Status Code: `200 OK`

Respuesta de Postman:
```json
{
  "NombreExamen": "creatinina",
  "abreviatura": "cr",
  "Precio": 15000,
  "Parametros": {
    "lectura": "450",
    "maxcon": "500"
  },
  "urgencia": ["leve", "normal", "alta"],
  "remitido": true,
  "id": "2"
}
```
### F. Validación de Recurso Inexistente (GET 404)
Status Code: `404 Not Found`

Respuesta de Postman:
```json
"Not found"
```
## 3. Resumen de Endpoints y Códigos HTTP

| Acción              | Método | Endpoint     | Código HTTP   |
| ------------------- | ------ | -----------  | ------------- |
| Obtener todos       | GET    | `/servicio`  | 200 OK        |
| Crear               | POST   | `/servicio`  | 201 Created   |
| Consultar registro  | GET    | `/servicio/3`| 200 OK        |
| Actualizar registro | PUT    | `/servicio/3`| 200 OK        |
| Eliminar registro   | DELETE | `/servicio/2`| 200 OK        |
| Recurso inexistente | GET    | `/servicio/2`| 404 Not Found |


