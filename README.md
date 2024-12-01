# Documentacion-Tecnica-grupo-3
## Estudiantes:
- Mercado Azabache
- Fernandez Malco Diego

## Ejercicio 1: 
Verificar si Node.js está instalado

Abre una terminal o consola (CMD en Windows, Terminal en Mac/Linux).

Ejecuta el siguiente comando:

bash

Copiar código

node -v

Si devuelve un número de versión como v18.17.0, Node.js ya está instalado.

Si no aparece, necesitas instalarlo siguiendo los pasos a continuación.

Descargar e instalar Node.js

Ve al sitio oficial de Node.js: https://nodejs.org.

Descarga la versión LTS (Long Term Support).

Instala Node.js según tu sistema operativo:

Windows:

Ejecuta el archivo .msi descargado.

Acepta los términos de licencia.

Asegúrate de seleccionar la opción "Agregar Node.js al PATH".

Finaliza la instalación.

MacOS:
Abre el archivo .pkg descargado.

Sigue las instrucciones del instalador.

Finaliza la instalación.

Linux:

Abre la terminal.

Ejecuta:

bash

Copiar código

sudo apt update

sudo apt install -y nodejs npm

O instala con nvm para versiones específicas:

bash

Copiar código

curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.4/install.sh | bash
source ~/.bashrc

nvm install --lts

Verificar instalación

Comprueba la instalación de Node.js:
bash

Copiar código

node -v

Comprueba la instalación de npm:
bash

Copiar código

npm -v
## Ejercicio 2: 
El package.json de su proyecto es el lugar central para configurar y describir cómo interactuar con su aplicación y ejecutarla. La CLI de npm (y yarn) lo utilizan para identificar su proyecto y comprender cómo manejar las dependencias del proyecto. Es el archivo package.json que permite a npm iniciar su proyecto, ejecutar scripts, instalar dependencias, publicar en el registro de NPM y muchas otras tareas útiles. La CLI de npm también es la mejor manera de administrar su package.json porque ayuda a generar y actualizar su archivo package.json durante la vida de un proyecto.
