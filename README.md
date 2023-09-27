# TALLER DE DE MODULARIZACIÓN CON VIRTUALIZACIÓN E INTRODUCCIÓN A DOCKER

Aplicación web usando el micro-framework de Spark java. Con un container en docker para la aplicación desplegado y configurado localmente y remotamente con DockerHub.

### Prerrequisitos
- Java
- Maven
- Docker

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

Al hacerlo vemos que el recurso solicitado carga en el navegador en el puerto especificado en el comando, 34000 en este caso

![bono arep](https://github.com/SantiagoBayona/Bono-AREP/assets/64861204/d498f832-07db-4b2f-9b78-7df81dece4ad)

## Creación de imagen

Para crear la imagen en docker debemos correr este comando desde la terminal estando en el directorio del proyecto

```
docker build --tag [nombre de la imagen] .
```

![img 2](https://github.com/SantiagoBayona/AREP-LAB-05/assets/64861204/71cc29d8-e87b-4b42-b7be-b972ea1ce01a)

Con la imagen ya creada podemos correrla localmente con este comando

```
docker run -d -p 34000:6000 --name [nombre de la instancia] [nombre de la imagen]
```

O subirla a un repositorio en Dockerhub para ser corrida remotamente con los siguientes comandos

```
docker tag [nombre de la imagen] [usuario en dockerhub]/[nombre del repositorio]
docker login
docker push [usuario en dockerhub]/[nombre del repositorio]:latest
```

## Diseño de clases

Se creó una clase main en la que se definió las peticiones a las que responderá el servidor web spark

![img 3](https://github.com/SantiagoBayona/AREP-LAB-05/assets/64861204/e264131f-d58b-45b3-878b-1000cca8a2d1)

Y un cliente web usando Html y JS

![img 4](https://github.com/SantiagoBayona/AREP-LAB-05/assets/64861204/c907c85c-c1b9-4776-ac2c-2634f2fac5a6)

![img 5](https://github.com/SantiagoBayona/AREP-LAB-05/assets/64861204/555af928-500d-427e-8231-1741494613ef)


## Construido con

* Java
* Maven
* Git
* Docker
