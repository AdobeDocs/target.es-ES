---
keywords: compositor de experiencias visuales;vec;wysiwyg
description: Aprenda los conceptos básicos del uso del Compositor de experiencias visuales (VEC) en Adobe Target. El VEC es un editor de WYSIWYG que permite crear fácilmente experiencias personalizadas.
title: ¿Cómo utilizo el Compositor de experiencias visuales (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
source-git-commit: 3f5b198ad08d85caa9c859171e78b710083e44fb
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 43%

---

# [!UICONTROL Visual Experience Composer] (VEC)

El [!UICONTROL Visual Experience Composer] (VEC) de [!DNL Adobe Target] es un editor de WYSIWYG que permite a los clientes crear y probar experiencias personalizadas directamente en sus sitios web o páginas web móviles sin necesidad de editar el código.

>[!NOTE]
>
>La versión de [!DNL Target Standard/Premium] 25.2.1 (17 de febrero de 2025) incluyó una versión actualizada del VEC. Para obtener información sobre las diferencias entre el VEC actualizado y la versión anterior, consulte [Cambios del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md). Para obtener una descripción general de las distintas opciones del VEC actualizado, consulte [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

El VEC permite crear y probar fácilmente experiencias y ofertas personalizadas en el contexto del sitio. Puede crear experiencias y ofertas para actividades de [!DNL Target] arrastrando y soltando, intercambiando y modificando el diseño y el contenido de una página web (u oferta) o de una página web móvil.

El VEC es una de las características principales de [!DNL Target]. El VEC permite que los expertos en marketing y los diseñadores creen y cambien contenido por medio de una interfaz visual. Se pueden elegir muchas opciones de diseño sin tener que editar directamente el código. Editar HTML y JavaScript también es posible con las opciones de edición que se encuentran disponibles en el compositor.

En la ficha [!DNL Target] **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**, puede escribir la dirección URL predeterminada [!UICONTROL Visual Experience Composer].

Esta dirección URL determina la página de inicio al abrir el VEC. Si no especifica una dirección URL predeterminada, comenzará con una página en blanco cuando abra el editor y, a continuación, podrá especificar una dirección URL.

![VEC resaltado](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

>[!NOTE]
>
>Algunos exploradores, como [!DNL Firefox], pueden bloquear una página y evitar que se muestre en el VEC si esta contiene contenido mixto (por ejemplo, una página no segura en un sitio seguro). Si la página no se muestra, haga clic en el icono situado junto a la dirección URL en la barra de direcciones del explorador y seleccione **[!UICONTROL Disable protection on this page]**. Este problema no afecta a la visualización de las páginas de los visitantes del sitio.

El contenido de dentro de un iframe en la página no se puede modificar en el VEC. Para editar contenido dentro de un iframe, asegúrese de que el documento del iframe esté habilitado para [!DNL Target] y luego cargue la dirección URL del iframe en el VEC.

Puede usar las pestañas del carril [!UICONTROL Experiences] para ver la página tal como se mostraría a diferentes audiencias o con diferentes experiencias. Puede proporcionar un nombre para cada experiencia. Por ejemplo, si está probando la ubicación del vínculo a la página de inicio en la barra de navegación, podría asignar un nombre a la experiencia en la que el vínculo a la página de inicio aparece primero. Por ejemplo, &quot;Vínculo a Inicio&quot; para que sea más fácil identificar las experiencias en la lista.

>[!NOTE]
>
>Los cambios en la estructura de una página que afecten a las ubicaciones utilizadas en una actividad creada en esa página pueden producir problemas al editar la experiencia. Si se ha cambiado una ubicación fuera del VEC, es posible que [!DNL Target] no encuentre la ubicación donde se cambió el contenido.

A medida que mueve el ratón por la página, un cuadro contextual sigue al cursor, destacando los elementos en la página.

<!--Click the **[!UICONTROL Overlays]** icon to change the way the highlight displays. For example, you can choose to highlight only images, links, regional mboxes, modifications, or JavaScript. You can change the color of the highlight. You can also specify a highlight color and type of fill used to highlight different element types.

![Change Overlay settings](/help/main/c-experiences/c-visual-experience-composer/assets/change-overlay.png)-->

Haga clic en un elemento resaltado para acceder al menú de opciones disponibles para dicho tipo de elemento. Por ejemplo, puede hacer clic en una imagen y seleccionar **[!UICONTROL Change Image]** para cambiar la imagen a otra imagen. O bien, haga clic en un botón y cambie el color del texto.

También puede hacer clic en **[!UICONTROL Browse]** y luego navegar a una página que esté disponible desde la página principal, como una página de envío o un carro de compras, y probar los cambios en esa página. También puede acceder a los elementos de la página que están disponibles cuando mueve el cursor por encima, como los menús flotantes y los minicarros. Cuando termine de navegar por la página, haga clic en **[!UICONTROL Design]** para editar la experiencia. Por ejemplo, puede interesarle cambiar el diseño de una lista desplegable de carro de compras o un carrusel de imágenes.

>[!NOTE]
>
>Si un estado de movimiento del cursor por encima depende de JavaScript, asegúrese de que **[!UICONTROL Disable JavaScript]** no esté seleccionado. JavaScript debe estar habilitado para poder editar los elementos JavaScript.

Para obtener información sobre las opciones disponibles en el VEC, consulte [Opciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81).

Puede realizar algunas modificaciones en una página mientras se carga la página (o después de que la página no se haya cargado), o puede cancelar la carga de la página en el VEC. Para obtener más información, consulte:

* [Edición de una página mientras se carga o después de que la página no se haya cargado](#loading)
* [Cancelación de la carga de una página dentro del VEC](#cancel-loading)

## Edición de una página mientras se carga o después de que la página no se haya cargado {#loading}

Puede realizar muchas acciones antes de que la página se cargue en VEC o incluso si la página no se carga completamente (por ejemplo, si el código personalizado ya no funciona).

Algunas razones por las cuales es posible que desee acceder o editar una página mientras ésta se carga dentro del VEC o después de que no se cargue:

* Desea realizar una modificación sencilla de una página, como agregar un código personalizado o cambiar el nombre de una experiencia
* Desea copiar código personalizado existente de una página que ya no es accesible
* Sabe que una página no se cargará dentro del VEC pero de todas maneras desea realizar ediciones simples

Mientras la página se carga (o después de que no se haya cargado), las opciones [!UICONTROL Experiences], [!UICONTROL Components] y [!UICONTROL Configure] están accesibles.

## Cancelación de la carga de una página dentro del VEC {#cancel-loading}

Puede cancelar la carga de una página dentro del VEC para desbloquear la edición de la actividad sin esperar a que se cargue la página. Esta función ahorra tiempo y le ayuda a realizar ediciones sencillas o a insertar código personalizado de forma más eficaz sin esperar a que la página cargue dentro del VEC.

Algunas de las razones por las que es posible que desee cancelar la carga de páginas dentro del VEC son:

* Desea realizar pequeñas ediciones en las modificaciones existentes
* Desea eliminar una o más modificaciones existentes
* Desea insertar o editar código personalizado
* Introdujo la dirección URL incorrecta para la página
* Desea habilitar o deshabilitar JavaScript antes de cargar la página en el VEC
* Desea agregar más reglas de prueba de plantilla a los criterios de [!UICONTROL Page Delivery]
* Desea anular la opción global [!UICONTROL Enhanced Experience Composer] (EEC) al cargar una página a través de EEC o solo iframe

Si cancela la carga de páginas en el VEC, puede cambiar entre experiencias en la actividad sin esperar a que se cargue la página. Para volver a ver la página dentro del VEC, debe hacer clic en el botón **[!UICONTROL Reload]**.

>[!IMPORTANT]
>
>Tenga en cuenta que cuando se crea un código personalizado o se realizan modificaciones, al elegir cancelar la carga dentro del VEC, debe asegurarse de que la codificación o los cambios se realicen correctamente. Asegúrese de realizar un control de calidad adecuado para garantizar que el código personalizado y cualquier otra modificación se entregue según lo esperado.

Para cancelar la carga de una página dentro del VEC, haga clic en el botón **[!UICONTROL Cancel Loading]** mientras se carga la página. La página no se cargará en el VEC para esta actividad durante la sesión de edición actual.

Para continuar administrando experiencias en la actividad actual o agregar nuevas modificaciones, debe hacer clic en el botón **[!UICONTROL Reload]**.
