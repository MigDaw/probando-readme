![Logo](assets/img/rookiesLogoPanoramico.jpg)

# OnBoarding-TypeScript

Este repositorio te guiará en la configuración de tu entorno para comenzar a trabajar con **TypeScript** y resolver tus primeros ejercicios.

## Opción 1: Instalación de TypeScript en el ordenador (Recomendada para ejercicios sueltos)

La forma más sencilla para empezar a trabajar con TypeScript es instalarlo globalmente en tu ordenador. Esto te permitirá compilar tus archivos `.ts` a `.js` y ejecutar tus programas directamente.

### Pasos:

1. **Descargar e instalar TypeScript:**

   - Ve a la página oficial de TypeScript: [https://www.typescriptlang.org/download/](https://www.typescriptlang.org/download/).

2. **Instalar TypeScript globalmente con npm:**

   - Abre la terminal y ejecuta el siguiente comando:

    ```bash
     npm install -g typescript
     ```

3. **Verificar la instalación:**

   - Para comprobar que TypeScript se ha instalado correctamente, ejecuta:

     ```bash
     tsc --version
     ```
   - Esto debería devolver la versión de TypeScript instalada en tu máquina.

4. **Estructura de carpetas recomendada a crear**

   ```bash
   typescript-onboarding/
   │── solutions/
   │   ├── exercise1/
   │   │   ├── index.ts
   │   │   ├── index.html
   │   ├── exercise2/
   │   │   ├── index.ts
   │   │   ├── index.html
   │   ├── exercise3/
   │   │   ├── index.ts
   │   │   ├── index.html
   │
   │── dist/   # Esta carpeta se generará automáticamente con los archivos compilados asi que no hace falta que   la crees, es solo para mostrar como quedará (forma recomendada)
   │   ├── exercise1/
   │   │   ├── index.js
   │   ├── exercise2/
   │   │   ├── index.js
   │   ├── exercise3/
   │   │   ├── index.js
   │
   │── .eslintrc.cjs   # Configuración de ESLint
   │── .prettierrc     # Configuración de Prettier
   │── tsconfig.json   # Configuración de TypeScript
   │── README.md       # Documentación del repositorio

5. **Configurar TypeScript**

- Genera un archivo de configuración para TypeScript con el siguiente comando:

```bash
tsc --init
```
- Luego, edita el archivo tsconfig.json para que luzca así:

```bash
{
  "compilerOptions": {
    "target": "ES6",
    "module": "ES6",
    "rootDir": "./solutions",
    "outDir": "./dist",
    "strict": true
  }
}
```

6. **Compilar los archivos TypeScript**
- Para compilar todos los ejercicios:

```bash
tsc
```

- Si prefieres que TypeScript observe los archivos y los compile automáticamente cada vez que realices un cambio, puedes usar el modo **watch**:
```bash
tsc --watch
```
- Si usas **tsc --watch** desde el principio, no necesitarás compilar manualmente después. Cada vez que guardes un archivo o añadas un nuevo archivo .ts en la carpeta **solutions/**, el compilador se encargará de compilarlo automáticamente en la carpeta **dist/**.

- Esto generará la carpeta **dist/** con los archivos compilados, manteniendo la misma estructura de **solutions/**.

7. **Configurar Prettier y ESLint (Opcional, pero recomendado)**
Para mejorar la calidad del código, puedes instalar Prettier y ESLint con:

```bash
npm install --save-dev prettier eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin
```
***Nota: estas configraciones pueden variarse y personalizarse a nuestro gusto***

- Luego, crea el archivo .prettierrc con el siguiente contenido:
```bash
{
  "semi": true,
  "singleQuote": true,
  "trailingComma": "all"
}
```
- Ahora crea el archivo .eslintrc.cjs con esta configuración:

```bash
module.exports = {
  env: {
    browser: true,
    es6: true
  },
  parser: "@typescript-eslint/parser",
  extends: [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended"
  ],
  rules: {
    "no-unused-vars": "warn",
    "prefer-const": "error",
    "@typescript-eslint/no-explicit-any": "warn"
  }
};
```

También suele ser recomendable instalar las siguientes extensiones aunque hayamos instalado las dependencias a nivel de proyecto:

- [ESLint](https://eslint.org/)
- [Prettier](https://prettier.io/)

8. **Por último podríamos ejecutar los siguientes comandos para revisar errores en el código y de formato (Opcional y si hemos seguido el paso 7)**

- Para asegurarnos de que sigamos las reglas definidas en nuestro archivo de configuración **.eslintrc.cjs** ejecuta:
```bash
npx eslint solutions/**/*.ts
```

- Y para asegurarnos de que sigamos las reglas definidas en nuestro archivo de configuración **.prettierrc** ejecuta::
```bash
npx prettier --write .
```

## Opción 2: Crear un proyecto con Vite (Ideal para proyectos más grandes)

Si prefieres trabajar en un entorno de desarrollo más estructurado, puedes usar [Vite](https://vitejs.dev/), una herramienta moderna para crear proyectos de desarrollo rápido con soporte nativo para TypeScript.

### Pasos:

1. **Crear un nuevo proyecto con Vite:**
   - Ejecuta el siguiente comando para crear un nuevo proyecto usando la plantilla de TypeScript:

     ```bash
     npm create vite@latest
     ```
    - **1.1** Selecciona el nombre del proyecto
    - **1.2** Selecciona el framework vanilla
    - **1.3** Selecciona Typescript

    - Esto creará una nueva carpeta con un proyecto de Vite configurado para TypeScript.
   

2. **Instalar dependencias del proyecto:**
   - Accede a la carpeta del proyecto recién creado:

     ```bash
     cd nombre-proyecto
     ```

   - Luego, instala las dependencias:

     ```bash
     npm install
     ```

3. **Iniciar el servidor de desarrollo:**
   - Para comenzar a trabajar en tu proyecto, ejecuta:

     ```bash
     npm run dev
     ```

   - Esto iniciará el servidor de desarrollo y abrirá el proyecto en tu navegador.

4. **Desarrollo con Vite:**
   - Puedes comenzar a agregar y modificar archivos `.ts` en el proyecto. Los cambios se reflejarán automáticamente en el navegador gracias a la recarga en vivo de Vite.
