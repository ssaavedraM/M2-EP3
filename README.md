# Ejercicio Práctico 3: Implementación de SASS y Framework CSS en el Sitio Web del Hospital

## Descripción

El siguiente proyecto muestra la tercera iteración del desarrollo y mejora del sitio web de un hospital privado. En esta entrega se muestra la implementación del preprocesador SASS para gestionar los estilos de forma más eficiente, modularizando el código y utilizando metodología BEM para organizar los estilos. Además, se integra el framework Bootstrap para hacer uso de sus componentes prefabricados y sobreescribir variables con el fin de mejorar la estructura visual acorde a lo desarrollado en iteraciones anteriores.

***NOTA: Este entregable formó parte de la iteración final del proyecto.***

## Prerrequisitos

Antes de ejecutar y visualizar el proyecto, debe tener instalados los siguientes componetes:
- [**Git**](https://git-scm.com/downloads) : Necesario para clonar el repositorio desde GitHub.
- [**Node.js**](https://nodejs.org/) (versión 12 o superior) : Necesario para instalar paquetes mediante npm.
- **Editor de Código**: Se recomienda [**Visual Studio Code**](https://code.visualstudio.com/).
   - **Extensión Live Sass Compiler**: Para compilar archivos SCSS a CSS en tiempo real.

## Instrucciones para Ejecutar y Visualizar el Proyecto

1. Clone o descargue el repositorio en su máquina.

   Clone el repositorio en su máquina local o descargue el archivo ZIP y extraiga el contenido.
   
   ```bash
   git clone https://github.com/ssaavedraM/EvaluacionM2.git
   ```
2. Navegar hasta la Carpeta del Proyecto y abralo con su editor de código 
3. Instalar Dependencias.

   Abra una terminal e instale las dependencias (en este caso Bootstrap) con el siguiente comando:

   ```bash
   npm install
   ```
   Esto instalará los paquetes listados en el `package.json`, incluyendo Bootstrap en la carpeta `node_modules`.
4. Compilar los archivos SCSS usando Live Sass Compiler en Visual Studio Code

   1. Instale la extensión Live Sass Compiler si aún no lo ha hecho.
   2. Abra el archivo scss/main.scss.
   3. Haga clic en "Watch Sass" en la parte inferior de Visual Studio Code.
  
   La extensión compilará automáticamente los archivos SCSS y generará el archivo CSS en `css/styles.css`. Cualquier cambio que realices en los archivos SCSS se reflejará en tiempo real.
5. Ejecutar el Proyecto
 
   Abra el archivo `index.html` en su navegador web preferido. Puede hacerlo de las siguientes maneras:

   - Haciendo doble clic en el archivo index.html.
   - Arrastrando el archivo index.html a la ventana de su navegador.
   - Usando una extensión como Live Server en Visual Studio Code para lanzar un servidor local.
  
6. Visualizar las Páginas
   
   Navegue a través de las diferentes páginas:
   
   - Home: `index.html`
   - Equipo Médico: `team.html`
   - Contacto: `contact.html`

## Estructura de Carpetas y Archivos

    .
    ├── index.html                         # Página de inicio
    ├── team.html                          # Página del equipo médico
    ├── contact.html                       # Página de contacto
    ├── scss/
    │   ├── abstracts/
    │   │   ├── _mixins.scss
    │   │   └── _variables.scss
    │   ├── base/
    │   │   ├── _base.scss
    │   │   ├── _reset.scss
    │   │   └── _typography.scss
    │   ├── components/
    │   │   ├── _button.scss
    │   │   ├── _card.scss
    │   │   └── _section.scss
    │   ├── layout/
    │   │   ├── _header.scss
    │   │   ├── _footer.scss
    │   │   └── _form.scss
    │   ├── pages/
    │   │   ├── _contact.scss
    │   │   ├── _home.scss
    │   │   └── _team.scss
    │   ├── theme/
    │   │   ├── _dark.scss
    │   │   └── _light.scss
    │   └── vendors/
    │   │   ├── _normalize.scss
    │   │   └── _bootstrap-custom_.scss
    │   ├── main.css
    │   ├── main.css.map
    │   └── main.scss                    # Archivo principal de SASS
    ├── img/
    │   ├── icons/
    │   │   ├── medical_attention.svg
    │   │   ├── medical_emergencies.svg
    │   │   ├── medical_specialities.svg
    │   │   └── person.svg
    │   ├── doctor1.png
    │   ├── doctor2.png
    │   ├── doctor3.png
    │   ├── doctor4.png
    │   └── logo.png
    ├── package.json                     # Archivo de configuración de npm
    ├── package-lock.json      
    └── README.md

## Explicación de cada vista

- Home (index.html): Página principal donde se podrán encontrar los servicios que el hospital ofrece junto a testimonios de los pacientes.
- Equipo Médico (team.html): Página donde se puede encontrar información de los distintos doctores que atienden en el hospital, junto a sus especialidades.
- Contacto (contact.html): Página con formulario de contacto para establecer comunicación con el Hospital. Posee un Mapa embebido mostrando la ubicación del Hospital.

## Implementación de la Modularización de Estilos y Media Queries

Se utiliza SASS siguiendo el patrón de arquitectura 7-1, utilizando de base el siguiente recurso: [Pattern Template 7-1](https://github.com/tanrax/pattern-7-1).

### Media Queries
Se implementan media queries para asegurar que el sitio web sea completamente responsivo, adaptándose a diferentes tamaños de pantalla (dispositivos móviles, tablets y pantallas de escritorio). Se establecen tres puntos de ruptura principales:

- Pantallas pequeñas (small): Menos de 768px.
- Pantallas medianas (medium): Entre 768px y 1024px.
- Pantallas grandes (large): Más de 1024px.

En el archivo `scss/abstracts/_mixins.scss`, se define un mixin para facilitar el uso de media queries

## Estructura de SASS y organización de Archivos Parciales

El proyecto sigue el patrón 7-1, que divide los estilos en 7 carpetas principales y un archivo `main.scss`:

1. abstracts/
   
   Contiene los abstractos como variables y mixins que se utilizan en todo el proyecto.
   - `_variables.scss`: Define variables globales (colores, tipografías, espaciados).
   - `_mixins.scss`: Contiene mixins reutilizables, como el de media queries.

2. base/

   Incluye los estilos base y las reglas de reset.
   - `_reset.scss`: Restablece los estilos predeterminados del navegador.
   - `_typography.scss`: Define las reglas tipográficas generales.
   - `_base.scss`: Contiene estilos generales para elementos HTML básicos.

3. components/

   Contiene los estilos de componentes reutilizables.
   - `_button.scss`: Estilos para botones.
   - `_card.scss`: Estilos para tarjetas utilizadas en servicios, testimonios y equipo médico.
   - `_section.scss`: Estilos para secciones.

4. layout/

   Incluye estilos que estructuran el diseño general del sitio.
   - `_header.scss`: Estilos para el encabezado.
   - `_footer.scss`: Estilos para el pie de página.
   - `_form.scss`: Estilos para formularios.

5. pages/
   
   Estilos específicos para páginas particulares.
   - `_home.scss`: Estilos exclusivos de la página de inicio.
   - `_team.scss`: Estilos para la página del equipo médico.
   - `_contact.scss`: Estilos para la página de contacto.

6. themes/

   Para estilos temáticos o de personalización.
   - `_dark.scss`: Estilo para tema oscuro (por realizar)
   - `_light.scss`: Estilo para tema claro (por realizar)

7. vendors/

   Incluye archivos de terceros o librerías externas.
   - `_normalize.scss`: Restablece los estilos de los navegadores.
   - `_bootstrap-custom.scss`: Archivo para personalizar Bootstrap con SASS.

## Personalización de Bootstrap con SASS

Se personaliza Bootstrap mediante SASS, sobrescribiendo variables como el color primario, secundario, tipografia a utilizar y radio del borde para este caso en `scss/vendors/_bootstrap-custom.scss`.

```scss
$primary: #0056B3;      
$secondary: #00BFFF;   
$font-family-base: 'Poppins';
$font-size-base: 1.0rem;
$border-radius: 5px;

@import "../../node_modules/bootstrap/scss/bootstrap";
```

Con esto, se importa el archivo personalizado de Bootstrap antes de los demás estilos en `main.scss`.

```scss
//vendor
@import 'vendors/bootstrap-custom';

//abstracts
@import 'abstracts/variables';
...
```

## Créditos y Recursos de Terceros

- Bootstrap: Framework CSS utilizado para agilizar el desarrollo y asegurar la responsividad. [Sitio web oficial](https://getbootstrap.com/)
- Normalize.scss: Archivo para normalizar estilos en navegadores. [Repositorio GitHub](https://github.com/kristerkari/normalize.scss)
- Patrón 7-1 para SASS: Estructura de organización de archivos SASS. [Repositorio de referencia](https://github.com/tanrax/pattern-7-1)
- Fuente Poppins: Fuente utilizada en el sitio. [Google Fonts](https://fonts.google.com/specimen/Poppins)