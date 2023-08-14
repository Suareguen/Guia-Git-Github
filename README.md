# Guia-Git-Github

## Windows


### Windows Subsystem Linux
Primero instalamos **Windows Subsystem Linux** (WSL) de la siguiente manera, para ello abrimos el PowerShell de Windows y ejecutamos el siguiente comando:

```bash
wsl --install
```

Una vez que se complete la instalación abre la tienda Microsoft Store desde el menú de inicio, busca la distribución de Linux que desees instalar (en nuestro caso sería Ubuntu), dar click en ‘Obtener’ / ‘Instalar’ y por último una vez instalado podremos iniciar la distribución desde el menú Inicio o ejecutándola desde el PowerShell.


Más información: https://learn.microsoft.com/en-us/windows/wsl/install


### WGet
Es una herramienta de línea de comandos utilizada para descargar archivos de la web. Su instalación se lleva a cabo de la siguiente manera:
- Abrimos WSL (Windows Subsystem Linux)
- INtroducimos en la terminal el siguiente comando:
```bash
sudo apt install wget
```

#### Curl
Es una herramienta de línea de comandos utilizada para transferir datos con URL. Su instalación se lleva a cabo de la siguiente manera:

- Abrimos WSL (Windows Subsystem Linux).
- Introducimos en la terminal el siguiente comando: 

```bash
sudo apt install curl
```
## MacOS
En MacOs desde la terminal instalamos Brew, Curl y WGet de la siguiente manera: 

### Brew

Desde la terminal de MacOs introducimos el siguiete coamndo:

´´´bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
´´´







