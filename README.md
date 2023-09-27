# TALLER DE DE MODULARIZACIÓN CON VIRTUALIZACIÓN E INTRODUCCIÓN A DOCKER

Aplicación web usando el micro-framework de Spark java. Con un container en docker para la aplicación desplegado y configurado localmente y remotamente con DockerHub.

### Prerrequisitos
- Java
- Maven

### Instalación

1. Clonar el repositorio

```
git clone https://github.com/SantiagoBayona/AREP-LAB-05
```

2. Dentro del directorio del proyecto lo construimos

```
mvn package
```

## Ejecución

1. Corremos el servidor en local

```
java -cp "target/classes;target/dependency/*" edu.escuelaing.SparkWebServer
```
## Pruebas

### Localmente

Ingresamos a la página mediante esta URL en un navegador

```
https://localhost:4567
```

![img 1](https://github.com/SantiagoBayona/AREP-LAB-05/assets/64861204/94e37520-7ca6-4e17-a370-858bf942c866)

### Remotamente

Para probar se puede hacer con la imagen de docker desde el repositorio. Para esto corremos el comando

```
docker run -d -p 34000:6000 --name [nombre de la instancia] santiagobayona04/arepbono
```

Al hacerlo vemos que el recurso solicitado carga en el navegador

![bono arep](https://github.com/SantiagoBayona/Bono-AREP/assets/64861204/d498f832-07db-4b2f-9b78-7df81dece4ad)
