# test_lar
Primer teste de laravel
Pasos de instalación
1- Descargar e instalar
1.1- Composer (Nos permitira instalar librerias que necesitemos)
1.2- Git bash (Terminal)
1.3- Xampp (Servidor)
1.4- Visual studio Code (Editor de texto)

2-Ya todo instalado crear la carpeta para los proyectos en C://Xampp/htdocs/"ej-apps"
Dentro de la carpeta creada (ej-apps) se guardaran los proyectos creados

3- Para crear nuestro primer proyecto hacemos clic derecho sobre "ej-apps" y clic sobre Git Bash here
En la terminal escribimos
composer create-project laravel/laravel teste2 (nombre del proyecto) enter y ahi descarga lo necesario y crea el proyecto
Para ver el proyecto escribimos ls enter
Para acceder al proyecto  cd teste2/

4- Para verlo desde el servidor (Xampp) abrimos Xampp Control Panel
Presionar Start apache para iniciar el servidor
Presionar Admin para abrir el localhost en el navegador
En el navegador borrar dashboard y reemplazar por el nombre de la carpeta que creamos en el punto 2
Ej: http://localhost/ej-apps
Nos debe abrir la carpeta con el nombre de nuestro proyecto creado en el punto 3
Tambien podemos ingresar directo a al contenido de la carpeta agregando al link /nombre del proyecto
Ej: http://localhost/ej-apps/teste2 
Al hacer esto nos abre las carpetas de nuestro proyecto, debemos ir a la carpeta public y nos debe abrir la pagina principal de nuestro proyecto
Ej: http://localhost/ej-apps/teste2/public

5- Para abrir nuestra aplicacion en el editor de texto 1.4 Visual Studio Code, volvemos a git bash y escribimos code . y enter
Nos debe abrir nuestro proyecto con todas sus carpetas para poder editarlas

6- Crear un host virtual (Modifical el link http://localhost/ej-apps/teste2/public)
6.1- Ir a la carpeta xampp luego apache luego config luego extra (C:\xampp\apache\conf\extra) y modificaremos el archivo "httpd-vhosts.conf" (clic derecho abrir con bloc)
Dentro del archivo, ir abajo y buscar el siguiente contenido
##<VirtualHost *:80>
    ##ServerAdmin webmaster@dummy-host2.example.com
    ##DocumentRoot "C:/xampp/htdocs/dummy-host2.example.com"
    ##ServerName dummy-host2.example.com
    ##ErrorLog "logs/dummy-host2.example.com-error.log"
    ##CustomLog "logs/dummy-host2.example.com-access.log" common
##</VirtualHost>
Copiar todo el contenido y pegar abajo
Los ## son etiquetas de comentarios, asi que eliminaremos las etiquetas y eliminaremos las lineas de texto que no vamos a utilizar
Solo dejaremos las lineas DocumentRoot y ServerName
En DocumentRoot escribimos la ubicacion de nuestro proyecto en el disco C - Xampp - Htdocs - nombre del punto 2 - nombre del punto 3 - public (pagina a mostrar)
En ServerName escribimos el nombre de dominio que queremos utilizar (link)
Ej: Quedaria asi
<VirtualHost *:80>
    DocumentRoot "C:/xampp/htdocs/laravel-apps/teste2/public"
    ServerName segundoteste.com
</VirtualHost>

Luego copiamos este contenido y lo pegamos debajo y reemplazamos los valores dejandolo con los valores por defecto como localhost
Ej: quedaria asi
<VirtualHost *:80>
    DocumentRoot "C:/xampp/htdocs/"
    ServerName localhost
</VirtualHost>
Guardar y cerrar
6.2- Ahora modificaremos el siguiente archivo
Abrir el bloc de notas como administrador 
Clic en archivo y abrir para buscar un archivo llamado host ubicado en C:\Windows\System32\drivers\etc
Abajo a la derecha clic en todos los archivos para que nos aparezcan los archivos que no sean .txt
Clic sobre el archivo host y abrir
Al final del archivo escribir
127.0.0.1 localhost
127.0.0.1 segundoteste.com (nombre del dominio que elegimos en el punto 6.1)
Guardar y cerrar
Reiniciar apache y listo, nuestro proyecto nos debe abrir en el nevegador con nuestro dominio, en este caso segundoteste.com (6.1)
Si deseamos crear mas dominios para otros proyectos repetir los mismos pasos agregando los nuevos dominios en los 2 archivos que modificamos

