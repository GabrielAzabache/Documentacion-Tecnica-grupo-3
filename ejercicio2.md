# Ejercicio 2
## ¿Que es package.jso?
El archivo package.json es un archivo de configuración utilizado en proyectos de Node.js para gestionar dependencias y metadatos del proyecto. Es el núcleo del ecosistema de npm (Node Package Manager) y facilita la instalación, configuración y administración de paquetes.

## ¿Cual es su proposito?
El archivo package.json es el núcleo de configuración de un proyecto Node.js. Su propósito principal es centralizar información sobre cómo interactuar con la aplicación, ejecutarla y manejar sus dependencias. Tanto npm como yarn utilizan este archivo para identificar el proyecto y gestionar su ciclo de vida de manera eficiente.
Además, es fundamental para el desarrollo, incluso si no planeas publicar tu proyecto en npm. Por ejemplo, el archivo es necesario para instalar paquetes desde npm y definir la estructura del flujo de trabajo del proyecto.

## Estructura:
```
{
  "name": "nombre-del-proyecto",
  "version": "Se recomienda el uso de SemVer",
  "description": "Descripción breve del proyecto",
  "main": " Indica el archivo de arranque del paquete. Por defecto es index.js",
  "scripts": "Un objecto en el que poder definir los scripts con los que poder interactuar con el programa",
  "dependencies": "Son las librerías de terceros que la aplicación necesita para funcionar correctamente en producción.",
  "devDependencies": "se trata de dependencias que no son necesarias instalarse para producción y solo se utilizan en tiempo de desarrollo.",
  "author": "Tu nombre",
  "license": "Indica bajo que licencia se distribuye el código"
}
```
