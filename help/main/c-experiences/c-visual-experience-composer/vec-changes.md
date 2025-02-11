---
keywords: compositor de experiencias visuales;vec;wysiwyg
description: Comprenda los cambios introducidos en el Compositor de experiencias visuales (VEC) en la versión de Adobe Target 25.2.1 (11 de febrero de 2025).
title: ¿Qué cambios se introducen en el nuevo Compositor de experiencias visuales (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
source-git-commit: 75f44b7ea4c3aff0e33cc2ee54bc39a705deaf2a
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 0%

---

# [!UICONTROL Visual Experience Composer] cambios

La versión de [!DNL Adobe Target Standard/Premium] 25.2.1 (del 11 de febrero de 2015) presenta un [!UICONTROL Visual Experience Composer] (VEC) actualizado. Este artículo explica las diferencias entre las versiones anteriores y actualizadas del VEC.

El VEC se muestra cuando crea o edita una actividad existente.

![Compositor de experiencias visuales (VEC)](/help/main/c-experiences/c-visual-experience-composer/assets/new-vec.png)

## Cambios importantes

Las siguientes secciones explican los cambios más importantes en el VEC actualizado en comparación con la versión anterior.

### [!UICONTROL Experiences] panel

Al igual que en la versión anterior, el panel [!UICONTROL Experiences] permanece en el lado izquierdo del VEC. El panel [!UICONTROL Experiences] no se puede contraer.

![Panel de experiencias](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

Puede crear, cambiar el nombre o quitar experiencias mediante el panel [!UICONTROL Experiences]. Haga clic en el icono **[!UICONTROL Add]** ( ![Agregar icono](/help/main/assets/icons/Add.svg) ) para agregar una nueva experiencia. Haga clic en el icono [!UICONTROL More Actions] ( ![icono Más acciones](/help/main/assets/icons/MoreSmall.svg) ) para duplicar, eliminar o redirigir una experiencia.

### [!UICONTROL Components] panel (nuevo)

Puede agregar varios componentes a la página web y editarlos según sea necesario mediante el nuevo panel [!UICONTROL Components].

![Panel de componentes](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

Para agregar un componente nuevo, arrastre el componente que desee insertar sobre un elemento de página existente en el lienzo de edición. A continuación, elija insertar el componente antes de después del elemento seleccionado.

En comparación con la versión anterior del VEC, no se puede reemplazar un elemento seleccionado con un componente.

### [!UICONTROL Modifications] panel

Para abrir el panel [!UICONTROL Modifications], haga clic en el icono [!UICONTROL Show Modifications] ( ![Mostrar panel de modificaciones](/help/main/assets/icons/History.svg) ) en el panel [!UICONTROL Components]. El panel [!UICONTROL Modifications] cambió la posición del lado derecho al lado izquierdo del lienzo de edición.

![Panel de modificaciones](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

El panel [!UICONTROL Modifications] muestra todos los cambios realizados en su página en [!UICONTROL Visual Experience Composer] (VEC) y le permite realizar cambios adicionales (como selector de CSS, mbox y código personalizado).

Haga clic en el icono [!UICONTROL More Options] ( ![icono Más acciones](/help/main/assets/icons/MoreSmall.svg) ) para agregar una modificación, eliminar todas las modificaciones o eliminar todas las modificaciones no válidas. Haga clic en [!UICONTROL Select] para realizar operaciones masivas: [!UICONTROL Apply to All Pages] o [!UICONTROL Delete].

### [!UICONTROL Properties] panel (nuevo)

El nuevo panel [!UICONTROL Properties] le permite cambiar las propiedades de los elementos seleccionados en la página, ya sean estos elementos elementos HTML u objetos específicos de [!DNL Target], como recomendaciones u ofertas.

![Panel de propiedades](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

Haga clic en los iconos de la parte superior del panel para editar el código del HTML o eliminar, duplicar u ocultar elementos. Los cambios aparecerán en el panel [!UICONTROL Modifications].

El panel [!UICONTROL Properties] se puede contraer en el carril derecho. Haga clic en el icono [!UICONTROL Show/Hide Properties] ( ![icono Propiedades](/help/main/assets/icons/Propertie.svg) ) a la derecha del panel para contraer o mostrar el panel [!UICONTROL Properties].

### Configuración de actividades

Haga clic en el icono [!UICONTROL Configure] ( ![Icono de configuración](/help/main/assets/icons/Setting.svg) ) que se muestra en la parte superior del lienzo de diseño para mostrar el menú de propiedades de la actividad.

![Opciones de configuración de actividades](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

Las distintas opciones permiten habilitar o deshabilitar actividades de audiencia múltiple o de varias páginas, asignar propiedades ([[!DNL Target Premium]](/help/main/c-intro/intro.md#premium) característica) o editar reglas de entrega de páginas.

La posición y la funcionalidad son similares a la interfaz de usuario del VEC anterior.

### Modos [!UICONTROL Design]/[!UICONTROL Browse]

Utilice los conmutadores [!UICONTROL Design]/[!UICONTROL Browse] que se muestran en la parte superior del lienzo de diseño para cambiar entre el modo de diseño y el modo de exploración.

![Alternadores de diseño y exploración](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

Utilice el modo [!UICONTROL Browse] para navegar por el sitio y elegir la vista o la página que desee actualizar. Vuelva al modo [!UICONTROL Design] para agregar o editar los cambios.

### [!UICONTROL Undo]/[!UICONTROL Redo]

Para deshacer los cambios, haga clic en el icono [!UICONTROL Undo] ( ![Deshacer icono](/help/main/assets/icons/Undo.svg) ).

![Icono Deshacer en VEC](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

Para rehacer una acción, expanda el grupo de botones Deshacer/[!UICONTROL Redo] y elija [!UICONTROL Redo].

### [!UICONTROL Design] lienzo

El lienzo [!UICONTROL Design] le permite seleccionar ventanillas móviles, incluidas las de ajuste a pantalla, [!UICONTROL Desktop], [!UICONTROL Tablet], [!UICONTROL Mobile Landscape] y [!UICONTROL Mobile Portrait]. De manera predeterminada, el lienzo ajusta la página a la pantalla junto con las ventanillas móviles definidas en la sección [Administración](/help/main/administrating-target/visual-experience-composer-set-up.md).

![Opciones de ventanilla](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

El VEC actualizado también le permite acercar o alejar la vista haciendo clic en el icono correspondiente ( ![icono Acercar](/help/main/assets/icons/ZoomIn.svg) o ![icono Alejar](/help/main/assets/icons/ZoomOut.svg) ).

## Ilustración visual que muestra cambios en la IU

La siguiente ilustración muestra los cambios de interfaz de usuario de alto nivel realizados en el VEC actualizado. La parte superior de la ilustración muestra la IU actualizada del VEC y la parte inferior muestra la IU anterior. Las flechas muestran dónde se han movido varios elementos.

![Comparación de VEC nueva respecto a la IU anterior](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png)