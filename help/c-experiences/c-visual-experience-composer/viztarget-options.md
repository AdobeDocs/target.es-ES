---
keywords: visual experience composer options;experience composer options;experience options;edit text;edit html;edit text/html;edit background color;background color;insert element;edit link;link;visual experience composer link;edit css class;css class;swap offer;offer swap;swap image;image swap;remove item;item remove;hide item;item hide;rearrange;move element;element move;resize element;element resize;element;expand selection;navigate to this link;navigate link;link navigate;navigate;link;undo;redo;undo/redo
description: Al hacer clic en un elemento de página del Compositor de experiencias visuales (VEC) de Adobe Target, se muestra un menú con las opciones disponibles para dicho tipo de elemento.
title: Opciones del Compositor de experiencias visuales (VEC) de Adobe Target
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '2403'
ht-degree: 94%

---


# Opciones del Compositor de experiencias visuales

Al hacer clic en un elemento de página en el [!DNL Adobe Target] [!UICONTROL Compositor de experiencias visuales] (VEC), un menú muestra las opciones disponibles para ese tipo de elemento. Además, se muestra una ruta DOM en la parte inferior de la página que permite navegar fácilmente por la estructura de la página.

## Opciones de VEC

Las distintas acciones del Compositor de experiencias visuales (VEC) agrupan las opciones de menú apropiadas para que su trabajo sea más rápido y eficiente:

![Menú Opciones de VEC](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>Las opciones disponibles dependen del tipo de actividad que esté editando.

### Editar

Las opciones disponibles son las siguientes:

#### Texto/HTML {#edit-text-html}

Cambie el código HTML del elemento, como el texto de un área de texto, un botón o un vínculo.

Además del código HTML, puede editar e insertar JavaScript personalizado.

Hay varias opciones disponibles para aplicar formato de texto enriquecido al editar texto y código HTML para actividades [!UICONTROL A/B] y de [!UICONTROL Segmentación de experiencias]. Puede seleccionar un tipo de letra, elegir un estilo de letra y cambiar la alineación del texto, entre otras opciones estándar de formato de texto. Cuando modifica el código HTML, puede cambiar entre la vista de código y la vista de edición enriquecida del código HTML.

Se pueden anidar las siguientes etiquetas HTML5:

| Etiqueta | Etiquetas anidadas permitidas |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`,  `<ol>`,  `<menu>`,  `<h1-h6>`,  `<p>` |
| `<label>` | `<p>` |

#### Color de fondo

Use el selector de color para seleccionar o configurar un color de fondo. Puede seleccionar una muestra de colores y ajustarla con valores RGB o códigos hexadecimales de color. La “x” roja del selector de color define que el fondo sea transparente.

**Nota:** Esta opción no está disponible para los elementos en los que haya establecida una imagen de fondo.

#### Estilos   {#styles}

Utilice el panel [!UICONTROL Estilos] para ver o editar el valor de los estilos existentes para el elemento seleccionado. También puede añadir estilos adicionales.

Para acceder al panel [!UICONTROL Estilos], haga clic en un elemento de página desde el VEC y, a continuación, haga clic en **[!UICONTROL Editar]** > **[!UICONTROL Estilos]**.

El panel [!UICONTROL Estilos] aparece en la parte derecha del VEC. El panel contiene una lista de estilos que le permite editar o agregar al elemento seleccionado. Un editor CSS en tiempo real permite ver cambios y agregar estilos si se siente cómodo utilizando hojas de estilo en cascada (CSS) o si recibe código de su desarrollador.

![Panel Estilos](/help/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

Al aplicar distintos estilos, siempre puede revertir los cambios haciendo clic en el icono [!UICONTROL Deshacer] que aparece en la esquina superior derecha del panel [!UICONTROL Estilos] después de realizar un cambio en cualquier sección. Tenga en cuenta que al hacer clic en el icono [!UICONTROL Deshacer] se revertirán todos los cambios en el panel de la sección actual.

Expanda cada sección para editar o agregar estilos, como se explica a continuación. Para guardar los cambios, haga clic en el icono Volver en la parte superior del panel para regresar a la pantalla principal del panel y, a continuación, haga clic en **[!UICONTROL Guardar]**.

Observe que los puntos azules en el panel principal y junto a cada opción en los diversos paneles de sección indican que ha realizado cambios en los estilos correspondientes. Esto facilita la revisión de los cambios antes de hacer clic en [!UICONTROL Guardar].

>[!NOTE]
>
>Las acciones rápidas para cambios de diseño, color de fondo, cambio de tamaño y movimiento también están disponibles como acciones independientes en el menú VEC. Estas opciones se pueden aprovechar como acciones independientes o puede utilizar el menú Estilos, tal como se explica aquí.

* **Contexto**

   Cambiar el color de fondo y la imagen.

   * Color (especifique el código de color o use el selector de color)
   * Imagen (seleccione una imagen del selector de imágenes)
   * Origen de imagen (especifique una URL externa)
   * Adjunto
      * Haga clic en la lista desplegable superior para seleccionar desplazamiento, fijo o local
      * Haga clic en la lista desplegable inferior para seleccionar repetir, repetir-x, repetir-y, no repetir, espacio o redondo
   * Clip
      * Haga clic en la lista desplegable superior para seleccionar el cuadro de borde, el relleno de margen, el cuadro de contenido o el texto
      * Haga clic en la lista desplegable inferior para seleccionar audio o audio automático

* **Tipografía**

   Cambie la tipografía de un elemento. Las ediciones tipográficas son rápidas y sencillas.

   Aunque el editor de texto enriquecido (Editar texto/HTML) está disponible para un mejor ajuste, las acciones rápidas para realizar cambios en todo el elemento están disponibles a través de esta opción. Si desea aplicar cambios tipográficos solo a una parte del texto (no al texto completo), utilice el [editor de texto enriquecido](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).

   Puede editar los siguientes estilos tipográficos:

   * Tamaño de fuente
   * Grosor de fuente
   * Estilo de fuente
   * Color (especifique el código de color o use el selector de color)
   * Espaciado entre palabras
   * Altura de línea
   * Alineación de texto

* **Margen**

   Cambie el margen del elemento seleccionado. Puede cambiar los márgenes izquierdo, derecho, inferior y superior.

   Haga clic en el icono desplegable de cada margen para elegir entre las siguientes opciones:

   * Automático
   * Valor (arrastre el control deslizante para definir el margen o especificar el número de píxeles para cada margen)

   El margen admite valores positivos y negativos.

   Target también admite otras unidades de tamaño, como rem, pc, em, etc. Para obtener más información sobre estas unidades, consulte [Hojas de estilo web Consejos y trucos CSS](https://www.w3.org/Style/Examples/007/units.en.html).

* **Relleno**

   Cambie el relleno del elemento seleccionado. Puede cambiar el relleno izquierdo, derecho, inferior y superior.

   Arrastre el control deslizante para definir el relleno o especifique el número de píxeles para el relleno.

   El relleno admite escalas de anchura a partir de 0.

   Destinatario también admite [otras unidades de tamaño](https://www.w3.org/Style/Examples/007/units.en.html), como rem, pc, em, etc.

* **Borde**

   Haga clic en los iconos de borde en la parte superior del panel para cambiar el borde del elemento seleccionado.

   Puede editar los estilos siguientes para cada borde (superior, derecho, inferior e izquierdo):

   * Estilo de borde (ninguno, oculto, punteado, discontinuo, continuo o doble)
   * Color de borde (especifique el código de color o use el selector de color)
   * Ancho de borde (arrastre el control deslizante para seleccionar un ancho de borde o especificar la anchura en píxeles)

   El borde admite escalas de anchura a partir de 0.

   Destinatario también admite [otras unidades de tamaño](https://www.w3.org/Style/Examples/007/units.en.html), como rem, pc, em, etc.

* **Posición**

   Mueva el elemento seleccionado desde su posición actual. Puede cambiar la posición superior, inferior, izquierda, derecha y [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) del elemento.

   Haga clic en la lista desplegable [!UICONTROL Estática] para elegir entre las siguientes opciones de posición:

   * Estático
   * Relativo
   * Absoluta
   * Fijo
   * Fijo

   Haga clic en el icono desplegable de cada posición para elegir entre las siguientes opciones:

   * Automático
   * Valor (arrastre el control deslizante para colocar el elemento o especificar el número de píxeles que desea desplazar el elemento)

   La posición admite valores positivos y negativos.

   Destinatario también admite [otras unidades de tamaño](https://www.w3.org/Style/Examples/007/units.en.html), como rem, pc, em, etc.

* **Tamaño**

   Cambie la anchura y la altura del elemento seleccionado.

   Haga clic en el icono desplegable situado junto a [!UICONTROL Anchura] y [!UICONTROL Altura] para elegir entre las siguientes opciones:

   * Automático
   * Valor (arrastre el control deslizante para cambiar el tamaño del elemento o especificar el número de píxeles para cada dimensión)

* **Filtro**

   Arrastre el control deslizante para cada opción de filtro o especifique el porcentaje que desee:

   * Sepia
   * Contraste
   * Brillo
   * Escala de grises
   * Desenfocar
   * Opacidad
   * Invertir
   * Rotación de tono
   * Saturar

* **Editor CSS**

   El editor CSS en tiempo real permite ver cambios y agregar estilos si se siente cómodo utilizando hojas de estilo en cascada (CSS) o si recibe código de su desarrollador.

   El editor CSS muestra los cambios realizados en el panel Estilos. Como se muestra en la siguiente ilustración, se han cambiado el tamaño de fuente, el borde superior y el tamaño de la imagen:

   ![Editor CSS con cambios](/help/c-experiences/c-visual-experience-composer/assets/css-changes.png)

   Observe los puntos azules junto a las opciones de [!UICONTROL Tipografía], [!UICONTROL Borde] y [!UICONTROL Tamaño] de la ilustración anterior. Estos puntos indican que ha realizado cambios en estas secciones. Si abre estos paneles de sección, aparecen puntos azules junto a las opciones específicas que ha modificado.

   Puede escribir su propio código si el estilo deseado no está disponible de forma predeterminada en [!UICONTROL Estilos].

   Tenga en cuenta que el editor CSS muestra solo los detalles de la sesión actual. Si guarda cambios y vuelve a abrir el editor, los detalles sobre el cambio anterior no se muestran en el editor, aunque vuelva a seleccionar el mismo elemento.

   >[!IMPORTANT]
   >
   >Puede aplicar una imagen de fondo mediante el editor CSS, pero puede provocar parpadeos. Pruebe los cambios antes de la implementación.

#### Clase CSS

Especifica la clase CSS predefinida usada para el elemento. Si selecciona más de un elemento, separe varias clases CSS con un espacio.

Disponible para actividades de prueba [!UICONTROL A/B], [!UICONTROL Personalización automatizada] y [!UICONTROL Prueba multivariable].

#### Vínculo

Cambia la dirección URL del vínculo.

Use Editar vínculo para actualizar el selector y que señale al mismo elemento de imagen. Sin embargo, no se permite vincular a otro elemento de imagen. Para vincular a otro elemento de imagen, elimine la acción original del editor de código y use el [!UICONTROL Compositor de experiencias visuales] para aplicar la acción en el otro elemento de imagen.

### Insertar antes

Las opciones disponibles son las siguientes:

#### Imagen, HTML y texto

Agrega cualquier tipo de elemento a la página además de modificar el contenido existente. Agregue texto, código, listas, etc. para crear experiencias que probar completamente diferentes.

Seleccione un elemento en la página, haga clic en [!UICONTROL Insertar antes] y elija si quiere insertar una imagen, HTML o texto. El elemento insertado aparece antes del elemento seleccionado.

El comportamiento del elemento insertado depende de la estructura de la página, el CSS y otras opciones de configuración de la página. Para que la página se muestre correctamente, es necesario que el código HTML sea válido. Después de insertar un elemento, pruebe siempre la página para asegurarse de que se muestra correctamente.

[!UICONTROL Recommendations] admite [!UICONTROL Insertar antes] los contenidos de las etiquetas DIV, SECTION y ARTICLE.

**Nota:**[!DNL Adobe Scene7 Publishing System] Para insertar una imagen es necesario que esté activado y así tener acceso a la biblioteca de imágenes.

#### Recomendación

Incluya recomendaciones dentro de la prueba A/B (incluidas las actividades de asignación automática y segmentación automática) y de segmentación de experiencias (XT). Para obtener más información, consulte [Recommendations como oferta](/help/c-recommendations/recommendations-as-an-offer.md).

#### Fragmento de experiencia

Insertar fragmentos de experiencia creados en [!DNL Adobe Experience Manager](AEM)[!DNL Target] en actividades para ayudar en la optimización o personalización. Para obtener más información, consulte [Fragmentos de experiencia de AEM](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Insertar después

Las opciones disponibles son las siguientes:

#### Imagen, HTML y texto

Agrega cualquier tipo de elemento a la página además de modificar el contenido existente. Agregue texto, código, listas, etc. para crear experiencias que probar completamente diferentes.

Seleccione un elemento en la página, haga clic en [!UICONTROL Insertar después] y elija si quiere insertar una imagen, HTML o texto. El elemento insertado aparece a continuación del elemento seleccionado.

El comportamiento del elemento insertado depende de la estructura de la página, el CSS y otras opciones de configuración de la página. Para que la página se muestre correctamente, es necesario que el código HTML sea válido. Después de insertar un elemento, pruebe siempre la página para asegurarse de que se muestra correctamente.

[!UICONTROL Recommendations] admite [!UICONTROL Insertar después] los contenidos de las etiquetas DIV, SECTION y ARTICLE.

**Nota:**[!DNL Adobe Scene7 Publishing System] Para insertar una imagen es necesario que esté activado y así tener acceso a la biblioteca de imágenes.

#### Recomendación

Incluya recomendaciones dentro de la prueba A/B (incluidas las actividades de asignación automática y segmentación automática) y de segmentación de experiencias (XT). Para obtener más información, consulte [Recommendations como oferta](/help/c-recommendations/recommendations-as-an-offer.md).

#### Fragmento de experiencia

Insertar fragmentos de experiencia creados en [!DNL Adobe Experience Manager](AEM)[!DNL Target] en actividades para ayudar en la optimización o personalización. Para obtener más información, consulte [Fragmentos de experiencia de AEM](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Reemplazar con

Las opciones disponibles son las siguientes:

#### Imagen

Selecciona una imagen distinta de la biblioteca de contenido. Las imágenes disponibles para intercambiar incluyen las imágenes cargadas en la carpeta de activos de Experience Cloud o en la biblioteca de contenido de Target.

Durante la creación inicial de la actividad, la URL mostrada no es la que se usa para la publicación. Al sincronizar la actividad, la URL se actualiza y se reemplaza por una URL de producción de Scene7.

Por ejemplo, la URL inicial puede ser como la del ejemplo siguiente:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

Tras sincronizar la actividad, la URL de publicación podría tener el aspecto siguiente:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations admite Reemplazar con etiquetas DIV, SECTION y ARTICLE.

**Nota:** Para intercambiar imágenes se requiere una cuenta de Adobe Scene7 Publishing System.

#### Oferta HTML

Seleccione una oferta distinta de la [!UICONTROL Biblioteca de contenido].

**Nota:**[!DNL Target] Las ofertas HTML se almacenan en servidores de

Una oferta de HTML puede tener un tamaño máximo de 256 kB.

#### Recomendación

Incluya recomendaciones dentro de la prueba A/B (incluidas las actividades de asignación automática y segmentación automática) y de segmentación de experiencias (XT). Para obtener más información, consulte [Recommendations como oferta](/help/c-recommendations/recommendations-as-an-offer.md).

#### Fragmento de experiencia

Insertar fragmentos de experiencia creados en [!DNL Adobe Experience Manager](AEM)[!DNL Target] en actividades para ayudar en la optimización o personalización. Para obtener más información, consulte [Fragmentos de experiencia de AEM](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Diseño

Las opciones disponibles son las siguientes:

#### Reorganizar

Arrastrar el elemento a otra ubicación dentro del mismo elemento principal o DIV. Otros elementos cambian de ubicación para dejar espacio al elemento que se ha cambiado de sitio.

**Nota:** El rastreo de clics no funcionará en los elementos que se hayan cambiado de posición.

#### Cambiar el tamaño

Cambia el tamaño de un elemento en la página. Al seleccionar [!UICONTROL Cambiar tamaño], se muestra un control en la esquina inferior derecha del elemento que permite arrastrar la esquina para cambiar el tamaño. Mantenga pulsada la tecla Mayús para conservar la misma relación de aspecto.

**Nota:** No se puede cambiar el tamaño de los elementos en línea.

#### Mover   {#move}

Mueve elementos en la página. A diferencia de [!UICONTROL Reorganizar], [!UICONTROL Mover] no desplaza otros elementos para conseguir espacio para el elemento que se va a mover. Use las teclas de dirección para ajustar el movimiento. (Mejora prevista: hacer que los elementos movidos no queden ocultos detrás de otros elementos).

En algunos casos, como cuando una restricción de CSS requiere que un elemento permanezca dentro de su elemento principal, no se puede mover el elemento fuera del elemento principal. Un elemento no se puede mover fuera de un contenedor que tenga la propiedad CSS siguiente: `overflow: hidden`.

#### Ocultar

Oculta el elemento. El espacio en blanco permanece, pero se elimina el contenido.

#### Eliminar

Elimina el elemento. Se elimina el espacio en blanco detrás de la imagen y el espacio donde se contrae el elemento.

**Nota:** Los artículos que hay en un mbox “clásico” (un mbox creado dentro de una campaña de Target Classic) no se pueden quitar mediante esta opción.

### Expandir sección

Selecciona el elemento principal además del elemento seleccionado originalmente. Al seleccionar un elemento principal, se seleccionan automáticamente todos los elementos secundarios de dicho elemento. Puede expandir la selección varias veces.

### Navegar al vínculo

Abre el destino del vínculo.

### Deshacer/rehacer

Deshace los cambios realizados en las actividades durante una sesión de edición. También puede rehacer cambios que haya deshecho anteriormente.

## Consideraciones {#considerations}

* Si una oferta contiene contenido HTML, consulte “Cómo at.js procesa ofertas con contenido HTML” en [Cómo funciona at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md#render) para obtener más información.

## Desplazamiento por elementos utilizando la ruta DOM {#dom-path}

Al hacer clic en un elemento de la página, aparece el menú de opciones de VEC. Además, al hacer clic en un elemento, la ruta DOM correspondiente se muestra en la parte inferior de la página.

![Ruta DOM](/help/c-experiences/c-visual-experience-composer/assets/dom-path.png)

Puede utilizar la ruta DOM para ver rápidamente información sobre el elemento seleccionado (tipo, ID y clase) y subir o bajar por la ruta DOM para seleccionar el elemento deseado.

Al pasar el ratón por encima de la ruta DOM, un cuadro azul resalta el elemento correspondiente del VEC. Al hacer clic en el elemento, un cuadro naranja resalta el elemento y se muestra el menú de opciones de VEC, como se explica más arriba.

Puede navegar fácilmente a cualquier elemento principal, del mismo nivel o secundario dentro del VEC utilizando la ruta DOM.

La función de ruta DOM también está disponible al configurar el [rastreo de clics](/help/c-activities/r-success-metrics/click-tracking.md).