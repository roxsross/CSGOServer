# Cómo instalar servidor de CS:GO en Linux (Ubuntu 18.04)

_En este caso usaré Ubuntu 18.04 Server_

## Comenzando 🚀

_Para poder comenzar lo que tendreis que hacer es descargaros [Ubuntu Server](https://www.ubuntu.com/download/server/thank-you?version=18.04.2&architecture=amd64). En este tutorial voy a seguir las instrucciones que podemos encontrar en [LGSM](https://linuxgsm.com/lgsm/csgoserver/)._

## Pre-requisitos 📋

* 2 Cores
* 2 GB de RAM
* 60 GB 

## Instalación 🔧

_A continuación vamos a ver los pasos que tenemos que seguir para realizar una correcta instalación del servidor._

_**Primer paso:** Instalar los programas necesarios para iniciar el servidor_

```
sudo dpkg --add-architecture i386; sudo apt update; sudo apt install mailutils postfix curl wget file bzip2 gzip unzip bsdmainutils python util-linux ca-certificates binutils bc jq tmux lib32gcc1 libstdc++6 libstdc++6:i386
```

_**Segundo paso:** Crearemos un usuario para la gestión del servidor, ya que no podemos iniciarlo con "sudo"_

```
adduser csgoserver
```

_**Tercer paso:** Nos loguearemos con el usuario que acabamos de crear_

```
su - csgoserver
```

_**Cuarto paso:** Descarga el instalador_

```
wget -O linuxgsm.sh https://linuxgsm.sh && chmod +x linuxgsm.sh && bash linuxgsm.sh csgoserver
```

_**Quinto paso:** Ejecuta el instalador, recuerda que NO puedes ejecutarlo como "sudo" y este se encuentra en la raiz del usuario "csgoserver"_

```
./csgoserver install
```

_Una vez acabado este proceso, tendrás que añadir un [Steam Game Server Login Token (GSLT)](https://steamcommunity.com/dev/managegameservers)_

![](imagenes/gslt.gif)


## Ejecutando las pruebas ⚙️
_Para saber si tu servidor se está ejecutando correctamente o te da algún fallo que no sabes solucionar puedes poner lo siguiente._
```
./csgoserver debug
```
_Ahí te dirá que es lo que está fallando. Si tienes algún otro problema, no dudes en comentarlo._


## Gestionar tu servidor ✔️

_Para INICIAR tu servidor simplemente tendrás que poner:_
```
./csgoserver start
```

_Para PARAR tu servidor simplemente tendrás que poner:_
```
./csgoserver stop
```

_Para REINICIAR tu servidor simplemente tendrás que poner:_
```
./csgoserver restart
```

_Para ver si tu servidor se está ejecutando pon:_
```
./csgoserver details
```
_Ahí podrás ver la contraseña y la RCON de tu servidor (si la has puesto), los puertos y la IP que usa, y mucha más información

## Construido con 🛠️

* [Ubuntu](https://www.ubuntu.com/download/server/thank-you?version=18.04.2&architecture=amd64)
* [LGSM](https://linuxgsm.com/lgsm/csgoserver/)
