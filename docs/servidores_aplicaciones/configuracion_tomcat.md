# Configuración de Tomcat

Habrás podido ver que en el apartado anterior hemos explicado cómo instalar y configurar Tomcat, así como también cómo arrancarlo y pararlo. En este apartado vamos a ver cómo configurar Tomcat para que pueda ejecutar aplicaciones web basadas en Java.

Tomcat tiene diferentes ficheros de configuración que permiten personalizar su comportamiento y adaptarlo a las necesidades de cada aplicación web. Algunos de estos ficheros son:

* **server.xml**: Es el fichero principal de configuración de Tomcat, donde se definen los conectores, los hosts virtuales y otros parámetros de configuración del servidor de aplicaciones.

* **tomcat-users.xml**: Es el fichero de configuración de usuarios y roles de Tomcat, donde se definen los usuarios y roles que pueden acceder a la administración del servidor de aplicaciones.

Vamos a ver cómo configurar Tomcat para que pueda ejecutar aplicaciones web basadas en Java. Para ello, vamos a utilizar el fichero `server.xml` y el fichero `tomcat-users.xml`.

## Configuración del fichero server.xml

El fichero `server.xml` se encuentra en el directorio `conf` dentro del directorio de Tomcat. Este fichero contiene la configuración principal del servidor de aplicaciones, incluyendo los conectores, los hosts virtuales y otros parámetros de configuración.

Este fichero está estructurado en formato XML y contiene diferentes elementos y atributos que permiten personalizar el comportamiento de Tomcat. Algunos de los elementos más importantes son:

* **<Server>**: Es el elemento raíz del fichero `server.xml`, que contiene la configuración global del servidor de aplicaciones.

* **<Service>**: Es el elemento que define un servicio de Tomcat, que puede contener uno o más conectores y un motor de procesamiento de solicitudes.

* **<Connector>**: Es el elemento que define un conector de Tomcat, que permite recibir solicitudes HTTP o HTTPS desde los clientes y enviarlas al motor de procesamiento de solicitudes.

* **<Engine>**: Es el elemento que define el motor de procesamiento de solicitudes de Tomcat, que se encarga de procesar las solicitudes recibidas por los conectores y generar las respuestas correspondientes.

* **<Host>**: Es el elemento que define un host virtual de Tomcat, que permite alojar múltiples aplicaciones web en el mismo servidor de aplicaciones.

Alguno de los fragmentos que podemos encontrar son:

```xml
<Server port="8005" shutdown="SHUTDOWN">
  <Service name="Catalina">
    <Connector port="8080" protocol="HTTP/1.1"
               connectionTimeout="20000"
               redirectPort="8443" />
    <Engine name="Catalina" defaultHost="localhost">
      <Host name="localhost"  appBase="webapps"            unpackWARs="true" autoDeploy="true">
        <Valve className="org.apache.catalina.valves.AccessLogValve" directory="logs"
               prefix="localhost_access_log" suffix=".txt"
               pattern="%h %l %u %t &quot;%r&quot; %s %b" />
      </Host>
    </Engine>
  </Service>
</Server>
``` 

En este fragmento, se define un conector HTTP en el puerto 8080, un motor de procesamiento de solicitudes llamado "Catalina" y un host virtual llamado "localhost" que aloja las aplicaciones web en el directorio "webapps".

Este fichero se puede modificar para cambiar el puerto de escucha del conector, habilitar HTTPS, configurar la autenticación de usuarios y roles, entre otras opciones de configuración.

## Configuración del fichero tomcat-users.xml

Este fichero se encuentra en el directorio `conf` dentro del directorio de Tomcat. Este fichero contiene la configuración de usuarios y roles de Tomcat, incluyendo los usuarios que pueden acceder a la administración del servidor de aplicaciones.

Vamos a ver un ejemplo de cómo configurar este fichero para crear un usuario administrador que pueda acceder a la administración de Tomcat:

```xml
<tomcat-users>
  <role rolename="admin-gui"/>
  <user username="admin" password="admin" roles="manager-gui,admin-gui"/>
</tomcat-users>
```

Vemos en este fragmento que se definen dos roles: "manager-gui" y "admin-gui", y un usuario llamado "admin" con la contraseña "admin" que tiene ambos roles asignados.

Es importante cambiar la contraseña del usuario administrador por una más segura antes de desplegar aplicaciones web en un entorno de producción. Por ejemplo , podemos cambiar la contraseña del usuario administrador a "admin123" de la siguiente manera:

```xml
<tomcat-users>
  <role rolename="admin-gui"/>
  <user username="admin" password="admin123" roles="manager-gui,admin-gui"/>
</tomcat-users>
```

!!! note
    Para poder acceder a la administración de Tomcat, debemos de asociar a un usuario el rol `manager-gui` y el rol `admin-gui`. Esto permitirá al usuario acceder a la interfaz de administración de Tomcat y gestionar las aplicaciones web desplegadas en el servidor de aplicaciones.