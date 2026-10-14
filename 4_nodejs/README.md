# Introduccion a backend

## 1. Servidor como proceso
Conocemos al servidor de dos maneras
    1. Una computadora especializada (tipica de los datacenters)
    2. Un proceso que esta en constante ejecucion (muy parecido al addEventListener)

```js
const contenedorDatos = document.getElementById("contenedor-datos");

// El addEventListener es un proceso en constante ejecucion que esta esperando una accion (o evento) del usuario
contenedorDatos.addEventListener("click", event => {
    console.log(event.target);
})
```

En el caso del servidor, es muy parecido, es un proceso que esta continuamente ejecutandose esperando una PETICION y devolviendo una RESPUESTA. Concretamente:

    - Escuchando peticiones HTTP (HTTP Request)
    - Devolviendo respuestas HTTP (HTTP Response)


---


## Codigos de estado HTTP
Los códigos de estado HTTP son respuestas de tres dígitos que indican el resultado de una solicitud entre un cliente y un servidor, organizados en cinco categorías principales según su primer dígito.

**1xx Informativo**: El servidor recibió la solicitud y continúa el proceso (ej. **100 Continue**).

**2xx Éxito**: La solicitud fue recibida, comprendida y aceptada correctamente.
*   **200 OK**: Éxito estándar.
*   **201 Created**: Recurso creado exitosamente.
*   **204 No Content**: Éxito sin contenido en la respuesta.

**3xx Redirección**: Se requiere una acción adicional para completar la solicitud, generalmente una redirección.
*   **301 Moved Permanently**: Redirección permanente.
*   **302 Found**: Redirección temporal.
*   **304 Not Modified**: El recurso no ha cambiado, usar caché.

**4xx Error del Cliente**: La solicitud contiene sintaxis incorrecta o no puede cumplirse por error del usuario.
*   **400 Bad Request**: Solicitud incorrecta o malformada.
*   **401 Unauthorized**: Se requiere autenticación.
*   **403 Forbidden**: Acceso denegado por permisos.
*   **404 Not Found**: Recurso no encontrado.

**5xx Error del Servidor**: El servidor falló al procesar una solicitud aparentemente válida.
*   **500 Internal Server Error**: Error genérico del servidor.
*   **502 Bad Gateway**: Puerta de enlace o proxy inválido.
*   **503 Service Unavailable**: Servicio no disponible (sobrecarga/mantenimiento).