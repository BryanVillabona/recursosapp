# 📚 Mis Recursos App

  

Aplicación orientada a registrar y gestionar el progreso personal de los usuarios al consumir contenido como **series, películas y libros**. Este proyecto se desarrolla como parte de un taller académico enfocado en bases de datos **No Relacionales utilizando MongoDB**.

  

---

  

## 📌 Descripción General

  

Esta aplicación permite a los usuarios:

  

- Añadir nuevos recursos (películas, series o libros).

- Registrar el estado de avance de cada recurso (pendiente, en progreso o terminado).

- Realizar reseñas y calificar los recursos.

- Filtrar recursos por formato, plataforma y estado.

- Buscar recursos por nombre.

  

Este repositorio contiene **la estructura y datos necesarios para poblar una base de datos MongoDB**, así como los comandos y archivos necesarios para importar las colecciones.

  

---

  

## 🗂️ Estructura del Repositorio

  

```bash

📁  MisRecursosApp/

│

├──  📄  README.md  ←  Documentación  principal  del  proyecto.

├──  📄  estados.json  ←  Datos  para  la  colección  `estados`.

├──  📄  formatos.json  ←  Datos  para  la  colección  `formatos`.

├──  📄  generos.json  ←  Datos  para  la  colección  `generos`.

├──  📄  plataformas.json  ←  Datos  para  la  colección  `plataformas`.

├──  📄  recursos.json  ←  Datos  para  la  colección  `recursos` (principal).

├──  📄  usuarios.json  ←  Datos  para  la  colección  `usuarios` (principal).

├──  📄  progreso.json  ←  Documento  de  ejemplo  para  `progreso`.

├──  📄  progreso_completado.json←  Datos  completos  para  la  colección  `progreso` (principal).

```

  

---

  

## 📚 Colecciones en MongoDB

| Colección | Archivo JSON | Descripción |
|---|---|---|
| `estados` | `estados.json` | Estados del recurso: pendiente, en progreso, terminado. |
| `formatos` | `formatos.json` | Tipo de recurso: libro, película, serie. |
| `generos` | `generos.json` | Género del recurso: acción, drama, comedia, etc. |
| `plataformas` | `plataformas.json` | Plataforma en la que se accede al recurso. |
| `recursos` | `recursos.json` | Recursos registrados por los usuarios. **(colección principal)** |
| `usuarios` | `usuarios.json` | Usuarios registrados. **(colección principal)** |
| `progreso` | `progreso_completado.json` | Registro del avance de los usuarios. **(colección principal)** |

---

  

## 🛠️ Comandos para crear la base de datos en MongoDB

  

Sigue estos pasos para importar las colecciones desde los archivos `.json`:

  

### 1. Crear la base de datos

  

```js

use  misRecursosDB

```

  

### 2. Crear e importar cada colección (desde terminal)

  

```bash

mongoimport  --db  misRecursosDB  --collection  estados  --file  estados.json  --jsonArray

mongoimport  --db  misRecursosDB  --collection  formatos  --file  formatos.json  --jsonArray

mongoimport  --db  misRecursosDB  --collection  generos  --file  generos.json  --jsonArray

mongoimport  --db  misRecursosDB  --collection  plataformas  --file  plataformas.json  --jsonArray

mongoimport  --db  misRecursosDB  --collection  recursos  --file  recursos.json  --jsonArray

mongoimport  --db  misRecursosDB  --collection  usuarios  --file  usuarios.json  --jsonArray

mongoimport  --db  misRecursosDB  --collection  progreso  --file  progreso.json  --jsonArray

```

  

> 📝 Asegúrate de ejecutar estos comandos desde la carpeta donde están los archivos `.json`.

---

  

## 💡 Consideraciones Adicionales

  

- Las colecciones `estados`, `formatos`, `generos` y `plataformas` se consideran auxiliares.

- La colección `progreso` conecta usuarios con recursos, permitiendo el seguimiento detallado de su avance.

- Los identificadores de cada documento son compatibles con MongoDB (`$oid`).

- Los datos fueron generados siguiendo una lógica coherente entre plataformas, formatos y géneros.

  

---

  


## 📌 Autores

| Nombre del Integrante | GitHub |
|---|---|
| Sergio Lievano | [@sergiosteven66](https://github.com/sergiosteven66)|
| Bryan Villabona | [@BryanVillabona](https://github.com/BryanVillabona)|

  

---