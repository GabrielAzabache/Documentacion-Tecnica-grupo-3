# Documentacion-Tecnica-grupo-3
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
