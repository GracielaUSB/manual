===========
Instalación
===========

-----
Linux
-----

Para instalar Graciela en Debian o en distribuciones de Linux 
derivadas de Debian (Ubuntu, Mint, Elementary, etc.):
  
- Descargar el paquete deb más reciente para la distribución (:code:`debian` o :code:`ubuntu`) y la arquitectura que corresponda a tu computador (:code:`i386` o :code:`amd64`) en https://github.com/GracielaUSB/graciela-debian/releases.
- Ejecutar el archivo descargado.

-----
macOS
-----

Para instalar Graciela en macOS es necesario cumplir los 
siguientes requisitos:

- **Command Line Tools** o **Xcode**. Se puede descargar Xcode (alrededor de 4GB) desde https://developer.apple.com/downloads o sólo los comandos necesarios desde la terminal usando el comando::

    $ xcode-select --install

- **Homebrew**. En caso de no tener Homebrew, puede instalarse siguiendo las instrucciones en http://brew.sh.

Una vez cumplidos los requisitos, se puede instalar Graciela con los siguientes comandos::

    $ brew tap GracielaUSB/graciela
    $ brew install graciela
