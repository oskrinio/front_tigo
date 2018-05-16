# MJML
La herramienta utilizada para la maquetación de los correos htm es [mjml](https://mjml.io/), MJML es un lenguaje creado y diseñado para reducir el dolor de codificar un correo electrónico responsivo. Su sintaxis semántica lo hace fácil y sencillo, mientras que su biblioteca de componentes estándar enriquece su tiempo de desarrollo y lo optimiza. El motor de código abierto de MJML se encarga de traducir el MJML que escribió en HTML versión 1, este funciona para todos los servicios de correos, hasta outlook.

## Uso MJML
plugins y aplicaciones para MJML:
- [MJML App](https://mjmlio.github.io/mjml-app/) (viene con MJML)
- [Visual Studio Code plugin](https://github.com/attilabuti/vscode-mjml) (viene con  MJML)
- [Atom plugin](https://atom.io/users/mjmlio) (MJML necesita ser instalado)
- [Sublime Text plugin](https://packagecontrol.io/packages/MJML-syntax) (MJML necesita ser instalado)
- o simeplemente en la web [MJML try it live](https://mjml.io/try-it-live)

## Ejemplos MJML

Hay dos correos actualmente creados con mjml en la carpeta `/ejemplos` puede copiar y pegar el código en calquier editor y renderezarlo

## Recomendaciones

* Subir código minificado al sistema de templates, en este caso sendgrid
* Imágenes:
  * Utilizar pocas imágenes, 2 o 3 máximo.
  * Deben ser optimizadas.
  * Que el contenido no dependa de las imagenes, menos si son CTA's pues no todos los servicios de mailing muestran las imágenes sin requerir permisos del usuario.
  * Deben ser subidas a un dominio `http://`.
* Utilizar mejores prácticas de HTML en general como atributos `alt`, `title`.
* Definir colores, estilos, y variables que se repiten a lo largo del código, para poder tener un código escalable, ejemplo:
  * ```
     <mj-attributes>
      <mj-class name="blue-font" color="#00377B" />
      <mj-class name="cyan-font" color="#00CCF8" />
      <mj-class name="gray-light-font" color="#A9ADB4" />
      <mj-class name="gray-font" color="#707682" />
      <mj-class name="black-font" color="#292B34" />
      <mj-class name="extra-small-font" font-size="12px" line-height="12px" />
      <mj-class name="small-font" font-size="14px" line-height="14px" />
      <mj-class name="regular-font" font-size="16px" line-height="16px" />
      <mj-class name="big-font" font-size="20px" line-height="20px" />
      <mj-class name="extra-big-font" font-size="30px" line-height="40px" />
      <mj-class name="cyan-button" font-weight="300" border-radius="25px" background-color="#00CCF8" color="#FFFFFF" font-size="14px" />
      <mj-class name="transparent-button" font-weight="300" border-radius="25px" border=".5px solid" background-color="transparent" color="#292B34" font-size="14px" />
      <mj-all font-family="Roboto" />
    </mj-attributes>
    ```
