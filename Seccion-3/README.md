# Seccion 3: Introduction to Back Web Development

## What happens when we access a webpage

El cliente, en este caso, el navegador, envia una solicitud (request) al servidor donde está alojada la página web, y el servidor enviará una respuesta (response), proceso denominado request-response model o arquitectura cliente-servidor.

### URL

Cada URL se divide en 3 partes importantes:

-  HTTP o HTTPS: Protocolo usado para la conexión 

- Dominio: Nombre de identificación. Normalmente se suele obtener un nombre di stinto a la dirección real del servidor al que estamos accediendo. Para convertir el nombre de domnio a la dirección, se usa un DNS.

- DNS: Domain Name Server, el navegador realiza una solicitud a un DNS y este servidor hará coincidir la dirección web que se ingresó al navegador con la dirección IP del servidor. 


- Recurso: Donde se va a acceder en el domio.

### TCP/IP socket connection

Conexion con el cliente y el servidor. 
TCP es el protocolo de control de transmisión (Transmition Control Protocol) e IP es el protocolo de internet (Internet Protocol) .

Permiten definir como viajan los datos a través de la web.

El trabajo de TCP es dividir las solicitudes y respuestas en pequeños fragmentos (packets). EL protocolo IP es enviar y enrutar estos packets en internet a las direcciones IP. 

### HTTP Request

HTTP = Hypertext Transfer Protocol, este protocolo permite que el cliente y el servidor se comuniquen mediante request and responses. 

> GET, POST, DELETE, PUT, PATCH

Sintaxis de HTTP request:

```
    1. Start line: HTTP method + request target + HTTP version

    2. HTTP request headers

    3. Request body (cuando mandamos información al servidor ex: POST)

```

### HTTP y HTTPS

La diferencia de estos protocolo es es que HTTPS está encriptado usando TLS o SSL. 

### HTTP Response 

Sintaxis de HTTP response:

```
    1. Start line: HTTP version + status code + status message

    2. HTTP request headers

    3. Request body (cuando mandamos información al servidor)

```


### Front-end and Back-end

- Frontend: Todo lo que sucede en el navegador web, diseñar y construir el sitio web final que será visible apra el usuario.

1. Stack tecnológico: HTML, CSS, JavaScript.

2. Otras tecnologías: React, Angular, Redux o GraphSQL

- Backend: Donde se alojan diferentes logicas para la implementación de diferentes informaciones que interactuan entre ellos. Asi como los HTTP protocolos, archivos y apps, y las mismas pueden interactuar con la base de datos.

1. Stack tecnologico: Node.js y Mongo.db

2. Otras tecnologías: PosgresSQL, MySQL, Python, PHP.

### Static VS Dinamic Vs API

- Static website: Archivos estáticos como HTML, CSS y JavaScript son lanzados al navegador y este los renderizará, pero no tienen conexion con alguna lógica backend. 

- Dynamic Website: Contienen bases de datos, y un entorno/aplicación de ejecución como Node.js, obteniendo los datos de la base de datos, generando una plantilla que contiene la renderización de la conexion, proyectandolo con HTML, CSS Y JavaScript, para finalmente renderizar en el navegador.

> Este proceso se denomina server-side rendering, la diferencia es que los datos no seran estaticos ya que las logicas e informaciones de acuerdo a l a base de datos.

- API: Aplication Programming Interface. Contiene una base datos, un entorno de desarrollo que obtiene datos de la base de datos cada que el cliente hace una solicitud. Solo que acá, solo enviamos datos, en la mayoria en formato JSON. Pieza que permite la comunicación de información.

Al construir sitios web, normalmente se construye la API y luego se consume.

