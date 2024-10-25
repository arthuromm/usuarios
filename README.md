API de Gestión de Ventas
Este proyecto es una API para la gestión de ventas construida con Node.js, Express, y Firebase Firestore como base de datos. La API permite realizar operaciones CRUD (Crear, Leer, Actualizar y Eliminar) en las ventas registradas, así como cambiar el estado de las mismas entre "pendiente", "vendido" y "cancelado".

Características
Crear ventas con datos como cantidad, producto, usuario, fecha y hora.
Obtener todas las ventas registradas en la base de datos.
Buscar una venta por ID.
Actualizar el estado de una venta a "vendido" o "cancelado".
Cancelar una venta actualizando su estado.
Guardar la fecha y hora de forma automática como un Timestamp de Firestore.
Tecnologías Utilizadas
Node.js: Entorno de ejecución para JavaScript del lado del servidor.
Express: Framework minimalista para la creación de servidores en Node.js.
Firebase Firestore: Base de datos NoSQL de Google utilizada para almacenar las ventas.
Firebase Admin SDK: Herramienta para gestionar Firestore desde un servidor.
Instalación
Sigue estos pasos para configurar el proyecto en tu entorno local:

Clona el repositorio:


git clone https://github.com/tuusuario/tu-repositorio.git
Navega al directorio del proyecto:


cd tu-repositorio
Instala las dependencias necesarias:


npm install
Configura Firebase:

Crea un proyecto en Firebase.
Descarga el archivo de configuración serviceAccountKey.json para Firebase Admin SDK y colócalo en el directorio raíz del proyecto.
Configura la conexión a Firestore en conexion.js.
Inicia el servidor:

npm run dev
El servidor estará disponible en http://localhost:3000.

Endpoints de la API
Crear una nueva venta
URL: /vent/nuevaVenta

Método: POST

Descripción: Crea una nueva venta con los datos proporcionados. La fecha y hora se generan automáticamente.

Parámetros (en el body o como query params):

Parámetro	Tipo	Descripción
cantidad	Number	Cantidad del producto vendido
id_producto	String	ID del producto
id_usuario	String	ID del usuario
status	String	Estado inicial (opcional)
Ejemplo:


POST /vent/nuevaVenta?cantidad=3&id_producto=abc123&id_usuario=xyz456&status=pendiente
Obtener todas las ventas
URL: /vent/
Método: GET
Descripción: Recupera una lista de todas las ventas registradas.
Buscar una venta por ID
URL: /vent/buscarPorId/:id

Método: GET

Descripción: Recupera los detalles de una venta específica por su ID.

Parámetros:

Parámetro	Tipo	Descripción
id	String	ID de la venta a buscar
Ejemplo:

GET /vent/buscarPorId/Cc0Lb2cCoN163nnVBM6b
Cancelar una venta
URL: /vent/cancelarVenta/:id

Método: PUT

Descripción: Cambia el estado de una venta a "cancelado".

Parámetros:

Parámetro	Tipo	Descripción
id	String	ID de la venta a cancelar
Ejemplo:

PUT /vent/cancelarVenta/Cc0Lb2cCoN163nnVBM6b
Marcar una venta como vendida
URL: /vent/marcarComoVendida/:id

Método: PUT

Descripción: Cambia el estado de una venta a "vendido".

Parámetros:

Parámetro	Tipo	Descripción
id	String	ID de la venta a actualizar
Ejemplo:

PUT /vent/marcarComoVendida/Cc0Lb2cCoN163nnVBM6b
Estructura del Proyecto

/proyecto
│
├── /bd
│   └── ventasBD.js         # Lógica de la base de datos para ventas
│
├── /rutas
│   └── rutasVentas.js      # Definición de rutas para las ventas
│
├── index.js                # Configuración del servidor
├── conexion.js             # Conexión a Firestore
├── package.json            # Información del proyecto y dependencias
└── README.md               # Documentación del proyecto
Consideraciones
Asegúrate de tener configuradas las reglas de Firestore para permitir la lectura/escritura adecuada según tu entorno.
Usa herramientas como Postman o Insomnia para probar los endpoints.
Contribuciones
¡Las contribuciones son bienvenidas! Por favor, sigue estos pasos para contribuir:

Haz un fork del proyecto.

Crea una rama para tu función:

git checkout -b nueva-funcion
Realiza los cambios y haz commit:

git commit -m "Añadida nueva función X"
Sube los cambios a tu fork:

git push origin nueva-funcion
Abre un Pull Request en el repositorio original.

Licencia
Este proyecto está bajo la Licencia MIT. Consulta el archivo LICENSE para obtener más detalles.
