# Imagen

Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.

![Imagen](img/imagen.PNG)

## ¿Cuál es la relación entre una imagen y un contenedor?

- #### **_La relación que se puede tener entre estas definiciones o funciones que tienen estos elementos es primero, la pertenencia de librerías, dependencias, programas, configuraciones, y mas elementos los cuales permiten que las imágenes se puedan desplegar en diferentes entornos misma efectividad o con la condición de que tengan los mismos resultados y para funcionar mismas configuraciones y especificaciones._**
  > #### Diferenciando que un contenedor esta dentro de una imagen y una vez cumplida su misión puede desaparecer.

---

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

> ## Descargar la imagen **hello-world**

- # docker pull hello-world

## **¿Qué es nginx?**

- #### **_Es un servidor web de código abierto que se utiliza principalmente para servir contenido web estático y dinámico._**
- **_Es conocido por su alto rendimiento, bajo uso de recursos y capacidad de manejar grandes cantidades de conexiones concurrentes, lo que lo convierte en una opción muy utilizada para proyectos a gran escala como sitios web, aplicaciones web, y APIs._**

> ### Descargar la imagen **nginx** en la versión **alpine**

- ### docker pull nginx:alpine

### Listar imágenes

```
docker images
```

# COLOCAR UNA CAPTURA DE PANTALLA DEL RESULTADO

![alt text](Imagenes_Screen.png)

**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran.

### Inspeccionar una imagen

El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red. Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world

- # docker inspect hello-world

**¿Con qué algoritmo se está generando el ID de la imagen?**

- #### **_El ID de la imagen en Docker se genera utilizando el algoritmo SHA-256._**
- **_Este algoritmo es un hash criptográfico que produce una cadena de 256 bits (64 caracteres hexadecimales)._**

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

- ## **docker rmi hello-world**

> Untagged: hello-world:latest
> Deleted: sha256:91fb4b041da273d5a3273b6d587d62d518300a6ad268b28628f74997b93171b2.

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```
