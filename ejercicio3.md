# Instalar TypeScript
 
## Asegúrate de tener Node.js instalado.
 
### En la terminal, instala TypeScript de forma global:
 
Copiar código
  ``` bash
npm install -g typescript
  ```
Verifica la instalación:
 
Copiar código
  ``` bash
  tsc -v
  ```
Debería aparecer una versión como Version 5.2.2.
Configurar TypeScript
### Navega a tu proyecto y ejecuta:
 
Copiar código
  ``` bash
  tsc --init
  ```
Esto generará un archivo de configuración llamado tsconfig.json.
 
### Ejemplo de configuración (tsconfig.json):
 
json
Copiar código
  ``` bash
  {
  "compilerOptions": {
    "target": "es6",
    "module": "commonjs",
    "strict": true,
    "outDir": "./dist"
  },
  "include": ["src/**/*.ts"],
  "exclude": ["node_modules"]
  }
  ```
Compilar archivos TypeScript
 
### Crea una carpeta src y dentro un archivo index.ts con el siguiente contenido:
 
typescript
 
Copiar código
  ``` bash
  const saludo: string = "¡Hola, TypeScript!";
  console.log(saludo);
  Compila el archivo:
  ```
Copiar código
  ``` bash
  tsc
  ```
Esto generará un archivo JavaScript en la carpeta dist.
 
Ejecuta el archivo compilado:
 
Copiar código
  ``` bash
  node dist/index.js
```
