---
keywords: opciones del compositor de experiencias visuales;opciones del compositor de experiencias visuales;opciones de experiencia;editar texto;editar html;editar texto/html;editar color de fondo;insertar elemento;editar vínculo;vínculo del compositor de experiencias visuales;editar clase css;clase css;intercambiar oferta;intercambio de ofertas;intercambiar imagen;intercambio de imágenes;eliminar elemento;eliminar elemento;ocultar elemento;ocultar elemento;reorganizar;mover elemento;mover elemento;cambiar tamaño elemento;cambiar tamaño elemento;elemento;ampliar selección;expandir selección;navegar a este vínculo;navegar vínculo;navegar por vínculo;deshacer;rehacer;deshacer/rehacer;eventos personalizados;componentes web;decisión de oferta
description: Explore las opciones disponibles en el  [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC).
title: ¿Cómo utilizo las opciones de [!UICONTROL Visual Experience Composer] (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: c8cbf4998c304910a63e31acc3ec93a04ac652ae
workflow-type: tm+mt
source-wordcount: '2047'
ht-degree: 8%

---

# [!UICONTROL Visual Experience Composer] opciones

La versión de [!DNL Adobe Target Standard/Premium] 25.2.1 (del 17 de febrero de 2015) presenta un [!UICONTROL Visual Experience Composer] (VEC) actualizado. Este artículo explica la interfaz de usuario actualizada y sus opciones.

>[!TIP]
>
>Para saber en qué se diferencia el VEC actualizado del VEC heredado, consulte [Cambios del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md).

>[!IMPORTANT]
>
>El(la) [!UICONTROL Visual Editing Composer] actualizado(a) requiere la extensión [!DNL Adobe Experience Cloud] [[!UICONTROL Visual Editing Helper] ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) disponible(a) en el [!DNL Chrome Web Store].

El VEC se muestra cuando crea o edita una actividad existente.

![Compositor de experiencias visuales (VEC)](/help/main/c-experiences/c-visual-experience-composer/assets/new-vec.png)

## Información general de VEC UI

Las siguientes secciones explican las opciones disponibles en el VEC actualizado para una actividad [!UICONTROL A/B Test]. Las opciones varían según el tipo de actividad.

### Carril [!UICONTROL Experiences]

El carril [!UICONTROL Experiences] se muestra en el carril izquierdo del VEC.

![Carril de experiencias](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

Puede ver, crear, cambiar el nombre o quitar experiencias con el carril [!UICONTROL Experiences].

Las siguientes opciones están disponibles en el carril [!UICONTROL Experiences]:

* **Ver una experiencia**: para ver una experiencia, haga clic en la experiencia que desee para mostrarla en el lienzo [!UICONTROL Design].
* **Agregar una experiencia**: Haga clic en el icono **[!UICONTROL Add]** ( ![Agregar icono](/help/main/assets/icons/Add.svg) ) para agregar una nueva experiencia. Configure la nueva experiencia como desee.
* **Cambiar el nombre de una experiencia**: haga clic en el icono **[!UICONTROL Rename]** ( ![Cambiar nombre](/help/main/assets/icons/Rename.svg) ) para mostrar el cuadro de diálogo [!UICONTROL Rename Experience]. Especifique el nuevo nombre y haga clic en **[!UICONTROL Save]**.
* **Duplicar, eliminar o redirigir una experiencia**: haga clic en el icono **[!UICONTROL More Actions]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmall.svg) ) y, a continuación, elija **[!UICONTROL Duplicate]**, **[!UICONTROL Delete]** o **[!UICONTROL Redirect to URL]**.

### Configuración de actividades {#settings}

Haga clic en el icono [!UICONTROL Configure] ( ![Icono de configuración](/help/main/assets/icons/Setting.svg) ) que se muestra en la parte superior del lienzo [!UICONTROL Design] para mostrar el menú de propiedades de la actividad.

![Opciones de configuración de actividades](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

Las opciones disponibles son las siguientes:

* **[!UICONTROL Properties]**: asigne propiedades a la actividad o elimine propiedades de la actividad. [!UICONTROL Properties] es una característica ([[!DNL Target Premium]](/help/main/c-intro/intro.md#premium)). Para obtener más información, consulte [Permisos de usuario de Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).
* **[!UICONTROL Page Delivery]**: incluya la misma experiencia en páginas similares del sitio. Utilice una plantilla de página para dar estructura a las páginas o, si las páginas contienen elementos similares, para probar variaciones en elementos de página de estructura similar o en todo el dominio. Para obtener más información, vea [Incluir la misma experiencia en páginas similares](/help/main/c-experiences/c-visual-experience-composer/temtest.md).
* **[!UICONTROL Site Preferences]**: configure las preferencias de su sitio para especificar cómo [!DNL Target] genera los selectores CSS. Para obtener más información, consulte _selectores CSS_ en [Configurar [!UICONTROL Visual Experience Composer]](/help/main/administrating-target/visual-experience-composer-set-up.md).
* **Agregar páginas adicionales**: agregue páginas adicionales a la actividad para crear una actividad de varias páginas que le permita crear una historia en varias páginas, con un diseño que sea específico de cada página. Para obtener más información, consulte [Actividad multipágina](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md).
* **Audiencia única**: use una sola audiencia para la actividad.
* **Varias audiencias**: asigne varias audiencias a la actividad. Haga clic en el icono Agregar audiencias ( ![Agregar icono](/help/main/assets/icons/Add.svg) ) y, a continuación, seleccione una o varias audiencias de la lista. También puede [combinar audiencias](/help/main/c-target/combining-multiple-audiences.md) o [crear una audiencia nueva](/help/main/c-target/c-audiences/create-audience.md) desde el cuadro de diálogo [!UICONTROL Add Audiences].

### Modos [!UICONTROL Design]/[!UICONTROL Browse]

Utilice los conmutadores [!UICONTROL Design]/[!UICONTROL Browse] que se muestran en la parte superior del lienzo de diseño para cambiar entre el modo de diseño y el modo de exploración.

![Alternadores de diseño y exploración](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

Utilice el modo [!UICONTROL Browse] para navegar por el sitio y elegir la vista o la página que desee actualizar. Vuelva al modo [!UICONTROL Design] para agregar o editar los cambios.

### [!UICONTROL Undo]/[!UICONTROL Redo]

Para deshacer los cambios, haga clic en el icono [!UICONTROL Undo] ( ![Deshacer icono](/help/main/assets/icons/Undo.svg) ).

![Icono Deshacer en VEC](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

Para rehacer una acción, expanda el grupo de botones Deshacer/[!UICONTROL Redo] y elija [!UICONTROL Redo].

### Carril [!UICONTROL Components]

Puede agregar varios componentes a la página web y editarlos según sea necesario mediante el nuevo carril [!UICONTROL Components].

![Carril de componentes](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

>[!NOTE]
>
>Si ve el carril [!UICONTROL Modifications] en esta área en lugar del carril [!UICONTROL Components], haga clic en el icono **[!UICONTROL Show Components]** ( ![Mostrar icono de componentes](/help/main/assets/icons/Add.svg) ). El icono [!UICONTROL Show Components] ( ![Mostrar icono de componentes](/help/main/assets/icons/Add.svg) ) y el icono [!UICONTROL Show Modifications] ( ![Mostrar carril de modificaciones](/help/main/assets/icons/History.svg) ) actúan como alternadores para mostrar las opciones adecuadas.
>
>Para contraer el carril [!UICONTROL Components] y ampliar el lienzo [!UICONTROL Design], mientras el carril [!UICONTROL Components] está abierto, haga clic en el icono ( ![Mostrar icono de componentes](/help/main/assets/icons/Add.svg) ).

Para añadir un componente nuevo a una experiencia:

1. Haga clic en el componente que desee añadir para resaltarlo.

   Los componentes disponibles se agrupan en contenedores lógicos:

   * [!UICONTROL Basic]
      * [!UICONTROL Divider]
      * [!UICONTROL HTML]
      * [!UICONTROL Image]
   * [!UICONTROL Text]
      * [!UICONTROL Heading]
      * [!UICONTROL Paragraph]
      * [!UICONTROL Link]
   * [!UICONTROL Dynamic]
      * [[!UICONTROL Recommendation]](/help/main/c-recommendations/recommendations-as-an-offer.md)
      * [[!UICONTROL Experience Fragment]](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md)
      * [[!UICONTROL HTML Offer]](/help/main/c-experiences/c-manage-content/manage-content.md)

1. Arrastre el componente sobre un elemento de página existente en el lienzo [!UICONTROL Design].
1. Seleccione para reemplazar el elemento seleccionado o para insertar el componente antes de o después del elemento seleccionado.

### Carril [!UICONTROL Modifications]

Para abrir el carril [!UICONTROL Modifications], haga clic en el icono [!UICONTROL Show Modifications] ( ![Mostrar modificaciones](/help/main/assets/icons/History.svg) ) en el carril [!UICONTROL Components].

![Carril de modificaciones](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

>[!NOTE]
>
>El icono [!UICONTROL Show Components] ( ![Mostrar icono de componentes](/help/main/assets/icons/Add.svg) ) y el icono [!UICONTROL Show Modifications] ( ![Mostrar carril de modificaciones](/help/main/assets/icons/History.svg) ) actúan como alternadores para mostrar las opciones adecuadas.
>
>Para contraer el carril [!UICONTROL Modifications] y ampliar el lienzo [!UICONTROL Design], mientras el carril [!UICONTROL Modifications] está abierto, haga clic en el icono [!UICONTROL Show Modifications] ( ![Mostrar modificaciones](/help/main/assets/icons/History.svg) ).

El carril [!UICONTROL Modifications] muestra todos los cambios realizados en su página en [!UICONTROL Visual Experience Composer] (VEC) y le permite realizar cambios adicionales (como selector de CSS, mbox y código personalizado).

Haga clic en el icono **[!UICONTROL More Options]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmall.svg) ) en el encabezado del carril para agregar una modificación, eliminar todas las modificaciones o eliminar todas las modificaciones no válidas. Haga clic en [!UICONTROL Select] para realizar operaciones masivas: [!UICONTROL Apply to All Pages] o [!UICONTROL Delete].

Haga clic en el icono **[!UICONTROL More Options]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmall.svg) ) junto a cada modificación para ver su información, eliminar la modificación o aplicar la modificación a más vistas.

### [!UICONTROL Design] lienzo

El lienzo [!UICONTROL Design] le permite seleccionar ventanillas móviles, incluidas las de ajuste a pantalla, [!UICONTROL Desktop], [!UICONTROL Tablet], [!UICONTROL Mobile Landscape] y [!UICONTROL Mobile Portrait]. De manera predeterminada, el lienzo ajusta la página a la pantalla junto con las ventanillas móviles definidas en la sección [Administración](/help/main/administrating-target/visual-experience-composer-set-up.md).

![Opciones de ventanilla](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

También puede acercar o alejar la vista haciendo clic en el icono apropiado ( ![Icono de acercar](/help/main/assets/icons/ZoomIn.svg) o ![icono de alejar](/help/main/assets/icons/ZoomOut.svg) ).

Al hacer clic en un elemento de página en el lienzo [!UICONTROL Design], un menú muestra las opciones disponibles para ese tipo de elemento. Además, se muestra una ruta DOM en la parte inferior de la página que permite navegar fácilmente por la estructura de la página.

Las distintas acciones de [!UICONTROL Visual Experience Composer] (VEC) se agrupan en opciones de menú apropiadas para que su trabajo sea más rápido y eficiente:

![Menú Opciones de VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-options.png)

>[!NOTE]
>
>Las opciones disponibles dependen del tipo de actividad y del elemento que esté creando o editando. Para obtener más información sobre la edición de imágenes y ofertas en una actividad [!UICONTROL A/B Test], consulte [Editar elementos usando el lienzo [!UICONTROL Design]](#design) a continuación.

### Carril [!UICONTROL Properties]

El carril [!UICONTROL Properties] le permite cambiar las propiedades de los elementos seleccionados en la página, ya sean estos elementos HTML u objetos específicos de [!DNL Target], como recomendaciones u ofertas.

![Carril de propiedades](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

Haga clic en los iconos de la parte superior del carril para editar el código HTML o eliminar, duplicar u ocultar elementos. Los cambios aparecerán en el carril [!UICONTROL Modifications].

El carril [!UICONTROL Properties] se puede contraer en el carril derecho para permitirle ocultar el lienzo de diseño y ampliar el lienzo de diseño. Haga clic en el icono [!UICONTROL Show/Hide Properties] ( ![icono Propiedades](/help/main/assets/icons/Propertie.svg) ) a la derecha del carril para contraer o mostrar el carril [!UICONTROL Properties].

## Editar elementos utilizando el lienzo [!UICONTROL Design] {#design}

Las secciones siguientes muestran cómo editar imágenes y texto en el lienzo [!UICONTROL Design]. El lienzo Diseño, junto con los carriles Componentes, Modificaciones y Propiedades, le proporcionan potentes herramientas que le permiten crear fácilmente experiencias para sus actividades.

### Opciones de imagen

Si hace clic en una imagen en una actividad [!UICONTROL A/B Test], el VEC tiene un aspecto similar al de la siguiente ilustración:

![VEC con imagen seleccionada](/help/main/c-experiences/c-visual-experience-composer/assets/vec-image.png)

Seleccione componentes del marco [!UICONTROL Components] del lado izquierdo para insertar los siguientes elementos:

* Básico (divisor, HTML, imagen).
* Texto (encabezado, párrafo, vínculo).
* Dinámico ([Recomendación](/help/main/c-recommendations/recommendations-as-an-offer.md), [Fragmento de experiencia](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), oferta de HTML).

El menú en la parte superior de la imagen le permite hacer lo siguiente:

* Insertar un vínculo ( ![Icono Insertar vínculo](/help/main/assets/icons/Link.svg) ).
* Cambiar la imagen ( ![Elija el icono Imagen](/help/main/assets/icons/Images.svg) ).
* Agregar personalización ( ![Agregar icono de Personalization](/help/main/assets/icons/PersonalizationField.svg) ).
* Eliminar la imagen ( ![Icono Eliminar](/help/main/assets/icons/Delete.svg) ).

El panel [!UICONTROL Properties] de la derecha permite configurar aún más las propiedades de la imagen.

Los iconos de la parte superior del marco permiten hacer lo siguiente:

* Edite el HTML ( ![Insertar icono de HTML](/help/main/assets/icons/Code.svg) ). Consulte [Editar HTML](#html) más abajo para obtener más información.
* Duplique la imagen ( ![Icono duplicado](/help/main/assets/icons/Code.svg) ).
* Eliminar la imagen ( ![Icono Eliminar](/help/main/assets/icons/Delete.svg) ).
* Ocultar la imagen ( ![Ocultar icono](/help/main/assets/icons/VisibilityOff.svg) ).

Las opciones del marco derecho permiten hacer lo siguiente:

* Edite la clase CSS.
* Configure las propiedades de la imagen (origen, título, texto alternativo).
* Edite la dirección URL del vínculo.
* Configure el tamaño de la imagen (altura y anchura). Haga clic en [!UICONTROL Show Advanced Options] para configurar el tamaño, la anchura, la altura, el desbordamiento y el ajuste de objeto mínimos y máximos de la imagen.
* Configure la posición de la imagen en la página (absoluta, fija, relativa, estática o fija).
* Configure el espaciado del elemento, incluidos el margen y el relleno.
* Configure los efectos del elemento (opacidad). Haga clic en [!UICONTROL Show Advanced Options] para configurar los valores de sepia, escala de grises, contraste, brillo y desenfoque de la imagen. También puede invertir o rotar la imagen.
* Configure los estilos en línea de la imagen.

### Opciones de texto

Si hace clic en texto en una actividad [!UICONTROL A/B Test], el VEC tiene un aspecto similar al de la siguiente ilustración:

![VEC con texto seleccionado](/help/main/c-experiences/c-visual-experience-composer/assets/vec-text.png)

Seleccione componentes del marco [!UICONTROL Components] del lado izquierdo para insertar los siguientes elementos:

* Básico (divisor, HTML, imagen).
* Texto (encabezado, párrafo, vínculo).
* Dinámico ([Recomendación](/help/main/c-recommendations/recommendations-as-an-offer.md), [Fragmento de experiencia](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), oferta de HTML).

Haga clic en el icono [!UICONTROL Show Modifications] ( ![Mostrar modificaciones](/help/main/assets/icons/History.svg) ) para mostrar las modificaciones a la experiencia.

El menú en la parte superior del elemento de texto permite hacer lo siguiente:

* Configure las propiedades del texto (nivel de encabezado, párrafo, comilla de bloque o monoespacio)
* Seleccione el color del texto ( ![icono Color de texto](/help/main/assets/icons/TextColor.svg) )
* Configure los atributos del texto (negrita, cursiva, subrayado o tachado) ( ![Elija el icono Atributos de texto](/help/main/assets/icons/Text.svg) ).
* Configure la alineación del texto (izquierda, centro, derecha, justificar) ( ![Icono Alineación de texto](/help/main/assets/icons/TextAlignCenter.svg) ).
* Insertar un vínculo ( ![Icono Insertar vínculo](/help/main/assets/icons/Link.svg) ).
* Reemplace el contenido por una oferta de HTML, [Fragmento de experiencia](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) o [Recomendación](/help/main/c-recommendations/recommendations-as-an-offer.md).
* Edite el HTML ( ![Insertar icono de HTML](/help/main/assets/icons/Code.svg) ).
* Agregar personalización ( ![Agregar icono de Personalization](/help/main/assets/icons/PersonalizationField.svg) ).
* Eliminar la imagen ( ![Icono Eliminar](/help/main/assets/icons/Delete.svg) ).

El carril [!UICONTROL Properties] del lado derecho permite configurar aún más las propiedades del texto.

Los iconos de la parte superior del marco permiten hacer lo siguiente:

* Edite el HTML ( ![Insertar icono de HTML](/help/main/assets/icons/Code.svg) ). Consulte [Editar HTML](#html) más abajo para obtener más información.
* Duplicar el texto ( ![Icono de duplicado](/help/main/assets/icons/Code.svg) ).
* Eliminar el texto ( ![Icono Eliminar](/help/main/assets/icons/Delete.svg) ).
* Ocultar el texto ( ![Ocultar icono](/help/main/assets/icons/VisibilityOff.svg) ).

Las opciones del marco derecho permiten hacer lo siguiente:

* Edite la clase CSS.
* Configure el color de fondo y la imagen del texto.
* Configure la tipografía del texto (estilo de encabezado, tamaño de fuente, grosor de fuente, altura de línea, alineación, color de texto, estilo de texto (negrita, cursiva, subrayado o tachado)).
* Configure listas, incluidas las listas con viñetas, numeradas o A,B,C.
* Elija el color del borde.
* Configure el tamaño del cuadro de texto (alto y ancho). Haga clic en [!UICONTROL Show Advanced Options] para configurar el tamaño, la anchura, la altura, el desbordamiento y el ajuste de objeto mínimos y máximos del cuadro de texto.
* Configure la posición del cuadro de texto en la página (absoluta, fija, relativa, estática o fija) y establezca el número de píxeles desde arriba, derecha, abajo e izquierda.
* Configure el espaciado del elemento, incluidos el margen y el relleno.
* Configure los efectos del elemento (opacidad). Haga clic en [!UICONTROL Show Advanced Options] para configurar los valores de sepia, escala de grises, contraste, brillo y desenfoque de la imagen. También puede invertir o rotar el texto.
* Configure los estilos en línea.

## Editar HTML

Además del código HTML, puede editar e insertar JavaScript personalizado.

Hay varias opciones disponibles para aplicar formato de texto enriquecido al editar texto y HTML para las actividades [!UICONTROL A/B] y [!UICONTROL Experience Targeting]. Puede seleccionar un tipo de letra, elegir un estilo de letra y cambiar la alineación del texto, entre otras opciones estándar de formato de texto. Al modificar HTML, puede alternar entre la vista de código y la vista de edición enriquecida de HTML.

Se pueden anidar las siguientes etiquetas HTML5:

| Etiqueta | Etiquetas anidadas permitidas |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

## Desplazamiento por elementos utilizando la ruta DOM {#dom-path}

Al hacer clic en un elemento de la página, aparece el menú de opciones de VEC. Además, al hacer clic en un elemento, la ruta DOM correspondiente se muestra en la parte inferior de la página.

![Ruta DOM](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path-refresh.png)

Si no ve la ruta DOM, haga clic en el icono [!UICONTROL Show DOM] ( ![Mostrar icono DOM](/help/main/assets/icons/LayersBringToFront.svg) ).

Puede utilizar la ruta DOM para ver rápidamente información sobre el elemento seleccionado (tipo, ID y clase) y subir o bajar por la ruta DOM para seleccionar el elemento deseado.

<!--When you hover over the DOM path, a blue box highlights the corresponding element in the VEC. When you click the element, an orange box highlights the element and the VEC options menu displays, as explained above.-->

Puede navegar fácilmente a cualquier elemento principal, del mismo nivel o secundario dentro del VEC utilizando la ruta DOM.

La función de ruta DOM también está disponible al configurar el [rastreo de clics](/help/main/c-activities/r-success-metrics/click-tracking.md).

## Más información sobre la IU actualizada

* [[!DNL Target Standard/Premium] 25.2.1 (17 de febrero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Activities], [!UICONTROL Recommendations] y [!UICONTROL Visual Experience Composer] (VEC).

* [[!DNL Target Standard/Premium] 25.1.1 (9 de enero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Offers Library].

* [Comprender la [!DNL Target] IU](/help/main/c-intro/understand-the-target-ui.md): Proporciona una breve descripción general para ayudarle a familiarizarse con [!DNL Target] y proporciona vínculos para obtener información más detallada e instrucciones paso a paso.

* [[!UICONTROL Visual Experience Composer] cambios](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): La versión de [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de febrero de 2015) presenta un [!UICONTROL Visual Experience Composer] (VEC) actualizado. Este artículo explica las diferencias entre las versiones heredadas y actualizadas del VEC.

* [[!UICONTROL Visual Experience Composer] opciones](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): Este artículo explica la interfaz de usuario actualizada del VEC y sus opciones.

* [[!DNL Target] Preguntas frecuentes sobre la actualización de la interfaz de usuario](/help/main/c-intro/updated-ui-faq.md): estas preguntas frecuentes tratan sobre las nuevas preguntas comunes acerca de la interfaz de usuario de [!DNL Target] y [!UICONTROL Visual Experience Composer] (VEC), incluidos los cambios de navegación, las ubicaciones de las características y la desaprobación de la opción de versión de la interfaz de usuario temporal. Tanto si es un experto en marketing, desarrollador o administrador, estas preguntas frecuentes le ayudan a realizar la transición sin problemas y a aprovechar al máximo la IU actualizada.

<!--## [!UICONTROL Edit]

The following options are available:

### [!UICONTROL Text/HTML] {#edit-text-html}

Change the HTML code for the element, such as the text for a text area, button, or link.

In addition to HTML code, you can edit and inject custom JavaScript.

Several rich text formatting options are available when editing text and HTML for [!UICONTROL A/B] and [!UICONTROL Experience Targeting] activities. You can choose a font, select a font style, change text alignment, and other standard text formatting options. When modifying HTML, you can toggle between the code view and rich-editing view of the HTML.

The following HTML5 tags can be nested:

|Tag|Allowed Nested Tags|
| --- | --- |
|`<a>`|`<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>`|
|`<ins>`|`<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`|
|`<del>`|`<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>`|
|`<label>`|`<p>`|

### [!UICONTROL Background Color]

Use the color picker to select or configure a background color. You can select a color swatch, and adjust it using RGB values or color hex codes. The red x in the color picker makes the background transparent.

**Note:** This option is not available for an element where a background image is set. 

### [!UICONTROL Styles] {#styles}

Use the [!UICONTROL Styles] panel to view or edit the value of existing styles for the selected element. You can also add additional styling.

To access the [!UICONTROL Styles] panel, click a page element from within the VEC, then click **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

The [!UICONTROL Styles] panel displays on the right side of the VEC. The panel contains a list of styles that lets you edit or add to the selected element. A real-time CSS Editor lets you view changes and add styles if you are comfortable using Cascading Style Sheets (CSS) or if you receive code from your developer.

![Styles panel](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

As you apply different styles, you can always revert your changes by clicking the [!UICONTROL Revert] icon that displays at the top-right corner of the [!UICONTROL Styles] panel after you change any section. Clicking the [!UICONTROL Revert] icon reverts all changes on the current section's panel.

Expand each section to edit or add styles, as explained below. To save your changes, click the [!UICONTROL Back] icon at the top of the panel to return to the panel's main display, then click **[!UICONTROL Save]**. 

Blue dots on the main panel and next to each option on the various section panels indicate that you have changed the corresponding styles. This visual indicator makes it easy for you to review your changes before clicking [!UICONTROL Save].

>[!NOTE]
>
>Quick actions for layout changes, background color, resizing, and move are also available as separate actions in the VEC menu. These options can be used as separate actions or you can use the Styles menu, as explained here.

* **[!UICONTROL Background]**

  Change the background color and image.

  * Color (specify the color code or use the color picker)
  * Image (select an image from the image picker)
  * Image source (specify an external URL)
  * Attachment
    * Click the top drop-down list to select scroll, fixed, or local
    * Click the bottom drop-down list to select repeat, repeat-x, repeat-y, no-repeat, space, or round
  * Clip
    * Click the top drop-down list to select border-box, padding-box, content-box, or text
    * Click the bottom drop-down list to select auto audio or audio

* **[!UICONTROL Typography]**

  Change the typography of an element. Typography edits are quick and easy. 

  Although the rich text editor (Edit Text/HTML) is available for fine tuning, quick actions to change the entire element is available via this option. If you want to apply typography changes to only a part of the text (not to the full text), use the [rich text editor](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md). 

  You can edit the following typography styles:

  * [!UICONTROL Font size]
  * [!UICONTROL Font weight]
  * [!UICONTROL Font style]
  * [!UICONTROL Color] (specify the color code or use the color picker)
  * [!UICONTROL Word spacing]
  * [!UICONTROL Line height]
  * [!UICONTROL Text alignment]

* **[!UICONTROL Margin]**

  Change the margin for the selected element. You can change the left, right, bottom, and top margins.

  Click the drop-down icon for each margin to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to set the margin or specify the number of pixels for each margin)

  Margin supports positive and negative values.

  Target also supports other size units, such as rem, pc, em. For more information about these units, see [Web Style Sheets CSS Tips and Tricks](https://www.w3.org/Style/Examples/007/units.en.html).

* **[!UICONTROL Padding]**

  Change the padding for the selected element. You can change the left, right, bottom, and top padding.

  Drag the slider to set the padding or specify the number of pixels for padding.

  Padding supports width scales from 0 onwards.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Border]**

  Click the border icons at the top of the panel to change the selected element's border.

  You can edit the following styles for each border (top, right, bottom, and left):

  * [!UICONTROL Border style] (none, hidden, dotted, dashed, solid, or double)
  * [!UICONTROL Border color] (specify the color code or use the color picker)
  * [!UICONTROL Border width] (drag the slider to select a border width or specify the width in pixels)

  Border supports width scales from 0 onwards.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Position]**

  Move the selected element from its current position. You can change the element's top, bottom, left, right, and [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) position.

  Click the [!UICONTROL Static] drop-down list to choose from the following position options:

  * [!UICONTROL Static]
  * [!UICONTROL Relative]
  * [!UICONTROL Absolute]
  * [!UICONTROL Sticky]
  * [!UICONTROL Fixed]

  Click the drop-down icon for each position to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to position the element or specify the number of pixels you want to move the element)

  Position supports positive and negative values.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Size]**

  Change the selected element's width and height.

  Click the drop-down icon next to [!UICONTROL Width] and [!UICONTROL Height] to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to size the element or specify the number of pixels for each dimension)

* **[!UICONTROL Filter]**

  Drag the slider for each filter option or specify the desired percentage:

  * [!UICONTROL Sepia]
  * [!UICONTROL Contrast]
  * [!UICONTROL Brightness]
  * [!UICONTROL GrayScale]
  * [!UICONTROL Blur]
  * [!UICONTROL Opacity]
  * [!UICONTROL Invert]
  *[!UICONTROL  Hue-rotate]
  * [!UICONTROL Saturate]

* **[!UICONTROL CSS Editor]**

  The real-time CSS Editor lets you view changes and add styles if you are comfortable using Cascading Style Sheets (CSS) or if you receive code from your developer.

  The CSS Editor displays any changes that you make in the Styles panel. As shown in the illustration below, the font size, top border, and image size have been changed:

  ![CSS editor with changes](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

  Notice the blue dots next to the [!UICONTROL Typography], [!UICONTROL Border], and [!UICONTROL Size] options in the preceding illustration. These dots indicate that you have changed these sections. If you open these section panels, blue dots display next to the specific options that you changed.

  You can type your own code if your desired style is not available by default in the [!UICONTROL Styles].

  The CSS Editor shows details for the current session only. If you save changes and then reopen the editor, details about your previous change do not display in the editor, even if you select the same element again.

  >[!IMPORTANT]
  >
  >You can apply a background image using the CSS Editor, but it might cause flicker. Test your changes before deployment.

### [!UICONTROL CSS Class]

Specify the predefined CSS class used for the element. If more than one element is selected, separate multiple CSS classes with a space.

Available for [!UICONTROL A/B], [!UICONTROL Automated Personalization], and [!UICONTROL Multivariate Test] activities.

### [!UICONTROL Link]

Change the URL in the link.

Use Edit Link to update the selector to point to the same image element. However, linking to a different image element is not supported. To link to a different image element, delete the original action from the code editor and use the [!UICONTROL Visual Experience Composer] to apply the action on the other image element.

## [!UICONTROL Insert Before]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html?lang=es){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML], and [!UICONTROL Text]

Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test.

Select an element on the page, then click [!UICONTROL Insert Before] and choose whether you want to insert an image, HTML, or text. The inserted element appears before the selected element.

The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected.

[!UICONTROL Recommendations] supports [!UICONTROL Insert Before] the contents of DIV, SECTION, and ARTICLE tags.

**Note:** Inserting an image requires that [!DNL Adobe Scene7 Publishing System] is enabled so you have access to the image library.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Insert After]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html?lang=es){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML], and [!UICONTROL Text]

Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test.

Select an element on the page, then click [!UICONTROL Insert After] and choose whether you want to insert an image, HTML, or text. The inserted element appears after the selected element.

The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected.

[!UICONTROL Recommendations] supports [!UICONTROL Insert After] the contents of DIV, SECTION, and ARTICLE tags.

**Note:** Inserting an image requires that [!DNL Adobe Scene7 Publishing System] is enabled so you have access to the image library.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Replace Content]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html?lang=es){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image]

Select a different image from the Content Library. The images available for swapping include the images uploaded to the Experience Cloud assets folder or uploaded in the Content Library in Target.

During initial activity creation, the URL displayed is not the URL used for delivery. Upon activity synching, that URL is updated to a production Scene7 URL.

For example, the initial URL might look like the following example:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

After activity syncing, the delivery URL might look like the following example:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations supports Replace With in DIV, SECTION, and ARTICLE tags.

**Note:** Swapping images requires an Adobe Scene7 Publishing System Account.

### [!UICONTROL HTML Offer]

Select a different offer from the [!UICONTROL Content Library].

**Note:** HTML Offers are stored on [!DNL Target] servers.

An HTML offer can be up to 256 KB.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Layout]

The following options are available:

### [!UICONTROL Rearrange]

Drag the element to another location inside the same parent element or DIV. Other elements shift location to make space for the rearranged element.

**Note**: Click-tracking does not work on rearranged items.

Currently, certain VEC actions, such as [!UICONTROL Rearrange] and [!UICONTROL Move], assume that the sibling elements of the source and destination parent elements are completely loaded. If lazy loading occurs under the parent DOM elements (source or destination), these VEC actions can cause inconsistent behavior. We are working on a more reliable approach to make VEC actions work in lazy-loaded DOM elements. As a temporary workaround, you can use [!UICONTROL Custom Code] in these scenarios to render your experiences.

### [!UICONTROL Resize]

Resize an element on your page. When you select [!UICONTROL Resize], a handle appears in the bottom-right corner of the element that lets you drag that corner to resize. Hold the Shift key to retain the same aspect ratio.

**Note:** Inline elements cannot be resized.

### [!UICONTROL Move] {#move}

Move elements on your page. Unlike the [!UICONTROL Rearrange] option, [!UICONTROL Move] does not shift other elements to make room for the element being moved. Use the arrow keys to fine tune the move. (Planned enhancement: support to ensure moved elements are not hidden behind other elements.)

In certain situations, such as when a CSS restriction requires an element to remain inside its parent element, you cannot move the element outside its parent. An element cannot be moved outside of a container that has following CSS property: `overflow: hidden`.

See [!UICONTROL Rearrange] above for more information about inconsistent behavior with the [!UICONTROL Move] and [!UICONTROL Rearrange] actions due to lazy loading of DOM elements.

### [!UICONTROL Hide]

Hide the element. The white space remains, but the content is removed.

### [!UICONTROL Remove]

Remove the element. The white space behind the image is removed and the space where the element was is collapsed.

**Note:** Items within a "classic" mbox (an mbox created within a Target Classic campaign) cannot be removed using this option.

## [!UICONTROL Expand Section]

Select the parent element in addition to the originally selected element. When you select any parent element, all children of that element are automatically selected. You can expand the selection multiple times.

## [!UICONTROL Navigate to Link]

Open the destination of the link.

## [!UICONTROL Undo]/[!UICONTROL Redo]

Undo changes you make to your activities during an editing session. You can also redo changes that have been previously undone.

## Considerations {#considerations}

* If an offer contains HTML content, see "How at.js renders offers with HTML content" in [How at.js works](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html?lang=es){target=_blank} for more information.

## Custom element support {#custom}

The VEC supports [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components) to let you create and test personalized experiences and offers on custom elements and on elements inside custom elements. This functionality is available in the VEC for all [!DNL Target] activity types.

>[!NOTE]
>
>VEC support for custom elements is supported in [at.js version](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank} 2.7.0 (or later){target=_blank}. Ensure that your website has the required version deployed. If you are using the [Visual Experience Composer helper extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md), it must also have the required version of at.js deployed. The VEC options described above are not visible and available for use with non-supported versions of at.js.
>
>VEC support for custom elements is currently not supported with the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

Most VEC actions are supported on custom events and inside custom events, with the following exceptions: 

The following actions are not available on custom elements:

* [!UICONTROL Edit]
  * [!UICONTROL Text/HTML]
  * [!UICONTROL Link]
  * [!UICONTROL Edit Source]

* [!UICONTROL Replace Content]

The following action is not available inside custom elements:

* [!UICONTROL Layout]
  * [!UICONTROL Rearrange]-->
