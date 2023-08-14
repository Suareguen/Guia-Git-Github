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

### Curl
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



### Curl

```bash
brew install brew
```

### WGet

```bash
brew install wget
```

### Git

```bash
brew install got
```


## Windows / MascOS / Ubuntu
**Importante**: Si estamos usando como Sistema Operativo Windows antes de ejecutar los comandos indicados abajo debemos abrir Windows Subsystem Linux (WSL) y ejecutar los comandos desde dicha terminal.

Una vez dicho esto vamos a configurar **Git** ejecutando los siguientes comandos:

```bash
git config --global user.name "JohnDoe"
```

```bash
git config --global user.email johndoe@email.com
```

**Nota**: En donde aparecen “John Doe” y johndoe@exameple.com pondremos el nombre de usuario que queramos y el email que vayamos a usar, en este caso es recomendable usar el usuario e email que vayamo a usar en Github, no es necesario pero para evitar líos posteriores. 

Más información: https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration


Una vez que ya tenemos Git configurado pasamos a generar una clave SSH y añadirla a nuestra cuenta de Github.

#### ¿Cómo crear la clave SSH?
Accedemos al directorio que contiene la carpeta .ssh, la ruta debería ser /home/nombre-de-usuario, en mi caso:

```bash
cd home/adrian
```

Si miráis el contenido de esta carpeta con veréis que no aparece ninguna carpeta llamada .ssh. Esto es porque se trata de una carpeta oculta (todas las carpetas ocultas empiezan por .), pero aunque no lo veamos está ahí. Para ver las carpetas ocultas de un directorio usamos el comando:

```bash
ls -a
```
Si nos aparace la carpeta **.ssh** borramos dicha carpeta con el siguiente comando:

```bash
rm -r .ssh
```
Volvemos a generar una clave SSH como hicimos el día del install party, no os preocupéis, os paso los comandos pasito a pasito:
Aquí abajo acordaos de cambiar your_email@example.com por el correo que utilizasteis para registraros en GitHub, ¡¡debe ser el mismo!! 
Vamos a generar una clave SSH para ello ejecutamos el siguiente comando:
```bash
 ssh-keygen -t ed25519 -C "your_email@example.com"
```


**Nota: En donde "youremail@example.com" pondremos nuestro email de Github,**






