# AYGO lab security
## Descripción

El objetivo de este taller es crear una api rest segura usando como framework
spring y las utilidades que este provee para construir una api que cuente
con caracteristicas de autenticación y autorización, usando auth0 como
servidor de autenticacion.

## Pre-requisitos
* [Maven](https://maven.apache.org/) - Administrador de dependencias
* [Git](https://git-scm.com/) - Sistema de control de versiones
* [Java 11](https://www.java.com/) - Tecnología para el desarrollo de aplicaciones
* [Spring](https://spring.io/) - Framework para el desarrollo de aplicaciones
* [Auth0](https://www.java.com/) - Servicio de autenticacion en aplicaciones



## Instrucciones de construcción y ejecución

1. **Construir la aplicación**: Desde la raíz del proyecto compilar la aplicación

``mvn clean install``

2. **Ejecutar la aplicación**

**Java:** Para ejecutar la aplicación localmente se debe ejecutar el siguiente comando:

``java -cp "target/classes:target/dependency/*" com.example.menu.MenuApplication``



## Componentes de la solucion

La solucion compone una api rest para el manejo de items en un
restaurante ofreciendo los diferentes servicios CRUD.

Dicha api puede ser utilizada desde una [aplicacion demo web ](https://dashboard.whatabyte.app/menu), 
donde se cuenta con dos componentes de seguridad:

* Acceso basado en autenticacion: Si estas autenticado puedes acceder a recursos.
* Acceso based en permisos: Si estas autorizado y autenticado, puedes realizar operaciones sobre recursos.

Cubriendo de esta manera los casos de uso mas comunes para tener una api segura.

## Pruebas

Primeramente se realizan las configuraciones respectivas en auth0 como
en la app web demo para soportar los modulos de autenticacion que se crearon.
![conf auth0.png](img%2Fconf%20auth0.png)
![conf sec api.png](img%2Fconf%20sec%20api.png)

Ahora se tendra un servicio de autenticación usando Auth0 como
servidor de autenticación.
![login.png](img%2Flogin.png)

Estando logueado se podra observar a recursos pero no modificarlos.
![autho view simple.png](img%2Fautho%20view%20simple.png)

Si se intenta acceder a recursos sin estar autenticados obtendremos un error 401.
![401 auth.png](img%2F401%20auth.png)

Ahora se añadira autorización mediante roles a la api.
![authorization conf.png](img%2Fauthorization%20conf.png)

Ingresando como un usuario con permisos ya podremos realizar operaciones sobre los recursos asegurados.
![admin 1.png](img%2Fadmin%201.png)

Al realizar una operacion de moficacion sobre los recursos esta es exitosa.
![admin3.png](img%2Fadmin3.png)

Si se realiza una operacion de modificacion con un usuario que no tenga permisos se obtiene una respuesta 403.
![admin2.png](img%2Fadmin2.png)

