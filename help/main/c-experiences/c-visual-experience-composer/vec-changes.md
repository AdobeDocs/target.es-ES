---
keywords: compositor de experiencias visuales;vec;wysiwyg
description: Comprenda los cambios introducidos en el Compositor de experiencias visuales (VEC) en la versión de Adobe Target 25.2.1 (17 de febrero de 2025).
title: ¿Qué cambios se introducen en el nuevo Compositor de experiencias visuales (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
TQID: https://experienceleague.adobe.com/PZaKHKs1-GPnR1U-E0d3YQVNWhinmt9ctjOSnIbNrE0
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 994
ht-degree: 0%

---

# [!UICONTROL Cambios en el Compositor de experiencias visuales]

La versión de [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de febrero de 2015) presenta un [!UICONTROL Compositor de experiencias visuales] (VEC) actualizado. Este artículo explica las diferencias entre las versiones anteriores y actualizadas del VEC.

>[!IMPORTANT]
>
>El [!UICONTROL Compositor de edición visual] actualizado requiere la extensión [!DNL Adobe Experience Cloud] [[!UICONTROL Ayuda de edición visual]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) disponible en [!DNL Chrome Web Store].

El VEC se muestra cuando crea o edita una actividad existente.

![Compositor de experiencias visuales (VEC)](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## Cambios importantes en el VEC

Las siguientes secciones explican los cambios más importantes en el VEC actualizado en comparación con la versión anterior.

### [!UICONTROL Experiencias] carril

Al igual que en la versión anterior, el carril [!UICONTROL Experiences] permanece en el lado izquierdo del VEC. El carril [!UICONTROL Experiencias] no se puede contraer.

![Carril de experiencias](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

Puede crear, cambiar el nombre o quitar experiencias con el carril [!UICONTROL Experiencias]. Haga clic en el icono **[!UICONTROL Agregar]** ( ![Agregar icono](/help/main/assets/icons/Add.svg) ) para agregar una nueva experiencia. Haga clic en el icono [!UICONTROL Más acciones] ( ![Icono de más acciones](/help/main/assets/icons/MoreSmall.svg) ) para duplicar, eliminar o redirigir una experiencia.

### [!UICONTROL Componentes] carril (nuevo)

Puede agregar varios componentes a la página web y editarlos según sea necesario mediante el nuevo carril [!UICONTROL Componentes].

![Carril de componentes](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

Para agregar un componente nuevo, seleccione el componente que desee en el carril [!UICONTROL Componentes], pase el ratón sobre un elemento existente de la página y, a continuación, elija insertar el componente antes de o después del elemento seleccionado.

>[!NOTE]
>
>Si ve el carril [!UICONTROL Modificaciones] en esta área en lugar del carril [!UICONTROL Componentes], haga clic en el icono **[!UICONTROL Mostrar componentes]** ( ![Mostrar componentes](/help/main/assets/icons/Add.svg) ). El icono [!UICONTROL Mostrar componentes] ( ![Mostrar componentes](/help/main/assets/icons/Add.svg) ) y el icono [!UICONTROL Mostrar modificaciones] ( ![Mostrar modificaciones carril](/help/main/assets/icons/History.svg) ) actúan como indicadores para mostrar las opciones adecuadas.
>
>Para contraer el carril [!UICONTROL Componentes] y ampliar el lienzo [!UICONTROL Diseño], mientras el carril [!UICONTROL Componentes] está abierto, haga clic en el icono ( ![Mostrar icono de componentes](/help/main/assets/icons/Add.svg) ).

### [!UICONTROL Modificaciones] carril

Para abrir el carril [!UICONTROL Modificaciones], haga clic en el icono [!UICONTROL Mostrar modificaciones] ( ![Mostrar modificaciones](/help/main/assets/icons/History.svg) ) en el carril [!UICONTROL Componentes]. El carril [!UICONTROL Modificaciones] ha cambiado de posición del lado derecho al lado izquierdo del lienzo de edición.

![Carril de modificaciones](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

>[!NOTE]
>
>El icono [!UICONTROL Mostrar componentes] ( ![Mostrar componentes](/help/main/assets/icons/Add.svg) ) y el icono [!UICONTROL Mostrar modificaciones] ( ![Mostrar modificaciones carril](/help/main/assets/icons/History.svg) ) actúan como indicadores para mostrar las opciones adecuadas.
>
>Para contraer el carril [!UICONTROL Modificaciones] y ampliar el lienzo [!UICONTROL Diseño], mientras el carril [!UICONTROL Modificaciones] está abierto, haga clic en el icono [!UICONTROL Mostrar modificaciones] ( ![Mostrar modificaciones](/help/main/assets/icons/History.svg) ).

El carril [!UICONTROL Modificaciones] muestra todos los cambios realizados en su página en el VEC y le permite realizar cambios adicionales (como Selector de CSS, Mbox y Código personalizado).

Haga clic en el icono [!UICONTROL Más opciones] ( ![Icono de más acciones](/help/main/assets/icons/MoreSmall.svg) ) para agregar una modificación, eliminar todas las modificaciones o eliminar todas las modificaciones no válidas. Haga clic en [!UICONTROL Seleccionar] para realizar operaciones masivas: [!UICONTROL Aplicar a todas las páginas] o [!UICONTROL Eliminar].

Para volver a mostrar el carril [!UICONTROL Modificaciones], haga clic en el icono [!UICONTROL Ocultar modificaciones] ( ![Mostrar modificaciones](/help/main/assets/icons/History.svg) ) en el carril [!UICONTROL Modificaciones].

### [!UICONTROL Propiedades] carril (nuevo)

El carril [!UICONTROL Propiedades] le permite cambiar las propiedades de los elementos seleccionados en la página, ya sean estos elementos HTML u objetos específicos de [!DNL Target], como recomendaciones u ofertas.

![Carril de propiedades](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

Haga clic en los iconos de la parte superior del carril para editar el código HTML o eliminar, duplicar u ocultar elementos. Los cambios aparecen en el carril [!UICONTROL Modificaciones].

![Iconos de propiedad](/help/main/c-experiences/c-visual-experience-composer/assets/options-icons.png)

El carril [!UICONTROL Propiedades] se puede contraer en el carril derecho. Haga clic en el icono [!UICONTROL Mostrar u ocultar propiedades] ( ![icono Propiedades](/help/main/assets/icons/Propertie.svg) ) a la derecha del carril para contraer o mostrar el carril [!UICONTROL Propiedades].

### Configuración de actividades

Haga clic en el icono [!UICONTROL Configurar] ( ![Configurar icono](/help/main/assets/icons/Setting.svg) ) que se muestra en la parte superior del lienzo de diseño para mostrar el menú de propiedades de la actividad.

![Opciones de configuración de actividades](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

Las distintas opciones permiten asignar propiedades, editar reglas de entrega de páginas, especificar preferencias de sitio, agregar páginas adicionales y habilitar o deshabilitar actividades de audiencia múltiple o de varias páginas. Asignar [!UICONTROL propiedades] es una característica de [[!DNL Target Premium]](/help/main/c-intro/intro.md#premium).

La posición y la funcionalidad son similares a la interfaz de usuario del VEC anterior.

### Modos [!UICONTROL Diseño]/[!UICONTROL Examinar]

Use los alternadores [!UICONTROL Diseño]/[!UICONTROL Examinar] que se muestran en la parte superior del carril de [!UICONTROL Propiedades] para cambiar entre el modo de diseño y el de exploración.

![Alternadores de diseño y exploración](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

Utilice el modo [!UICONTROL Examinar] para navegar por el sitio y elegir la vista o la página que desee actualizar. Vuelva al modo [!UICONTROL Diseño] para agregar o editar los cambios.

### [!UICONTROL Deshacer]/[!UICONTROL Rehacer]

Puede deshacer los cambios realizados haciendo clic en el icono [!UICONTROL Deshacer] ( ![Deshacer icono](/help/main/assets/icons/Undo.svg) ).

![Icono Deshacer en VEC](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

Para rehacer una acción, expande el grupo de botones Deshacer/[!UICONTROL Rehacer] y elige [!UICONTROL Rehacer].

### [!UICONTROL Diseñar] lienzo

El lienzo [!UICONTROL Design] le permite seleccionar ventanillas móviles, entre las que se incluyen la pantalla adaptada, [!UICONTROL Escritorio], [!UICONTROL Tableta], [!UICONTROL Horizontal móvil] y [!UICONTROL Vertical móvil].

![Opciones de ventanilla](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

El VEC actualizado también le permite acercar o alejar la vista haciendo clic en el icono correspondiente ( ![icono Acercar](/help/main/assets/icons/ZoomIn.svg) o ![icono Alejar](/help/main/assets/icons/ZoomOut.svg) ).

## Ilustración visual que muestra cambios en la IU

La siguiente ilustración muestra los cambios de interfaz de usuario de alto nivel realizados en el VEC actualizado. La parte superior de la ilustración muestra la IU actualizada del VEC y la parte inferior muestra la IU anterior. Las flechas muestran dónde se han movido varios elementos.

(Haga clic en la imagen para expandirla al ancho completo del explorador).

![Comparación de VEC nueva respecto a la IU anterior](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png){width="600" zoomable="yes"}

## Más información sobre la IU actualizada

* [[!DNL Target Standard/Premium] 25.2.1 (17 de febrero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para [!UICONTROL Actividades], [!UICONTROL Recommendations] y [!UICONTROL Compositor de experiencias visuales] (VEC).

* [[!DNL Target Standard/Premium] 25.1.1 (9 de enero de 2025) notas de la versión](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): Proporciona un resumen de los cambios clave de la interfaz de usuario en [!DNL Target] para la [!UICONTROL Biblioteca de ofertas].

* [Comprender la [!DNL Target] IU](/help/main/c-intro/understand-the-target-ui.md): Proporciona una breve descripción general para ayudarle a familiarizarse con [!DNL Target] y proporciona vínculos para obtener información más detallada e instrucciones paso a paso.

* [[!UICONTROL Cambios del Compositor de experiencias visuales]](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): La versión de [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de febrero de 2025) presenta un [!UICONTROL Compositor de experiencias visuales] (VEC) actualizado. Este artículo explica las diferencias entre las versiones heredadas y actualizadas del VEC.

* [[!UICONTROL Compositor de experiencias visuales] opciones](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): Este artículo explica la interfaz de usuario de VEC actualizada y sus opciones.

* [[!DNL Target] Preguntas frecuentes sobre la actualización de la interfaz de usuario](/help/main/c-intro/updated-ui-faq.md): estas preguntas frecuentes tratan sobre las nuevas preguntas comunes acerca de la interfaz de usuario de [!DNL Target] y el [!UICONTROL Compositor de experiencias visuales] (VEC), incluidos los cambios de navegación, las ubicaciones de las características y la obsolescencia de la opción de versión de la interfaz de usuario temporal. Tanto si es un experto en marketing, desarrollador o administrador, estas preguntas frecuentes le ayudan a realizar la transición sin problemas y a aprovechar al máximo la IU actualizada.