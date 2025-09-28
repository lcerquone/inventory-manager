Inventory Manager
Un sistema de gestión de inventario full-stack construido con Node.js, Express, PostgreSQL y React. La aplicación proporciona una interfaz limpia y moderna para realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) sobre una base de datos de productos.

➤ Descripción
Esta aplicación es una solución completa para la gestión de inventarios. Permite a los usuarios visualizar un dashboard con estadísticas clave, añadir nuevos productos, editar los existentes y eliminarlos. La interfaz es dinámica y responsiva, gracias a React y Tailwind CSS, y se comunica con un backend robusto que gestiona la lógica de negocio y la persistencia de datos en una base de datos PostgreSQL.

✨ Características
Dashboard Interactivo: Muestra estadísticas clave como el número total de productos, la cantidad total de artículos, el número de categorías y el valor total del inventario.

Gestión Completa de Productos (CRUD):

Crear: Añade nuevos productos a través de un formulario modal.

Leer: Visualiza todos los productos en una cuadrícula de tarjetas.

Actualizar: Edita la información de cualquier producto existente.

Eliminar: Borra productos de la base de datos con una confirmación.

Búsqueda y Filtrado:

Busca productos por nombre o descripción.

Filtra la vista de productos por categoría.

Diseño Responsivo: La interfaz se adapta a diferentes tamaños de pantalla, desde móviles hasta escritorios.

API RESTful: Backend bien definido que separa la lógica del frontend.

🛠️ Tecnologías Utilizadas
Backend:

Node.js: Entorno de ejecución de JavaScript.

Express.js: Framework para construir la API RESTful.

PostgreSQL: Base de datos relacional para el almacenamiento de datos.

node-postgres (pg): Cliente de PostgreSQL para Node.js.

dotenv: Para la gestión de variables de entorno.

Frontend:

React: Biblioteca para construir la interfaz de usuario.

ReactDOM: Para renderizar los componentes de React en el DOM.

JavaScript (ES6+): Con fetch para las llamadas a la API.

Estilos:

Tailwind CSS: Framework de CSS para un diseño rápido y moderno.

Font Awesome: Para los iconos.

🚀 Cómo Empezar
Sigue estos pasos para configurar y ejecutar el proyecto en tu máquina local.

Prerrequisitos
Node.js y npm: Descargar e instalar.

PostgreSQL: Tener una instancia de base de datos PostgreSQL en ejecución (localmente o en un servicio como AWS RDS).

1. Clonar el Repositorio
git clone [https://URL-DE-TU-REPOSITORIO.git](https://URL-DE-TU-REPOSITORIO.git)
cd nombre-del-directorio

2. Configuración del Backend
Instalar Dependencias:
En la raíz del proyecto, ejecuta el siguiente comando para instalar los paquetes necesarios para el servidor.

npm install express pg dotenv cors

Configurar Variables de Entorno:
Crea un archivo llamado .env en la raíz del proyecto y añade las credenciales de tu base de datos.

# .env
DB_HOST='localhost'
DB_PORT=5432
DB_USER='tu_usuario_postgres'
DB_PASSWORD='tu_contraseña_segura'
DB_DATABASE='inventory_db'

Crear la Base de Datos:
Asegúrate de que la base de datos (inventory_db en el ejemplo) exista en tu instancia de PostgreSQL. El servidor creará la tabla products e insertará datos de ejemplo la primera vez que se ejecute.

3. Configuración del Frontend
El frontend está diseñado para ser servido directamente por el backend de Express.

Crear la Carpeta public:
En la raíz del proyecto, crea una carpeta llamada public.

Mover Archivos del Frontend:
Coloca tu archivo de React (vamos a llamarlo app.js) dentro de la carpeta public.

Crear el Archivo index.html:
Dentro de la carpeta public, crea un archivo index.html con el siguiente contenido. Este archivo cargará React, Tailwind CSS, Font Awesome y tu código de la aplicación.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inventory Manager</title>
    <!-- Tailwind CSS -->
    <script src="[https://cdn.tailwindcss.com](https://cdn.tailwindcss.com)"></script>
    <!-- Font Awesome (para iconos) -->
    <link rel="stylesheet" href="[https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css](https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css)">
    <!-- React -->
    <script src="[https://unpkg.com/react@17/umd/react.development.js](https://unpkg.com/react@17/umd/react.development.js)" crossorigin></script>
    <script src="[https://unpkg.com/react-dom@17/umd/react-dom.development.js](https://unpkg.com/react-dom@17/umd/react-dom.development.js)" crossorigin></script>
    <!-- Babel (para compilar JSX en el navegador) -->
    <script src="[https://unpkg.com/@babel/standalone/babel.min.js](https://unpkg.com/@babel/standalone/babel.min.js)"></script>
</head>
<body class="bg-gray-100">
    <div id="root"></div>

    <!-- Tu código de React -->
    <script type="text/babel" src="app.js"></script>
</body>
</html>

Importante: Nota que la etiqueta <script> para app.js tiene el atributo type="text/babel". Esto es necesario para que el navegador pueda interpretar la sintaxis JSX de React sin un paso de compilación.

4. Iniciar la Aplicación
Ejecutar el Servidor:
Abre tu terminal en la raíz del proyecto y ejecuta:

node server.js

El servidor se iniciará, generalmente en el puerto 80 o el que hayas configurado.

Abrir en el Navegador:
Abre tu navegador web y ve a http://localhost. ¡Deberías ver la aplicación de inventario en funcionamiento!

📂 Estructura del Proyecto
/inventory-manager
├── public/
│   ├── app.js          # Lógica del frontend en React
│   └── index.html      # Punto de entrada HTML
├── .env                # Variables de entorno (NO subir a Git)
├── package.json
├── README.md           # Este archivo
└── server.js           # Lógica del backend (Express y API)

📖 API Endpoints
La API RESTful proporciona los siguientes endpoints:

Método

Ruta

Descripción

GET

/api/products

Obtiene una lista de todos los productos.

GET

/api/products/:id

Obtiene un producto específico por su ID.

POST

/api/products

Crea un nuevo producto.

PUT

/api/products/:id

Actualiza un producto existente.

DELETE

/api/products/:id

Elimina un producto.

GET

/api/stats

Obtiene las estadísticas del dashboard.
