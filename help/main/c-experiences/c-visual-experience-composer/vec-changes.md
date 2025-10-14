---
keywords: compositor de experiencias visuales;vec;wysiwyg
description: Comprenda los cambios introducidos en el Compositor de experiencias visuales (VEC) en la versión de Adobe Target 25.2.1 (17 de febrero de 2025).
title: ¿Qué cambios se introducen en el nuevo Compositor de experiencias visuales (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
source-git-commit: 2dabda04aabe720b28e31033052e2076e78d1376
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 0%

---

# [!UICONTROL Visual Experience Composer] cambios

La versión de [!DNL Adobe Target Standard/Premium] 25.2.1 (del 17 de febrero de 2015) presenta un [!UICONTROL Visual Experience Composer] (VEC) actualizado. Este artículo explica las diferencias entre las versiones anteriores y actualizadas del VEC.

>[!IMPORTANT]
>
>El(la) [!UICONTROL Visual Editing Composer] actualizado(a) requiere la extensión [!DNL Adobe Experience Cloud] [[!UICONTROL Visual Editing Helper] &#x200B;](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) disponible(a) en [!DNL Chrome Web Store].

El VEC se muestra cuando crea o edita una actividad existente.

![Compositor de experiencias visuales (VEC)](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## Cambios importantes en el VEC

Las siguientes secciones explican los cambios más importantes en el VEC actualizado en comparación con la versión anterior.

### Carril [!UICONTROL Experiences]

Como en la versión anterior, el carril [!UICONTROL Experiences] permanece en el lado izquierdo del VEC. El carril [!UICONTROL Experiences] no se puede contraer.

![Carril de experiencias](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

Puede crear, cambiar el nombre o quitar experiencias mediante el carril [!UICONTROL Experiences]. Haga clic en el icono **[!UICONTROL Add]** ( ![Agregar icono](/help/main/assets/icons/Add.svg) ) para agregar una nueva experiencia. Haga clic en el icono [!UICONTROL More Actions] ( ![icono Más acciones](/help/main/assets/icons/MoreSmall.svg) ) para duplicar, eliminar o redirigir una experiencia.

### [!UICONTROL Components] carril (nuevo)

Puede agregar varios componentes a la página web y editarlos según sea necesario mediante el nuevo carril [!UICONTROL Components].

![Carril de componentes](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

Para agregar un componente nuevo, seleccione el componente que desee en el carril [!UICONTROL Components], pase el ratón sobre un elemento existente de la página y, a continuación, elija insertar el componente antes de o después del elemento seleccionado.

>[!NOTE]
>
>Si ve el carril [!UICONTROL Modifications] en esta área en lugar del carril [!UICONTROL Components], haga clic en el icono **[!UICONTROL Show Components]** ( ![Mostrar icono de componentes](/help/main/assets/icons/Add.svg) ). El icono [!UICONTROL Show Components] ( ![Mostrar icono de componentes](/help/main/assets/icons/Add.svg) ) y el icono [!UICONTROL Show Modifications] ( ![Mostrar carril de modificaciones](/help/main/assets/icons/History.svg) ) actúan como alternadores para mostrar las opciones adecuadas.
>
>Para contraer el carril [!UICONTROL Components] y ampliar el lienzo [!UICONTROL Design], mientras el carril [!UICONTROL Components] está abierto, haga clic en el icono ( ![Mostrar icono de componentes](/help/main/assets/icons/Add.svg) ).

### Carril [!UICONTROL Modifications]

Para abrir el carril [!UICONTROL Modifications], haga clic en el icono [!UICONTROL Show Modifications] ( ![Mostrar modificaciones](/help/main/assets/icons/History.svg) ) en el carril [!UICONTROL Components]. El carril [!UICONTROL Modifications] cambió de posición del lado derecho al lado izquierdo del lienzo de edición.

![Carril de modificaciones](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

>[!NOTE]
>
>El icono [!UICONTROL Show Components] ( ![Mostrar icono de componentes](/help/main/assets/icons/Add.svg) ) y el icono [!UICONTROL Show Modifications] ( ![Mostrar carril de modificaciones](/help/main/assets/icons/History.svg) ) actúan como alternadores para mostrar las opciones adecuadas.
>
>Para contraer el carril [!UICONTROL Modifications] y ampliar el lienzo [!UICONTROL Design], mientras el carril [!UICONTROL Modifications] está abierto, haga clic en el icono [!UICONTROL Show Modifications] ( ![Mostrar modificaciones](/help/main/assets/icons/History.svg) ).

El carril [!UICONTROL Modifications] muestra todos los cambios realizados en su página en el VEC y le permite realizar cambios adicionales (como selector de CSS, mbox y código personalizado).

Haga clic en el icono [!UICONTROL More Options] ( ![icono Más acciones](/help/main/assets/icons/MoreSmall.svg) ) para agregar una modificación, eliminar todas las modificaciones o eliminar todas las modificaciones no válidas. Haga clic en [!UICONTROL Select] para realizar operaciones masivas: [!UICONTROL Apply to All Pages] o [!UICONTROL Delete].

Para volver a mostrar el carril [!UICONTROL Modifications], haga clic en el icono [!UICONTROL Hide Modifications] ( ![Mostrar modificaciones](/help/main/assets/icons/History.svg) ) en el carril [!UICONTROL Modifications].

### [!UICONTROL Properties] carril (nuevo)

El carril [!UICONTROL Properties] le permite cambiar las propiedades de los elementos seleccionados en la página, ya sean estos elementos HTML u objetos específicos de [!DNL Target], como recomendaciones u ofertas.

![Carril de propiedades](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

Haga clic en los iconos de la parte superior del carril para editar el código HTML o eliminar, duplicar u ocultar elementos. Los cambios aparecerán en el carril [!UICONTROL Modifications].

![Iconos de propiedad](/help/main/c-experiences/c-visual-experience-composer/assets/options-icons.png)

El carril [!UICONTROL Properties] se puede contraer en el carril derecho. Haga clic en el icono [!UICONTROL Show/Hide Properties] ( ![icono Propiedades](/help/main/assets/icons/Propertie.svg) ) a la derecha del carril para contraer o mostrar el carril [!UICONTROL Properties].

### Configuración de actividades

Haga clic en el icono [!UICONTROL Configure] ( ![Icono de configuración](/help/main/assets/icons/Setting.svg) ) que se muestra en la parte superior del lienzo de diseño para mostrar el menú de propiedades de la actividad.

![Opciones de configuración de actividades](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

Las distintas opciones permiten asignar propiedades, editar reglas de entrega de páginas, especificar preferencias de sitio, agregar páginas adicionales y habilitar o deshabilitar actividades de audiencia múltiple o de varias páginas. Asignar [!UICONTROL Properties] es una característica de [[!DNL Target Premium]](/help/main/c-intro/intro.md#premium).

La posición y la funcionalidad son similares a la interfaz de usuario del VEC anterior.

### Modos [!UICONTROL Design]/[!UICONTROL Browse]

Utilice los conmutadores [!UICONTROL Design]/[!UICONTROL Browse] que se muestran en la parte superior del carril [!UICONTROL Properties] para cambiar entre el modo de diseño y el de exploración.

![Alternadores de diseño y exploración](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

Utilice el modo [!UICONTROL Browse] para navegar por el sitio y elegir la vista o la página que desee actualizar. Vuelva al modo [!UICONTROL Design] para agregar o editar los cambios.

### [!UICONTROL Undo]/[!UICONTROL Redo]

Para deshacer los cambios, haga clic en el icono [!UICONTROL Undo] ( ![Deshacer icono](/help/main/assets/icons/Undo.svg) ).

![Icono Deshacer en VEC](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

Para rehacer una acción, expanda el grupo de botones Deshacer/[!UICONTROL Redo] y elija [!UICONTROL Redo].

### [!UICONTROL Design] lienzo

El lienzo [!UICONTROL Design] le permite seleccionar ventanillas móviles, incluidas las de ajuste a pantalla, [!UICONTROL Desktop], [!UICONTROL Tablet], [!UICONTROL Mobile Landscape] y [!UICONTROL Mobile Portrait].

![Opciones de ventanilla](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

El VEC actualizado también le permite acercar o alejar la vista haciendo clic en el icono correspondiente ( ![icono Acercar](/help/main/assets/icons/ZoomIn.svg) o ![icono Alejar](/help/main/assets/icons/ZoomOut.svg) ).

## Ilustración visual que muestra cambios en la IU

La siguiente ilustración muestra los cambios de interfaz de usuario de alto nivel realizados en el VEC actualizado. La parte superior de la ilustración muestra la IU actualizada del VEC y la parte inferior muestra la IU anterior. Las flechas muestran dónde se han movido varios elementos.

(Haga clic en la imagen para expandirla al ancho completo del explorador).

![Comparación de VEC nueva respecto a la IU anterior](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png){width="600" zoomable="yes"}

## Más información sobre la IU actualizada

* [[!DNL Target Standard/Premium] 25.2.1 (17 de febrero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Activities], [!UICONTROL Recommendations] y [!UICONTROL Visual Experience Composer] (VEC).

* [[!DNL Target Standard/Premium] 25.1.1 (9 de enero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Offers Library].

* [Comprender la [!DNL Target] IU](/help/main/c-intro/understand-the-target-ui.md): Proporciona una breve descripción general para ayudarle a familiarizarse con [!DNL Target] y proporciona vínculos para obtener información más detallada e instrucciones paso a paso.

* [[!UICONTROL Visual Experience Composer] cambios](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): La versión de [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de febrero de 2025) presenta un [!UICONTROL Visual Experience Composer] (VEC) actualizado. Este artículo explica las diferencias entre las versiones heredadas y actualizadas del VEC.

* [[!UICONTROL Visual Experience Composer] opciones](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): Este artículo explica la interfaz de usuario actualizada del VEC y sus opciones.

* [[!DNL Target] Preguntas frecuentes sobre la actualización de la interfaz de usuario](/help/main/c-intro/updated-ui-faq.md): estas preguntas frecuentes tratan sobre las nuevas preguntas comunes acerca de la interfaz de usuario de [!DNL Target] y [!UICONTROL Visual Experience Composer] (VEC), incluidos los cambios de navegación, las ubicaciones de las características y la desaprobación de la opción de versión de la interfaz de usuario temporal. Tanto si es un experto en marketing, desarrollador o administrador, estas preguntas frecuentes le ayudan a realizar la transición sin problemas y a aprovechar al máximo la IU actualizada.