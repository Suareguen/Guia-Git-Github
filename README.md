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
- Introducimos en la terminal el siguiente comando:
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
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Más información: https://brew.sh/

### Curl

```bash
brew install curl
```

### WGet

```bash
brew install wget
```

### Git

```bash
brew install gist
```
Más información: https://git-scm.com/download/mac.

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

**Nota: En donde "youremail@example.com" pondremos nuestro email de Github.**

**Le damos a enter hasta que nos termine de preguntar, creo que era 3 veces.**

Ahora nos aseguraremos de que todo se haya generado correctamente y que los archivos tengan los permisos correctos. 
Dentro de la carpeta .ssh debería haber 2 archivos: **id_ed25519** e **id_ed25519.pub**.

```bash
ls -l .ssh
```

Los permisos del archivo id_ed25519 deberían ser -rw-------, y las de id_ed25519.pub, -rw-r--r--. Si no tienen esos permisos, corregidlos con el comando chmod tal y como aprendimos en la primera clase de Linux Intro. 

Ahora iniciaremos el agente que nos gestionará todas nuestras llaves y le damos la llave SSH que habíamos generado: 

```bash
eval "$(ssh-agent -s)" 
```
```bash
ssh-add ~/.ssh/id_ed25519
```

Por último copiamos (**copiamos todo menos el email que nos aparece al final**) la clave con el comando que os paso aquí abajo y pegamos lo que nos sale en la sección de Settings -> SSH and GPG keys. **IMPORTANTE**: no dejar espacios al principio ni al final.

```bash
cat ~/.ssh/id_ed25519.pub
```
#### ¿Cómo añadir clave SSH a nuestra cuenta de Github?

Si el archivo de tu clave pública SSh tiene un nombre diferente al del código de ejemplo, modifica el nombre del archivo para que coincida con tu configuración actual. Al copiar tu clave, no agregues saltos de línea ni espacios en blancos nuevos.

En la esquina superior derecha de cualquiera de las páginas de Github, haz click en tu foto de perfil y luego en Configuración (Settings) y luego haz click en el apartado ‘SSH and GPG Keys’ que aparece en la izquierda.

![desc](https://res.cloudinary.com/mypath/image/upload/v1673485751/mypath-assets/222aa250-7588-49b8-af68-f6441bcd2bc7/userbar-account-settings_a6gbnw.png)

Una vez estemos dentro de la sección `SSH and GPG Keys` hacemos click en `New SSH`:
![desc](https://res.cloudinary.com/mypath/image/upload/v1673485808/mypath-assets/222aa250-7588-49b8-af68-f6441bcd2bc7/ssh-add-ssh-key-with-auth_jkzvoq.png)

Debería aparecernos la siguiente vista:
![desc](https://res.cloudinary.com/mypath/image/upload/v1673485974/mypath-assets/222aa250-7588-49b8-af68-f6441bcd2bc7/ssh-key-paste-with-type_bdudom.png)

Como título por algo que sea descriptivo, si es tu ordenador personal puedes poner ‘Ordenador Personal’ por ejemplo.
En el apartado Key Field pega la clave que obtuviste anteriormente mediante el comando `cat`, copiando todo menos el email que nos da como mencionamos anteriormente, y haz click en ‘Add SSH key’ y ya todo debería estar listo.














