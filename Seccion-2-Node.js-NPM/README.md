# Seccion 2 Node.js NPM DOCUMENTACIÓN

- Documentación acerca de la sección 2 Node.js -> Introducción a Node.js y NPM (Node Package Manager).

## What Is Node.js and Why Use It?

 Node.js es un entorno de ejecución de código JavaScript del lado del servidor. Una de sus características más destacadas es su enfoque en la asincronía y la no bloqueante, lo que lo convierte en una herramienta ideal para aplicaciones en tiempo real y de alta concurrencia.

Node.js está construido en el motor V8 JavaScript de Google. Se podría considerar un contenedor para ejecturar JavaScript fuera del navegador.

Podemos usar Node.js para un servidor web, podemos usar JavaScript en la parte del servidor (back-end) para construccion de aplicaciones web y construirlas rapido y facilmente escalables, ya que su modelo se basa en un solo hilo, pudiendo hacer API's, Streaming Data, aplicaciones web en el lado del servidor, etc. 

> Node.js cuenta con una libreria open-source para instalar dependencias y funcionalidades llamada NPM.


## Modules on Node.js

Node.js se basa en el concepto de módulos, que son unidades independientes de código que se pueden reutilizar. Estos módulos pueden ser partes internas de Node.js o componentes creados por los desarrolladores para cumplir funciones específicas.

## File System Module

Uno de los módulos más esenciales es el módulo "fs" (File System o Sistema de Archivos). Proporciona métodos para interactuar con archivos y directorios en el sistema. Esto incluye la capacidad de crear, leer, escribir, actualizar y eliminar archivos, así como trabajar con directorios y manejar rutas de archivo.


```
const fs = require('fs');

const textIn= fs.readFileSync('./txt/input.txt', 'utf-8')
console.log(textIn);

const textOut = `This is what we know about the avocado: ${textIn}.\nCreated on ${Date.now()}`;
fs.writeFileSync('./txt/output.txt', textOut);

```

## HTTP Module

El módulo "http" permite la creación de servidores web y la gestión de solicitudes y respuestas HTTP. Esencial para construir aplicaciones web y APIs, este módulo permite definir cómo responder a las solicitudes entrantes y cómo manejar las rutas.

Usando el http module, usaremos lo que se creará en el servidor y luego su petición

```
const http = require('http');

const server = http.createServer((req, res) => {
    res.writeHead(200, {
        'Content-Type': 'text/html'
    });
    res.end(console.log('Server on'));
}
```
Petición:

```
const http = require('http');

server.listen(8020, '127.0.0.1', () => {
    console.log(`Listening on port 8020`);
});

```



## URL Module

El módulo "url" se utiliza para analizar y manipular direcciones URL. Proporciona herramientas para desglosar una URL en sus partes componentes, como protocolo, host y parámetros de consulta. Esto resulta útil para interpretar las solicitudes entrantes y trabajar con los elementos de una URL.

```
const url = require('url');

const server = http.createServer((req, res) => {
    const pathName = url.parse(req.url, true);
    console.log(pathName);
}
```

## Callbacks and async functions

Node.js se destaca por su naturaleza asincrónica. En lugar de ejecutar operaciones en secuencia, Node.js permite que múltiples operaciones se ejecuten al mismo tiempo, lo que es fundamental para la escalabilidad y la eficiencia. Esto se logra mediante el uso de callbacks, que son funciones que se pasan como argumentos y se ejecutan cuando se completa una operación asincrónica.

### Callback hell

El callback Hell se produce cuando encadenamos muchas operaciones asíncronas seguidas.
```
/* fs.readFileSync('./txt/start.txt', 'utf-8', (err, data1)=> {
    fs.readFile(`${data1}.txt`, 'utf-8', (err, data2) => {
        fs.readFile(`./txt/append.txt`, 'utf-8', (err, data3)=>{
            fs.writeFile(`./txt/final.txt`, `${data2} ${data3}`, 'utf-8', (err) => {
                if (err) throw err;
                console.log('Your file has been saved')
            });
        });
    });
});
```

## NPM (Node Package Manager)

NPM (Node Package Manager) es una herramienta crucial en el ecosistema de Node.js. Permite a los desarrolladores descargar, instalar y gestionar paquetes de código reutilizable. Los paquetes son bibliotecas de software que contienen funciones y utilidades listas para usar en proyectos Node.js. NPM simplifica la integración de estos paquetes y sus dependencias, acelerando el proceso de desarrollo y fomentando la colaboración.

Node.js es una plataforma que se basa en módulos para organizar el código. Su enfoque en la asincronía y la programación no bloqueante lo hace idóneo para aplicaciones en tiempo real y de alto rendimiento. NPM agiliza la administración de paquetes de terceros, fomentando la eficiencia y la reutilización de código.

