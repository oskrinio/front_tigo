# Documentación de barra de navegación | **TIGO**

* Contenido del documeto
  - Manual de administrador Drupal
  - Instalación
  - Desarrollo

## Manual de administrador Drupal
Los menús están ubicados en `admin/structure/menu` para su edición, y se muestran al ser añadidos como bloques en `admin/structure/block`.
#### Tipos de menús
1.  **Menú para Móvil**: *navbar-complete-pqr__mobile*
1.  **Menú de tipo de usuario empresas y personas**: *navbar-complete-pqr__top-left*
1.  **Menú mi cuenta y radicación PQR**: *navbar-complete-pqr__top-right*
1.  **Menú principal**: *navbar-complete-pqr__main*
#### Campos
*   **Título Del enlace del menú**: Nombre del elemento del menú.
*   **Enlace**: Url a donde redirigirá
  > NOTA: Si el elemento creado es de primer nivel, segundo nivel, un mega menú o cualquier elemento que no redirija a una *url* en especifico debe tener `#`.

*   **Activado**: De no estar activado no se mostrará.
*   **Descripción**: Texto extra que explica el contenido, este campo es necesario por accesibilidad.
*   **Mostrar expandido**: Este campo se selecciona si el elemento tiene hijos, si no se activa, no se mostrarán.
*   **Enlace padre**: Si es un hijo de otro elemento en el menú, acá lo escogemos.
*   **Peso**: El peso del elemento entre los enlaces del mismo menú.
*   **Atributos**: Listado de opciones para comportamientos avanzados.
  *   **Nombre de la clase**: Esta es solo utilizada para estilos css, algunas clases traen comportamientos particulares y es recomendable que no sean cambiados, ejemplo: *logo*, *account*, *border*, *js-open-menu*
  *   **Dónde abrir el link?**: Seleccionable que define si el link se abre en la misma página o en una diferente.
  *   **El elemento se mostrará únicamente en**: El elemento se mostrará unicamente en móvil o en escritorio, si se muestra en los dos no dejar ninguna de estas dos opciones.
    > NOTA: Si un elemento se esconde y contiene hijos, estos se ocultarán también

  *   **Ancho de la columna**: Asigna el valor del ancho de la columnda, valores aceptados: 
    *   **12**: La columna tendrá el 100% del espacio disponible.
    *   **6**: La columna ocupará la mitad del espacio, pueden caber hasta dos elementos de 6 columnas.
    *   **4**: La columna ocpará un tercio del espacio, pueden haber hasta 3 elementos de 4 columnas
    *   **3**: Lacolumna ocpar´á un cuarto del espacio, pueden haber hasta 4 elementos de 4 columnas
  *   **Nombre del icono**: Este tiene que ser exactamente igual al nombre de la clase del ícono a escoger, [ver iconos disponibles](190.248.48.5/contenidos/UX/idigital/index.php/diseno-tigoune/iconos)
      >   NOTA: Los iconos agregados elementos del primer nivel en el menú solo se muestran en móvil.

  *   **Tamaño del icono**: Recibe un número que es transformado en pixeles para darle un ancho fijo al ícono.
  *   **MEGA-MENU**: Todos los campos que tengan este prefijo pertenecen únicamente a elementos tipo mega menú, para definirlos es necesario responder **si** al seleccionable *"Este menú es una imagen con texto y botón?"*
  *   **MEGA-MENU, Imagen del menú**: Se necesita la **url** completa de la imagen, en lo posible que no sea una url segura (HTTPS), ni que tampoco tenga espacios ni caracteres especiales (&?=) en lo posible, además necesita terminar con la extensión del tipo de imagen ie: *http://repodeimagenes-com/mi-imagen.jpg*. la imágen debe tener 170 pixeles de alto y mínimo 300 pixeles de ancho para una columna de 3 y de 4.
  *   **MEGA-MENU, Texto del botón**: Texto del mega menu, el máximo de caracteres recomendados es de 15 caracteres.
  *   **MEGA-MENU, Link del botón**: Link a donde redirecciona el botón del mega menu, esta ruta puede ser relativa o absoluta.
  *   **MEGA-MENU, Dónde abrir el link de el botón del mega menu?**: Opción para abrir el link del mega-menu en una pestaña nueva o en la misma pestaña, por defecto los links abren en la misma pestaña:
  *   **MEGA-MENU, Texto del menú**: Espacio para el texto del mega menú, el máximo de caracteres recomendados es de 50.
## Instlación
___
*   La barra de navegación esta elaborada con la base del tema `tigo_theme`, así que es necesario que esté instalado y activo.
*   En `/admin/modules` el módulo *Menu Link Attributes* debe estar instalado y activo.
* En `/admin/structure/block` añadir los siguientes bloques en el orden mostrado:
  *   Barra de navegación:
    1.  navbar-complete-pqr__mobile
    1.  navbar-complete-pqr__top-left
    1.  navbar-complete-pqr__top-right
    1.  navbar-complete-pqr__main
    ...
## Desarrollo
___

La funcionalidad de dropdown en móvil está basado en la clase *DropDown* en: `themes/tigo_theme/src/core/js/components/dropdown.js`.
Las funcionalidades asignadas en el formulario del administrador y de abrir y cerrar el menú en móvil esta en la clase `HamburgerMenu` en: `themes/tigo_theme/src/core/js/components/navbar.js`
Los estilos en `themes/tigo_theme/src/core/scss/components/_navbar-complete.scss`
El markup está en: `themes/tigo_theme/templates/custom/menu.html.twig`
