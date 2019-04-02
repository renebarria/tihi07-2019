# tihi07-2019

La siguiente será una guía de instalación de la maquina virtual (virtualbox) e instalación de sistema operativo (centos7), Nosotros usaremos la versión 6.0.4 disponible para windows de 64-bits.


Cabe destacar que esta guía está siendo creada con fines didacticos realizados en nuestra maquina personal

El primer paso será descargar e instalar virtualbox
VirtualBox(6.0.4): https://www.virtualbox.org/wiki/Downloads

Una vez que ya tenemos instalada virtualbox descargaremos la versión minima de CentOS-7
CentOS-7(versión minima): http://isoredirect.centos.org/centos/7/isos/x86_64/CentOS-7-x86_64-Minimal-1810.iso

Cuando ya hayamos descargado CentOS-7 procederemos a descargar el software putty e instalarlo respectivamente
putty(versión 0.71): https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html

Luego abriremos el software de virtualbox y seleccionaremos la opción "nuevo", allí asignaremos un espacio de memoria RAM de 4096mb

A continuación crearemos un disco virtual (VDI VirtualBox Disk Image) de 15GB

Una vez que finalize el proceso procederemos a iniciar e instalar CentOS-7

En la siguiente ventana seleccionaremos el lenguaje en el cual iremos a trabajar, en este caso, English (United States) y presionaremos "Continuar"

Si todo va correctamente el programa nos pedirá que seleccionemos el destino de la instalación, el cual será nuestro disco de 15GB creado previamente y en la esquina superior izquierda presionaremos "Done"

Para finalizar en la esquina inferior derecha presionaremos "Begin Installation" para comenzar la instalación

Teniendo en cuenta de que nadie mas accederá a nuestra maquina crearemos una root password la cual para este caso será "root"
Luego crearemos un usuario el cual tendrá como username "user" y contraseña "user" y para finalizar haremos click en "reboot"

Una vez que termine de reiniciar accederemos con nuestro usuario y contraseña (user)

En la consola escribiremos el comando "su -" y nuestra contraseña "root", seguido de el comando "ifup enp0s3" mostrandonos el siguiente mensaje

Luego escribiremos "ip a" lo cual nos mostrará esta IP

Despues iremos a nuestra ventana de virtualbox y seleccionando OS iremos a configuración, iremos a la pestaña de red y haremos click en avanzadas y haremos click en "Reenvio de puertos"

Allí agregaremos la siguiente regla de envios
	IP anfitrion: 127.0.0.1 (Nuestra IP local)
	Puerto anfitrion: 8001 (Puerto inutilizado)
	IP invitado: 10.0.2.15 (IP en la consola CentOS-7)
	Puerto invitado: 22 (Puerto estandar)

Despues abriremos putty donde agregaremos la siguiente IP "127.0.0.1" con puerto "8001"

Si todo ha ido bien nos debería abrir la siguiente ventana donde entraremos con nuestro usuario y contraseña "user"

Luego habilitaremos SSH a traves de nuestra consola

Para instalar el servidor y cliente OpenSSH escribiremos "yum -y install openssh-server openssh-clients" en la consola

habilitar al comenzar "chkconfig sshd on"

reiniciar SSHD "service sshd restart"

Ahora pasaremos a instalar java 8 jdk

En la consola escribiremos el comando cd ~

Luego escribiremos lo siguiente:
wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "https://download.oracle.com/otn-pub/java/jdk/8u201-b09/42970487e3af4f5aa5bca3f542482c60/jdk-8u201-linux-x64.rpm"












Referencias
virtualbox(versión 6.0.4): https://www.virtualbox.org/wiki/Downloads
CentOS7(versión minima): http://isoredirect.centos.org/centos/7/isos/x86_64/CentOS-7-x86_64-Minimal-1810.iso
putty(versión 0.71): https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html


Para mas información
SSH: https://medium.com/@taufiq_ibrahim/enable-ssh-on-centos-fresh-install-25329569c120



