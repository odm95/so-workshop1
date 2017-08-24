# Taller 1

**Nombre:** Óscar Daniel Molano  

**Código:** A00267576

## Descripción

En este taller se profundizó en conocer la estructura de los directorios del sistema operativo Linux-CentOS. Se investigó comandos distintos a los vistos durante la clase, enrriqueciendo el conocimiento para movernos en el mundo de Linux.

## Soluciones

### 1.

Explique la función de los directorios en la raíz de sistema operativo Linux-CentOS. Proporcione ejemplos de los archivos que se encuentran en cada directorio (explique al menos un archivo por directorio).

| Directorio   | Archivo ejemplo | Descripción del contenido del directorio  |
|------|------|------|
| /bin | cd | Almacena la mayoría de los programas esenciales del sistema. |
| /boot | vmlinuz-0-rescue-fae4cec556514973b73cc8be86c219a0.x86_64 | Archivos estáticos utilizados por el cargador de arranque(boot-loader) del sistema. |
| /dev | network_latency | Contiene archivos especiales del sistema, conocidos como controladores de dispositivo (device drivers), los cuales se usan para acceder a los dispositivos del sistema y recursos, como discos duros, modems, memoria, etc. |
| /etc | smb.conf | Este directorio está reservado para los ficheros de configuración y arranque del sistema Linux. En este directorio no debe aparecer ningún fichero binario (programas). |
| /home | operativos | Contiene los directorios personales (casas) de los usuarios. En un sistema recién instalado, no habrá ningún usuario en este directorio. |
| /lib | sendmail.postfix | Estos ficheros contienen código que compartirán muchos programas. En lugar de que cada programa contenga una copia propia de las rutinas compartidas, éstas son guardadas en este fichero. Esto hace que los programas ejecutables sean menores y reduce el espacio usado en disco. |
| /mnt | ---- | Punto de montaje. Montar temporalmente otros sistemas de archivos. |
| /opt | ---- | Aplicaciones adicionales |
| /proc | kpagecount | Contiene Archivos especiales que o bien reciben o envían información al kernel del sistema. Información asociada con el núcleo que se está ejecutando, para obtener información de recursos utilizados en el sistema (CPU, memoria, swap, dispositivos..) Este directorio es un sistema de archivo virtual, es decir, no existe físicamente en el disco duro, sólo en memoria. |
| /root | anaconda-ks.cfg | Directorio hogar (casa) del administrador del sistema. |
| /sbin | fsck.ext4 | Contiene programas esenciales del sistema, que son únicamente accesibles al administrador (root). |
| /tmp  | yum.log | Archivos temporales del sistema. |
| /usr  | tmp |  Éste es uno de los directorios más importantes del sistema puesto que contiene los datos, programas y librerías de uso común para todos los usuarios |
| /var  | logs del sistema cuando se presentan errores | Este directorio contiene información temporal de los programas (lo cual no implica que se pueda borrar su contenido) |


### 2.

En una tabla como se muestra a continuación escriba 10 comandos de Linux no visto en clase. Puede incluir comandos que funcionan una vez han sido instalados con yum

| Comando   | Usuario | Descripción   |
|------|------|------|
| dmidecode -q | Cualquier usuario | Mostrar los componentes (hardware) del sistema. |
| find /home/user1 -name \*.bin | Cualquier usuario | Buscar ficheros con extensión ‘. bin’ dentro del directorio ‘/ home/user1’. |
| df -h | Cualquier usuario | Mostrar los componentes (hardware) del sistema. |
| chage -E 2011-12-31 user1 | root | Colocar un plazo para la contraseña del usuario. En este caso dice que la clave expira el 31 de diciembre de 2011.. |
| bunzip2 file1.bz2 | Cualquier usuario | Descomprime in fichero llamado ‘file1.bz2’. |
| yum localinstall package_name.rpm | root y usuarios con permiso de instalación de paquetes | Este instalará un RPM y tratará de resolver todas las dependencies para ti, usando tus repositorios. |
| dump -0aj -f /tmp/home0.bak /home | Cualquier usuario | hacer una salva completa del directorio ‘/home’. |
| fdformat -n /dev/fd0 | root | Formatear un disco flooply. |
| ifconfig eth0 192.168.1.1 netmask 255.255.255.0 | root | Configurar una dirección IP. |
| strace -c ls >/dev/null | root | Mostrar las llamadas del sistema hechas y recibidas por un proceso. |

### 3.

¿Cuál es la utilidad del comando printenv en Linux?, Investigue acerca de la creación de variables de ambiente en Linux y como hacerlas permanentes. Cree una variable de ambiente, hágala permanente y muestre evidencias del funcionamiento.

printenv: Imprime en forma de listado las variables de ambiente (nombre y valor asignado) configuradas en el sistema.

### Declaración de variables de entorno

A continuación se realizará el proceso de creación y verificación de variable de entorno creada por nosotros mismos:

[root@localhost ~]# prueba="prueba_variable_entorno"  

[root@localhost ~]# export prueba  

[root@localhost ~]# printenv  

XDG_SESSION_ID=17  

HOSTNAME=localhost.localdomain  

SELINUX_ROLE_REQUESTED=  

TERM=xterm  

SHELL=/bin/bash  

HISTSIZE=1000  

SSH_CLIENT=192.168.0.13 54985 22  

SELINUX_USE_CURRENT_RANGE=  

SSH_TTY=/dev/pts/1  

USER=root  

LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=01;05;37;41:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.Z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.jpg=01;35:*.jpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.axv=01;35:*.anx=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=01;36:*.au=01;36:*.flac=01;36:*.mid=01;36:*.midi=01;36:*.mka=01;36:*.mp3=01;36:*.mpc=01;36:*.ogg=01;36:*.ra=01;36:*.wav=01;36:*.axa=01;36:*.oga=01;36:*.spx=01;36:*.xspf=01;36:  

MAIL=/var/spool/mail/root  

PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/root/bin  

PWD=/root  

LANG=es_CO.UTF-8  

SELINUX_LEVEL_REQUESTED=  

HISTCONTROL=ignoredups  

SHLVL=1  

HOME=/root  

**prueba=prueba_variable_entorno**  

LOGNAME=root  

SSH_CONNECTION=192.168.0.13 54985 192.168.0.17 22  

LESSOPEN=||/usr/bin/lesspipe.sh %s  

XDG_RUNTIME_DIR=/run/user/0  

_=/usr/bin/printenv  


Podemos observar que al ejecutar el comando printenv nuestra nueva variable de entorno se encuentra en el listado.  


## Referencias

https://github.com/ICESI/so-commands/tree/master/centos7
http://docencia.udea.edu.co/cci/linux/dia4/directorio.htm
http://www.mancera.org/2011/06/26/%C2%BFque-contiene-cada-carpeta-de-linux/
https://blog.desdelinux.net/mas-de-400-comandos-para-gnulinux-que-deberias-conocer/
https://www.comoinstalarlinux.com/comandos-linux/comandos-linux-de-la-a-a-la-z/
https://hablemoslinux.wordpress.com/2012/04/15/las-variables-de-entorno-y-el-comando-export/

