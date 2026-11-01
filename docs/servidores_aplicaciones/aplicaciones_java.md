## Aplicaciones Web basadas en Java

Antes de continuar con los servidores de aplicaciones, es importante comprender cómo se desarrollan y despliegan las aplicaciones web basadas en Java. Estas aplicaciones utilizan tecnologías como Servlets, JSP (JavaServer Pages) y frameworks como Spring o Struts para crear aplicaciones web dinámicas y robustas.

En esta sección, exploraremos los conceptos básicos de las aplicaciones web basadas en Java, su arquitectura y cómo se integran con los servidores de aplicaciones para ofrecer una experiencia completa de despliegue de aplicaciones web.

Hasta ahora, has trabajado en aplicaciones basadas en escritorio ya sea a través de consola, o con interfaces gráficas de usuario (GUI), pero ahora nos centraremos en aplicaciones web, que se ejecutan en un navegador web y permiten a los usuarios interactuar con ellas a través de la web.

## Conceptos básicos de las aplicaciones web basadas en Java

En las aplicaciones web basadas en Java, el punto de entrada es un servlet, que es una clase Java que maneja las solicitudes HTTP y genera respuestas HTTP. Los servlets se ejecutan en un contenedor de servlets, que es parte del servidor de aplicaciones.

!!! info
    Recuerda que las peticiones HTTP son las solicitudes que los clientes (como los navegadores web) envían a los servidores para obtener recursos o realizar acciones. Estas solicitudes pueden ser de diferentes tipos, como GET, POST, PUT, DELETE, entre otros.

Una aplicación web basada en java no tiene un único punto de entrada sino que puede tener múltiples servlets que manejan diferentes tipos de solicitudes y rutas. Cada servlet se encarga de procesar una solicitud específica y generar la respuesta correspondiente.

Además las aplicaciones web basadas en Java pueden utilizar otros protocolos y tecnologías, como WebSockets para comunicación en tiempo real, o RESTful APIs para exponer servicios web que pueden ser consumidos por otros sistemas.


## Arquitectura de aplicaciones web basadas en Java

Vamos a ver como realmente se comporta una aplicación web basada en Java, y cómo se integra con los servidores de aplicaciones para ofrecer una experiencia completa de despliegue de aplicaciones web.

Hay diferentes arquitecturas para las aplicaciones web basadas en Java, pero una de las más comunes es la arquitectura de tres capas, que se compone de:

1. Capa de presentación: Esta capa se encarga de la interacción con el usuario y se implementa utilizando tecnologías como JSP, Servlets y frameworks como Spring MVC o Struts. La capa de presentación genera la interfaz de usuario y maneja las solicitudes del cliente.

2. Capa de negocio: Esta capa contiene la lógica de negocio de la aplicación y se implementa utilizando clases Java y frameworks como Spring o EJB (Enterprise JavaBeans). La capa de negocio procesa las solicitudes del cliente, realiza operaciones y toma decisiones basadas en la lógica de negocio.

3. Capa de datos: Esta capa se encarga de la gestión de los datos y se implementa utilizando tecnologías como JDBC (Java Database Connectivity) o JPA (Java Persistence API). La capa de datos interactúa con bases de datos y otros sistemas de almacenamiento para recuperar y almacenar información.

4. Capa de servicios: Esta capa se encarga de exponer servicios web y APIs que pueden ser consumidos por otros sistemas o aplicaciones. Se implementa utilizando tecnologías como RESTful APIs, SOAP o GraphQL.

!!! info
    Mucha de estas capas se basan en el patrón de diseño MVC (Modelo-Vista-Controlador), que separa la lógica de negocio, la presentación y el control de flujo de la aplicación, facilitando el mantenimiento y la escalabilidad de las aplicaciones web basadas en Java.

## Creación y despliegue de aplicaciones web basadas en Java

Para crear y desplegar aplicaciones web basadas en Java, es necesario seguir una serie de pasos que incluyen:

1. Configuración del entorno de desarrollo: Instalar y configurar un IDE (como Eclipse o IntelliJ IDEA), el JDK (Java Development Kit) y un servidor de aplicaciones (como Apache Tomcat, JBoss, WebLogic o WebSphere).

2. Creación de la aplicación web: Crear un proyecto web en el IDE, definir la estructura del proyecto y desarrollar los servlets, JSPs y clases Java necesarias para implementar la lógica de negocio y la presentación.

3. Configuración del servidor de aplicaciones: Configurar el servidor de aplicaciones para que pueda ejecutar la aplicación web, incluyendo la configuración de puertos, contextos y recursos necesarios.

4. Despliegue de la aplicación web: Empaquetar la aplicación web en un archivo WAR (Web Application Archive) y desplegarlo en el servidor de aplicaciones, ya sea copiando el archivo WAR al directorio de despliegue del servidor o utilizando herramientas de administración del servidor.

5. Pruebas y monitoreo: Probar la aplicación web desplegada para asegurarse de que funciona correctamente y monitorear el rendimiento y la disponibilidad de la aplicación en el servidor de aplicaciones.

Habrás podido ver que hay un apartado donde se empaqueta la aplicación web; este paso es fundamental para establecer nuestra aplicación web y poder desplegarla en un servidor de aplicaciones. El empaquetado de la aplicación web en un archivo permite que el servidor de aplicaciones pueda reconocer y ejecutar la aplicación correctamente.

Existen diferentes métodos para realizar este proceso de empaquetado, dependiendo del IDE y las herramientas utilizadas. 

Podemos utilizar los propios IDEs o utilizar otras herramientas; algunas de estas herramientas son:

* **Maven**: Es una herramienta de gestión de proyectos y construcción de software que permite automatizar el proceso de empaquetado de aplicaciones web basadas en Java. Maven utiliza un archivo de configuración llamado `pom.xml` para definir las dependencias, plugins y configuraciones necesarias para construir y empaquetar la aplicación web en un archivo.

* **Gradle**: Es otra herramienta de construcción de software que permite automatizar el proceso de empaquetado de aplicaciones web basadas en Java. Gradle utiliza un archivo de configuración llamado `build.gradle` para definir las dependencias, plugins y configuraciones necesarias para construir y empaquetar la aplicación web en un archivo.

Por otro lado, habrás podido ver que hemos mencionado un fichero `WAR`este es un archivo que contiene todos los recursos necesarios para ejecutar una aplicación web basada en Java, incluyendo servlets, JSPs, clases Java, archivos de configuración y otros recursos estáticos como imágenes, hojas de estilo y scripts.

Existen diferentes ficheros para trabajar y desplegar aplicaciones web basadas en Java, algunos de estos ficheros son:

* **JAR (Java Archive)**: Es un archivo que contiene clases Java compiladas y otros recursos necesarios para ejecutar una aplicación Java. Los archivos JAR se utilizan para empaquetar bibliotecas, utilidades y aplicaciones Java.

* **WAR (Web Application Archive)**: Es un archivo que contiene todos los recursos necesarios para ejecutar una aplicación web basada en Java, incluyendo servlets, JSPs, clases Java, archivos de configuración y otros recursos estáticos como imágenes, hojas de estilo y scripts. Los archivos WAR se utilizan para desplegar aplicaciones web en servidores de aplicaciones.

* **EAR (Enterprise Archive)**: Es un archivo que contiene uno o más módulos de aplicaciones Java EE, incluyendo aplicaciones web, EJBs y otros recursos necesarios para ejecutar una aplicación empresarial. Los archivos EAR se utilizan para desplegar aplicaciones empresariales en servidores de aplicaciones.

* **RAR (Resource Adapter Archive)**: Es un archivo que contiene los recursos necesarios para integrar una aplicación Java con un sistema externo, como una base de datos o un sistema de mensajería. Los archivos RAR se utilizan para desplegar adaptadores de recursos en servidores de aplicaciones.

A la hora de crear y desplegar aplicaciones web basadas en Java, es importante comprender la estructura y el contenido de estos archivos, así como las herramientas y técnicas necesarias para empaquetarlos y desplegarlos correctamente en un servidor de aplicaciones.

### Ejercicio 1: Creación y despliegue de una aplicación web basada en Java

Vamos a crear una aplicación web basada en Java utilizando Apache Tomcat como servidor de aplicaciones. La aplicación consistirá en un servlet que maneje las solicitudes HTTP y genere respuestas dinámicas.

Necesitaremos un IDE como IntelliJ IDEA, el JDK (Java Development Kit).

Vamos a utilizar el siguiente fichero con la aplicación web basada en Java.

[Descarga de proyecto web basado en Java](../assets/ejercicio1.zip)

Una vez descargado y descomprimido el proyecto, vamos a tratar de generar el fichero war; para posteriormente desplegarlo en el servidor de aplicaciones Apache Tomcat.

Ahora sigue los siguientes pasos:

1. Abre el IDE y abre el proyecto como un proyecto Maven (Lo detectará automáticamente al abrir el proyecto).
2. Observa la estructura del proyecto y familiarízate con los archivos y directorios.
3. Abre el fichero miServlet.java y revisa el código del servlet que maneja las solicitudes HTTP.
4. Abre el fichero web.xml y revisa la configuración del servlet y las rutas de acceso.
5. Abre el fichero pom.xml y revisa las dependencias y configuraciones necesarias para construir y empaquetar la aplicación web en un archivo WAR.
6. Genera el archivo War usando el IDE o utilizando la línea de comandos con Maven.

!!! info
    Para generar el archivo WAR en IntelliJ IDEA, ve a la parte derecha donde verás el icono de Maven y despiega el apartado Lifecycle y haz doble click en el apartado package. Esto generará el archivo WAR en la carpeta target del proyecto.

No borres el proyecto, ya que lo utilizaremos en el siguiente apartado para desplegarlo en el servidor de aplicaciones Apache Tomcat.