---
keywords: opciones del compositor de experiencias visuales;opciones del compositor de experiencias visuales;opciones de experiencia;editar texto;editar html;editar texto/html;editar color de fondo;insertar elemento;editar vínculo;vínculo;vínculo del compositor de experiencias visuales;editar clase css;clase css;intercambiar oferta;intercambio de ofertas;intercambiar imagen;intercambio de imágenes;quitar elemento;eliminar elemento;ocultar elemento;ocultar elemento;reorganizar;mover elemento;mover elemento;cambiar tamaño elemento;cambiar tamaño elemento;elemento;expandir selección;expandir selección;navegar a este vínculo;vínculo navegar;navegar por vínculo;deshacer;rehacer;deshacer/rehacer;eventos personalizados;componentes web;decisión de oferta;offer decisioning
description: Explore las opciones disponibles en el  [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC).
title: ¿Cómo utilizo las opciones de [!UICONTROL Visual Experience Composer] (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: be9996c4dce0a3135a39fcbf0608b57b6e742ac3
workflow-type: tm+mt
source-wordcount: '2667'
ht-degree: 55%

---

# Opciones del Compositor de experiencias visuales

Al hacer clic en un elemento de página en el [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC), un menú muestra las opciones disponibles para ese tipo de elemento. Además, se muestra una ruta DOM en la parte inferior de la página que permite navegar fácilmente por la estructura de la página.

Las distintas acciones de [!UICONTROL Visual Experience Composer] (VEC) se agrupan en opciones de menú apropiadas para que su trabajo sea más rápido y eficiente:

![Menú Opciones de VEC](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>Las opciones disponibles dependen del tipo de actividad que cree o edite.

## [!UICONTROL Edit]

Las opciones disponibles son las siguientes:

### [!UICONTROL Text/HTML] {#edit-text-html}

Cambie el código HTML del elemento, como el texto de un área de texto, un botón o un vínculo.

Además del código HTML, puede editar e insertar JavaScript personalizado.

Hay varias opciones disponibles para aplicar formato de texto enriquecido al editar texto y HTML para las actividades [!UICONTROL A/B] y [!UICONTROL Experience Targeting]. Puede seleccionar un tipo de letra, elegir un estilo de letra y cambiar la alineación del texto, entre otras opciones estándar de formato de texto. Cuando modifica el código HTML, puede cambiar entre la vista de código y la vista de edición enriquecida del código HTML.

Se pueden anidar las siguientes etiquetas HTML5:

| Etiqueta | Etiquetas anidadas permitidas |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

### [!UICONTROL Background Color]

Use el selector de color para seleccionar o configurar un color de fondo. Puede seleccionar una muestra de colores y ajustarla con valores RGB o códigos hexadecimales de color. La “x” roja del selector de color define que el fondo sea transparente.

**Nota:** Esta opción no está disponible para los elementos en los que haya establecida una imagen de fondo.

### [!UICONTROL Styles] {#styles}

Utilice el panel [!UICONTROL Styles] para ver o editar el valor de los estilos existentes para el elemento seleccionado. También puede añadir estilo adicional.

Para acceder al panel [!UICONTROL Styles], haga clic en un elemento de página desde el VEC y, a continuación, haga clic en **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

El panel [!UICONTROL Styles] aparece a la derecha del VEC. El panel contiene una lista de estilos que le permite editar o agregar al elemento seleccionado. Un editor CSS en tiempo real permite ver cambios y agregar estilos si se siente cómodo utilizando hojas de estilo en cascada (CSS) o si recibe código de su desarrollador.

![Panel Estilos](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

Al aplicar diferentes estilos, siempre puede revertir los cambios haciendo clic en el icono [!UICONTROL Revert] que aparece en la esquina superior derecha del panel [!UICONTROL Styles] después de cambiar cualquier sección. Al hacer clic en el icono [!UICONTROL Revert] se revertirán todos los cambios en el panel de la sección actual.

Expanda cada sección para editar o agregar estilos, como se explica a continuación. Para guardar los cambios, haga clic en el icono [!UICONTROL Back] en la parte superior del panel para volver a la pantalla principal del panel y, a continuación, haga clic en **[!UICONTROL Save]**.

Los puntos azules en el panel principal y junto a cada opción en los distintos paneles de sección indican que ha cambiado los estilos correspondientes. Este indicador visual facilita la revisión de los cambios antes de hacer clic en [!UICONTROL Save].

>[!NOTE]
>
>Las acciones rápidas para cambios de diseño, color de fondo, cambio de tamaño y movimiento también están disponibles como acciones independientes en el menú VEC. Estas opciones se pueden utilizar como acciones independientes o puede utilizar el menú Estilos, tal como se explica aquí.

* **[!UICONTROL Background]**

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

* **[!UICONTROL Typography]**

  Cambie la tipografía de un elemento. Las ediciones tipográficas son rápidas y sencillas.

  Aunque el editor de texto enriquecido (Editar texto/HTML) está disponible para un mejor ajuste, las acciones rápidas para cambiar todo el elemento están disponibles a través de esta opción. Si desea aplicar cambios tipográficos solo a una parte del texto (no al texto completo), utilice el [editor de texto enriquecido](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).

  Puede editar los siguientes estilos tipográficos:

   * [!UICONTROL Font size]
   * [!UICONTROL Font weight]
   * [!UICONTROL Font style]
   * [!UICONTROL Color] (especifique el código de color o use el selector de color)
   * [!UICONTROL Word spacing]
   * [!UICONTROL Line height]
   * [!UICONTROL Text alignment]

* **[!UICONTROL Margin]**

  Cambie el margen del elemento seleccionado. Puede cambiar los márgenes izquierdo, derecho, inferior y superior.

  Haga clic en el icono desplegable de cada margen para elegir entre las siguientes opciones:

   * [!UICONTROL Auto]
   * [!UICONTROL Value] (arrastre el control deslizante para definir el margen o especificar el número de píxeles para cada margen)

  El margen admite valores positivos y negativos.

  Target también admite otras unidades de tamaño, como rem, pc, em. Para obtener más información sobre estas unidades, consulte [Consejos y trucos de hojas de estilo web CSS](https://www.w3.org/Style/Examples/007/units.en.html).

* **[!UICONTROL Padding]**

  Cambie el relleno del elemento seleccionado. Puede cambiar el relleno izquierdo, derecho, inferior y superior.

  Arrastre el control deslizante para definir el relleno o especifique el número de píxeles para el relleno.

  El relleno admite escalas de anchura a partir de 0.

  Target también admite [otras unidades de tamaño](https://www.w3.org/Style/Examples/007/units.en.html), como rem, pc, em.

* **[!UICONTROL Border]**

  Haga clic en los iconos de borde en la parte superior del panel para cambiar el borde del elemento seleccionado.

  Puede editar los estilos siguientes para cada borde (superior, derecho, inferior e izquierdo):

   * [!UICONTROL Border style] (ninguno, oculto, punteado, discontinuo, continuo o doble)
   * [!UICONTROL Border color] (especifique el código de color o use el selector de color)
   * [!UICONTROL Border width] (arrastre el control deslizante para seleccionar un ancho de borde o especificar el ancho en píxeles)

  El borde admite escalas de anchura a partir de 0.

  Target también admite [otras unidades de tamaño](https://www.w3.org/Style/Examples/007/units.en.html), como rem, pc, em.

* **[!UICONTROL Position]**

  Mueva el elemento seleccionado desde su posición actual. Puede cambiar la posición superior, inferior, izquierda, derecha y [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) del elemento.

  Haga clic en la lista desplegable [!UICONTROL Static] para elegir entre las siguientes opciones de posición:

   * [!UICONTROL Static]
   * [!UICONTROL Relative]
   * [!UICONTROL Absolute]
   * [!UICONTROL Sticky]
   * [!UICONTROL Fixed]

  Haga clic en el icono desplegable de cada posición para elegir entre las siguientes opciones:

   * [!UICONTROL Auto]
   * [!UICONTROL Value] (arrastre el control deslizante para colocar el elemento o especificar el número de píxeles que desea mover el elemento)

  La posición admite valores positivos y negativos.

  Target también admite [otras unidades de tamaño](https://www.w3.org/Style/Examples/007/units.en.html), como rem, pc, em.

* **[!UICONTROL Size]**

  Cambie la anchura y la altura del elemento seleccionado.

  Haga clic en el icono desplegable al lado de [!UICONTROL Width] y [!UICONTROL Height] para elegir entre las siguientes opciones:

   * [!UICONTROL Auto]
   * [!UICONTROL Value] (arrastre el control deslizante para cambiar el tamaño del elemento o especificar el número de píxeles para cada dimensión)

* **[!UICONTROL Filter]**

  Arrastre el control deslizante para cada opción de filtro o especifique el porcentaje que desee:

   * [!UICONTROL Sepia]
   * [!UICONTROL Contrast]
   * [!UICONTROL Brightness]
   * [!UICONTROL GrayScale]
   * [!UICONTROL Blur]
   * [!UICONTROL Opacity]
   * [!UICONTROL Invert]
*[!UICONTROL &#x200B; Hue-rotate]
   * [!UICONTROL Saturate]

* **[!UICONTROL CSS Editor]**

  El editor CSS en tiempo real permite ver cambios y agregar estilos si se siente cómodo utilizando hojas de estilo en cascada (CSS) o si recibe código de su desarrollador.

  El editor CSS muestra los cambios realizados en el panel Estilos. Como se muestra en la siguiente ilustración, se han cambiado el tamaño de fuente, el borde superior y el tamaño de la imagen:

  ![Editor CSS con cambios](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

  Observe los puntos azules junto a las opciones [!UICONTROL Typography], [!UICONTROL Border] y [!UICONTROL Size] de la ilustración anterior. Estos puntos indican que ha cambiado estas secciones. Si abre estos paneles de sección, aparecen puntos azules junto a las opciones específicas que ha modificado.

  Puede escribir su propio código si el estilo deseado no está disponible de forma predeterminada en [!UICONTROL Styles].

  El editor CSS muestra solo los detalles de la sesión actual. Si guarda cambios y vuelve a abrir el editor, los detalles sobre el cambio anterior no se muestran en el editor, aunque vuelva a seleccionar el mismo elemento.

  >[!IMPORTANT]
  >
  >Puede aplicar una imagen de fondo mediante el editor CSS, pero puede provocar parpadeos. Pruebe los cambios antes de la implementación.

### [!UICONTROL CSS Class]

Especifica la clase CSS predefinida usada para el elemento. Si selecciona más de un elemento, separe varias clases CSS con un espacio.

Disponible para las actividades [!UICONTROL A/B], [!UICONTROL Automated Personalization] y [!UICONTROL Multivariate Test].

### [!UICONTROL Link]

Cambia la dirección URL del vínculo.

Use Editar vínculo para actualizar el selector y que señale al mismo elemento de imagen. Sin embargo, no se permite vincular a otro elemento de imagen. Para vincular a un elemento de imagen diferente, elimine la acción original del editor de código y utilice [!UICONTROL Visual Experience Composer] para aplicar la acción al otro elemento de imagen.

## [!UICONTROL Insert Before]

Las opciones disponibles son las siguientes:

### [!UICONTROL Offer Decision]

Agregue una [oferta creada en [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} para presentar la mejor oferta y experiencia a sus clientes con offer decisioning.

**Nota:** Esta opción solo está disponible al editar o crear [actividades manuales [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) o [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT). Esta opción no está disponible para otros tipos de actividades.

Para obtener más información, consulte [Usar decisiones de oferta](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML] y [!UICONTROL Text]

Agrega cualquier tipo de elemento a la página además de modificar el contenido existente. Agregue texto, código, listas, etc. para crear experiencias que probar completamente diferentes.

Seleccione un elemento en la página, haga clic en [!UICONTROL Insert Before] y elija si quiere insertar una imagen, un HTML o un texto. El elemento insertado aparece antes del elemento seleccionado.

El comportamiento del elemento insertado depende de la estructura de la página, el CSS y otras opciones de configuración de la página. Para que la página se muestre correctamente, es necesario que el código HTML sea válido. Después de insertar un elemento, pruebe siempre la página para asegurarse de que se muestra correctamente.

[!UICONTROL Recommendations] admite [!UICONTROL Insert Before] el contenido de las etiquetas DIV, SECTION y ARTICLE.

**Nota:**&#x200B;[!DNL Adobe Scene7 Publishing System] Para insertar una imagen es necesario que esté activado y así tener acceso a la biblioteca de imágenes.

### Recomendación

Incluya recomendaciones dentro de la prueba A/B (incluidas las actividades de asignación automática y segmentación automática) y de segmentación de experiencias (XT). Para obtener más información, consulte [Recommendations como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insertar fragmentos de experiencia creados en [!DNL Adobe Experience Manager] (AEM) [!DNL Target] en actividades para ayudar en la optimización o personalización. Para obtener más información, consulte [Fragmentos de experiencia de AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Insert After]

Las opciones disponibles son las siguientes:

### [!UICONTROL Offer Decision]

Agregue una [oferta creada en [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} para presentar la mejor oferta y experiencia a sus clientes con offer decisioning.

**Nota:** Esta opción solo está disponible al editar o crear [actividades manuales [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) o [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT). Esta opción no está disponible para otros tipos de actividades.

Para obtener más información, consulte [Usar decisiones de oferta](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML] y [!UICONTROL Text]

Agrega cualquier tipo de elemento a la página además de modificar el contenido existente. Agregue texto, código, listas, etc. para crear experiencias que probar completamente diferentes.

Seleccione un elemento en la página, haga clic en [!UICONTROL Insert After] y elija si quiere insertar una imagen, un HTML o un texto. El elemento insertado aparece a continuación del elemento seleccionado.

El comportamiento del elemento insertado depende de la estructura de la página, el CSS y otras opciones de configuración de la página. Para que la página se muestre correctamente, es necesario que el código HTML sea válido. Después de insertar un elemento, pruebe siempre la página para asegurarse de que se muestra correctamente.

[!UICONTROL Recommendations] admite [!UICONTROL Insert After] el contenido de las etiquetas DIV, SECTION y ARTICLE.

**Nota:**&#x200B;[!DNL Adobe Scene7 Publishing System] Para insertar una imagen es necesario que esté activado y así tener acceso a la biblioteca de imágenes.

### Recomendación

Incluya recomendaciones dentro de la prueba A/B (incluidas las actividades de asignación automática y segmentación automática) y de segmentación de experiencias (XT). Para obtener más información, consulte [Recommendations como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insertar fragmentos de experiencia creados en [!DNL Adobe Experience Manager] (AEM) [!DNL Target] en actividades para ayudar en la optimización o personalización. Para obtener más información, consulte [Fragmentos de experiencia de AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Replace Content]

Las opciones disponibles son las siguientes:

### [!UICONTROL Offer Decision]

Agregue una [oferta creada en [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} para presentar la mejor oferta y experiencia a sus clientes con offer decisioning.

**Nota:** Esta opción solo está disponible al editar o crear [actividades manuales [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) o [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT). Esta opción no está disponible para otros tipos de actividades.

Para obtener más información, consulte [Usar decisiones de oferta](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image]

Selecciona una imagen distinta de la biblioteca de contenido. Las imágenes disponibles para intercambiar incluyen las imágenes cargadas en la carpeta de activos de Experience Cloud o en la biblioteca de contenido de Target.

Durante la creación inicial de la actividad, la URL mostrada no es la que se usa para la publicación. Al sincronizar la actividad, la URL se actualiza y se reemplaza por una URL de producción de Scene7.

Por ejemplo, la URL inicial puede ser como la del ejemplo siguiente:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

Tras sincronizar la actividad, la URL de publicación podría tener el aspecto siguiente:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations admite Reemplazar con etiquetas DIV, SECTION y ARTICLE.

**Nota:** Para intercambiar imágenes se requiere una cuenta de Adobe Scene7 Publishing System.

### [!UICONTROL HTML Offer]

Seleccione una oferta diferente de [!UICONTROL Content Library].

**Nota:**&#x200B;[!DNL Target] Las ofertas HTML se almacenan en servidores de

La oferta de HTML puede alcanzar los 256 KB.

### Recomendación

Incluya recomendaciones dentro de la prueba A/B (incluidas las actividades de asignación automática y segmentación automática) y de segmentación de experiencias (XT). Para obtener más información, consulte [Recommendations como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insertar fragmentos de experiencia creados en [!DNL Adobe Experience Manager] (AEM) [!DNL Target] en actividades para ayudar en la optimización o personalización. Para obtener más información, consulte [Fragmentos de experiencia de AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Layout]

Las opciones disponibles son las siguientes:

### [!UICONTROL Rearrange]

Arrastrar el elemento a otra ubicación dentro del mismo elemento principal o DIV. Otros elementos cambian de ubicación para dejar espacio al elemento que se ha cambiado de sitio.

**Nota**: el rastreo de clics no funciona en elementos que se han cambiado de sitio.

Actualmente, ciertas acciones del VEC, como [!UICONTROL Rearrange] y [!UICONTROL Move], suponen que los elementos del mismo nivel de los elementos principales de origen y destino están completamente cargados. Si la carga diferida se produce en los elementos DOM principales (origen o destino), estas acciones del VEC pueden provocar un comportamiento incoherente. Estamos trabajando en un enfoque más confiable para hacer que las acciones del VEC funcionen en elementos DOM cargados de forma diferida. Como solución temporal, puede usar [!UICONTROL Custom Code] en estos escenarios para procesar sus experiencias.

### [!UICONTROL Resize]

Cambia el tamaño de un elemento en la página. Al seleccionar [!UICONTROL Resize], aparece un controlador en la esquina inferior derecha del elemento que le permite arrastrar la esquina para cambiar su tamaño. Mantenga pulsada la tecla Mayús para conservar la misma relación de aspecto.

**Nota:** No se puede cambiar el tamaño de los elementos en línea.

### [!UICONTROL Move] {#move}

Mueve elementos en la página. A diferencia de la opción [!UICONTROL Rearrange], [!UICONTROL Move] no desplaza otros elementos para dejar espacio al elemento que se está moviendo. Use las teclas de dirección para ajustar el movimiento. (Mejora prevista: compatibilidad para garantizar que los elementos movidos no se oculten detrás de otros elementos).

En determinadas situaciones, como cuando una restricción de CSS requiere que un elemento permanezca dentro de su elemento principal, no se puede mover el elemento fuera del elemento principal. Un elemento no se puede mover fuera de un contenedor que tenga la propiedad CSS siguiente: `overflow: hidden`.

Consulte [!UICONTROL Rearrange] más arriba para obtener más información sobre el comportamiento incoherente con las acciones [!UICONTROL Move] y [!UICONTROL Rearrange] debido a la carga lenta de elementos DOM.

### [!UICONTROL Hide]

Oculta el elemento. El espacio en blanco permanece, pero se elimina el contenido.

### [!UICONTROL Remove]

Elimina el elemento. Se elimina el espacio en blanco detrás de la imagen y el espacio donde se contrae el elemento.

**Nota:** Los artículos que hay en un mbox “clásico” (un mbox creado dentro de una campaña de Target Classic) no se pueden quitar mediante esta opción.

## [!UICONTROL Expand Section]

Selecciona el elemento principal además del elemento seleccionado originalmente. Al seleccionar un elemento principal, se seleccionan automáticamente todos los elementos secundarios de dicho elemento. Puede expandir la selección varias veces.

## [!UICONTROL Navigate to Link]

Abre el destino del vínculo.

## [!UICONTROL Undo]/[!UICONTROL Redo]

Deshace los cambios realizados en las actividades durante una sesión de edición. También puede rehacer cambios que haya deshecho anteriormente.

## Consideraciones {#considerations}

* Si una oferta contiene contenido de HTML, consulte &quot;Cómo at.js procesa ofertas con contenido de HTML&quot; en [Cómo funciona at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html){target=_blank} para obtener más información.

## Compatibilidad con elementos personalizados {#custom}

El VEC admite [Componentes web](https://developer.mozilla.org/es/docs/Web/Web_Components) para permitirle crear y probar experiencias y ofertas personalizadas en elementos personalizados y en elementos dentro de elementos personalizados. Esta funcionalidad está disponible en el VEC para todos los tipos de actividad [!DNL Target].

>[!NOTE]
>
>La compatibilidad con VEC para elementos personalizados se admite en [at.js versión](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} 2.7.0 (o posterior){target=_blank}. Asegúrese de que el sitio web tenga implementada la versión requerida. Si utiliza la [extensión de ayuda del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md), también debe tener implementada la versión requerida de at.js. Las opciones de VEC descritas anteriormente no están visibles y disponibles para su uso con versiones no compatibles de at.js.
>
>La compatibilidad con VEC para elementos personalizados actualmente no es compatible con [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=es){target=_blank}.

La mayoría de las acciones del VEC son compatibles con los eventos personalizados y dentro de los eventos personalizados, con las siguientes excepciones:

Las siguientes acciones no están disponibles en los elementos personalizados:

* [!UICONTROL Edit]
   * [!UICONTROL Text/HTML]
   * [!UICONTROL Link]
   * [!UICONTROL Edit Source]

* [!UICONTROL Replace Content]

La siguiente acción no está disponible dentro de los elementos personalizados:

* [!UICONTROL Layout]
   * [!UICONTROL Rearrange]

## Desplazamiento por elementos utilizando la ruta DOM {#dom-path}

Al hacer clic en un elemento de la página, aparece el menú de opciones de VEC. Además, al hacer clic en un elemento, la ruta DOM correspondiente se muestra en la parte inferior de la página.

![Ruta DOM](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path.png)

Puede utilizar la ruta DOM para ver rápidamente información sobre el elemento seleccionado (tipo, ID y clase) y subir o bajar por la ruta DOM para seleccionar el elemento deseado.

Al pasar el ratón por encima de la ruta DOM, un cuadro azul resalta el elemento correspondiente del VEC. Al hacer clic en el elemento, un cuadro naranja resalta el elemento y se muestra el menú de opciones de VEC, como se explica más arriba.

Puede navegar fácilmente a cualquier elemento principal, del mismo nivel o secundario dentro del VEC utilizando la ruta DOM.

La función de ruta DOM también está disponible al configurar el [rastreo de clics](/help/main/c-activities/r-success-metrics/click-tracking.md).
