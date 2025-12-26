Desafío – Like Me (Parte I)
Autor

Celeste Nicole Lluen Delgado

Descripción

Este proyecto corresponde al Desafío – Like Me (Parte I), cuyo objetivo es desarrollar un servidor backend utilizando Express.js que permita gestionar publicaciones de una red social, almacenando la información en una base de datos PostgreSQL.

El servidor expone rutas HTTP que permiten consultar y registrar publicaciones, utilizando el paquete pg para la interacción con la base de datos y habilitando CORS para permitir la comunicación con la aplicación cliente proporcionada como apoyo en el desafío.

Tecnologías utilizadas:

Node.js v16

Express.js

PostgreSQL

pg

cors

JavaScript

Estructura del proyecto: 

Like_Me_Celeste_Lluen/
├── index.js
├── db.js
├── package.json
└── README.md

Requisitos previos

Node.js versión 16 o superior

PostgreSQL instalado y en ejecución

Base de datos likeme creada con la tabla posts

CREATE DATABASE likeme;

CREATE TABLE posts (
  id SERIAL PRIMARY KEY,
  titulo VARCHAR(25),
  img VARCHAR(1000),
  descripcion VARCHAR(255),
  likes INT
);

Instalación

Desde la terminal, ubicada en la carpeta del proyecto, ejecutar:

npm install

Ejecución

Para levantar el servidor, ejecutar:

npm start


El servidor se inicia en el puerto 3000:

http://localhost:3000

Rutas disponibles
GET /posts

Devuelve todos los registros almacenados en la tabla posts de la base de datos PostgreSQL en formato JSON.

POST /posts

Recibe los datos de una publicación y los almacena en la base de datos.

Ejemplo de body enviado en formato JSON:

{
  "titulo": "Publicación de ejemplo",
  "img": "https://url-de-imagen.com",
  "descripcion": "Descripción del post"
}


El campo likes se inicializa automáticamente en cero.

Funcionamiento general

El servidor se conecta a PostgreSQL mediante un pool de conexiones configurado con el paquete pg.

Se habilita CORS para permitir el consumo de las rutas desde la aplicación cliente de apoyo.

Las consultas a la base de datos se realizan utilizando sentencias SQL parametrizadas.

El proyecto se enfoca exclusivamente en el desarrollo backend, tal como lo indica el enunciado del desafío.

Conclusión

El proyecto cumple con todos los requerimientos del Desafío – Like Me (Parte I), implementando correctamente un servidor Express, la conexión e interacción con PostgreSQL mediante el paquete pg, la habilitación de CORS y la creación de rutas GET y POST para la gestión de publicaciones.
