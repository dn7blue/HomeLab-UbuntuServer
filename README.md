# HomeLab-UbuntuServer

Despliegue de servicios y gestión de volúmenes con Docker Compose en Linux

Siguiendo con las prácticas en mi Home Lab, he configurado un servicio en Docker sobre Linux para trabajar la gestión de contenedores y la persistencia de datos.

El objetivo del laboratorio ha sido desplegar el servicio desde un archivo de configuración (`docker-compose.yml`) y asegurarme de que los datos y la configuración se guarden en el sistema anfitrión, evitando que se pierdan al reiniciar o eliminar el contenedor.

🔹 Puntos clave del laboratorio:

* **Despliegue automatizado:** Configuración del servicio en un archivo `docker-compose.yml` para levantar toda la infraestructura con un solo comando (`docker compose up -d`).
* **Persistencia de datos (Bind Mounts):** Mapeo de carpetas locales (`./datos/config` y `./datos/peliculas`) hacia las rutas del contenedor (`/config` y `/data/movies`) para que los cambios queden guardados en el disco local.
* **Seguridad y permisos:** Asignación de un usuario sin privilegios de root (`user: "1000:1000"`) para evitar problemas de seguridad y gestionar los permisos del sistema de archivos correctamente, junto al mapeo de puertos (`8096:8096`).
* **Verificación:** Comprobación del estado del contenedor desde la terminal con `docker ps`, verificando que el servicio está activo (`healthy`) y comprobando las rutas desde el panel de administración.
