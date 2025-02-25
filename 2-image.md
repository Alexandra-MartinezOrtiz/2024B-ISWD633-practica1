# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](img/imagen.PNG)


## ¿Cuál es la relación entre una imagen y un contenedor? 

La relación entre una imagen y un contenedor se refiere a cómo la imagen se ajusta, escala y posiciona dentro de un elemento que la contiene. El contenedor define el tamaño, el posicionamiento y el ajuste de la imagen mediante propiedades CSS como width, height, object-fit, y puede influir en la visualización de la imagen en diferentes dispositivos o resoluciones.
![Imagen y contenedores](img/imagenContenedores.JPG)
## Comandos para imágenes

### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**

```
docker pull hello-world
```

**¿Qué es nginx?**

Nginx es un servidor web y proxy inverso de código abierto, conocido por su alto rendimiento y capacidad para manejar muchas conexiones simultáneas. Se utiliza para servir contenido estático, actuar como proxy entre clientes y servidores de aplicaciones, realizar balanceo de carga, y mejorar la seguridad con funciones como limitación de solicitudes y protección contra DDoS. Es ampliamente usado en sitios de alto tráfico por su eficiencia y estabilidad.

Descargar la imagen  **nginx** en la versión **alpine**

```
docker pull nginx:alpine
```

### Listar imágenes

```
docker images
```

![image](https://github.com/user-attachments/assets/c3341bc3-7df6-4078-8303-b16a8d8bcfec)


**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen

El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 

```
docker inspect hello-world
docker inspect hello-world:latest
```


**¿Con qué algoritmo se está generando el ID de la imagen?**

Se genera utilizando el algoritmo de hash SHA-256.

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 

```
docker rmi hello-world:latest
```

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

