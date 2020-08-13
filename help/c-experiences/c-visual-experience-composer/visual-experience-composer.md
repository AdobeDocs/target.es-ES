---
description: Información sobre el uso de VEC (Visual Experience Composer) en Adobe Target.
title: Compositor de experiencias visuales (VEC) de Adobe Target
feature: vec
uuid: f1e6f67e-1d7e-4806-8389-2ce165b534b4
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 97%

---


# Compositor de experiencias visuales (VEC){#visual-experience-composer-vec}

Información sobre el uso de VEC (Visual Experience Composer).

El VEC es una interfaz de usuario WYSIWYG que permite crear y probar fácilmente experiencias y ofertas personalizadas en el contexto del sitio. Puede crear experiencias y ofertas para actividades de Target arrastrando y soltando, intercambiando y modificando el diseño y el contenido de una página Web (u oferta) o una página web móvil.

El VEC es una de las características principales de [!DNL Adobe Target]. El VEC permite que los expertos en marketing y los diseñadores creen y cambien contenido por medio de una interfaz visual. Se pueden elegir muchas opciones de diseño sin tener que editar directamente el código. Editar HTML y JavaScript también es posible con las opciones de edición que se encuentran disponibles en el compositor.

On the Target **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** tab, you can enter the Default Visual Experience Composer URL.

![Configuración de URL predeterminada de VEC](/help/c-experiences/c-visual-experience-composer/assets/pref-default-url-new.png)

Esta dirección URL determina la página de inicio al abrir el VEC. Si no establece un valor predeterminado, comenzará con una página en blanco cuando abra el editor y deberá indicar una dirección URL entonces.

>[!NOTE]
>
>Algunos navegadores, como Firefox, pueden bloquear una página y evitar que se muestre en el VEC si esta contiene contenido mixto (por ejemplo, una página no segura en un sitio seguro). Si la página no se muestra, haga clic en el icono al lado de la dirección URL en la barra de direcciones del explorador y seleccione **[!UICONTROL Deshabilitar protección en esta página]**. Este problema no afecta a la visualización de las páginas de los visitantes del sitio.

El contenido de dentro de un iframe en la página no se puede modificar en el VEC. Para editar el contenido de dentro de un iframe, asegúrese de que el documento del iframe tenga habilitada la segmentación y luego cargue la dirección URL del iframe en el VEC.

Puede usar los menús desplegables de la parte superior de la página para ver su página tal como se mostrará a diferentes audiencias o con diferentes experiencias. Puede asignar un nombre a cada experiencia en la segunda lista desplegable. Por ejemplo, si está probando la ubicación del vínculo a la página de inicio en la barra de navegación, sería interesante poner a la experiencia en la que aparece primero el vínculo a la página de inicio un nombre como “Vínculo a Inicio”, para que sea más fácil identificar las experiencias de la lista.

>[!NOTE]
>
>Los cambios en la estructura de una página que afecten a las ubicaciones empleadas en una actividad creada en esa página podrían producir errores al editar la experiencia. Si se ha cambiado una ubicación fuera del VEC es posible que Target no encuentre la ubicación donde se cambió el contenido.

A medida que mueve el ratón por la página, un cuadro contextual sigue al cursor, destacando los elementos en la página.

![VEC resaltado](/help/c-experiences/c-visual-experience-composer/assets/vec-highlight-new.png)

Haga clic en el icono **[!UICONTROL Superposiciones]** para cambiar la forma en que se resalta el elemento. Por ejemplo, puede elegir resaltar solo imágenes, vínculos, mboxes regionales, modificaciones o JavaScript. Puede cambiar el color del resaltado. También puede especificar el color de resaltado y el tipo de relleno usado para resaltar distintos tipos de elementos.

![Cambios en la configuración de superposición](/help/c-experiences/c-visual-experience-composer/assets/change-overlay.png)

Haga clic en un elemento resaltado para acceder al menú de opciones disponibles para dicho tipo de elemento. Por ejemplo, puede hacer clic en una imagen y seleccionar **[!UICONTROL Editar > Texto/HTML]** para modificar el texto, o bien hacer clic en un botón y cambiar el color del fondo. Puede usar los botones de la parte superior izquierda para activar y desactivar las superposiciones.

También puede hacer clic en **[!UICONTROL Examinar]** y navegar a una página que esté disponible como página principal (por ejemplo, la página de envío o el carro de compras) y probar los cambios en esa página. También puede acceder a los elementos de la página que están disponibles cuando mueve el cursor por encima, como los menús flotantes y los minicarros. Cuando termine de navegar por la página, haga clic en **[!UICONTROL Componer]** para editar la experiencia. Por ejemplo, puede interesarle cambiar el diseño de una lista desplegable de carro de compras o un carrusel de imágenes.

>[!NOTE]
>
>Si un estado de movimiento del cursor por encima depende de JavaScript, asegúrese de que la opción **[!UICONTROL Deshabilitar JavaScript]** no esté seleccionada. JavaScript debe estar habilitado para poder editar los elementos JavaScript.

Para obtener información sobre las opciones disponibles en el VEC, consulte [Opciones del Compositor de experiencias visuales](../../c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81).

Puede realizar algunas modificaciones en una página mientras se carga la página (o después de que la página no se haya cargado), o puede cancelar la carga de la página en el VEC. Para obtener más información, consulte:

* [Edición de una página mientras se carga o después de que la página no se haya cargado](#loading)
* [Cancelación de la carga de una página dentro del VEC](#cancel-loading)

## Edición de una página mientras se carga o después de que la página no se haya cargado {#loading}

Puede realizar muchas acciones antes de que la página se cargue en VEC o incluso si la página no se carga completamente (por ejemplo, si el código personalizado ya no funciona).

Algunas razones por las cuales es posible que desee acceder o editar una página mientras ésta se carga dentro del VEC o después de que no se cargue:

* Desea realizar una modificación sencilla de una página, como agregar un código personalizado o cambiar el nombre de una experiencia
* Desea copiar código personalizado existente de una página que ya no es accesible
* Sabe que una página no se cargará dentro del VEC pero de todas maneras desea realizar ediciones simples

Mientras la página se carga (o después de que dé error al cargar), el panel [!UICONTROL Experiencias], el panel [!UICONTROL Modificaciones] y la configuración en la parte superior de la experiencia (Superposiciones, Modificaciones, Configurar, etc.) están accesibles.

La siguiente ilustración muestra que puede insertar código personalizado o realizar otras acciones mientras la página sigue cargándose:

![Carga de página](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/loading-page.png)

## Cancelación de la carga de una página dentro del VEC {#cancel-loading}

Puede cancelar la carga de una página dentro del VEC para desbloquear la edición de la actividad sin esperar a que se cargue la página. Esta función ahorra tiempo y le ayuda a realizar ediciones sencillas o a insertar código personalizado de forma más eficaz sin esperar a que la página cargue dentro del VEC.

Algunas de las razones por las que es posible que desee cancelar la carga de páginas dentro del VEC son:

* Desea realizar pequeñas ediciones en las modificaciones existentes
* Desea eliminar una o más modificaciones existentes
* Desea insertar o editar código personalizado
* Introdujo la dirección URL incorrecta para la página
* Desea habilitar o deshabilitar JavaScript antes de cargar la página en el VEC
* Desea agregar más reglas de prueba de plantilla a los criterios de Entrega de página
* Desea anular la opción del Compositor de experiencias mejorado (EEC) global al cargar una página a través del EEC o solo iframe podría depender o variar de una página a otra

Después de cancelar la carga de páginas en el VEC, puede cambiar entre experiencias en la actividad sin esperar a que se cargue la página. Para volver a ver la página dentro del VEC, debe hacer clic en el botón **[!UICONTOL Recargar]**.

>[!IMPORTANT]
>
>Tenga en cuenta que cuando se crea un código personalizado o se realizan modificaciones, al elegir cancelar la carga dentro del VEC, debe asegurarse de que la codificación o los cambios se realicen correctamente. Asegúrese de realizar un control de calidad adecuado para garantizar que el código personalizado y cualquier otra modificación se entregue según lo esperado.

Para cancelar la carga de una página dentro del VEC, haga clic en el botón **[!UICONTROL Cancelar carga]** mientras se carga la página. La página no se cargará en el VEC para esta actividad durante la sesión de edición actual.

![Botón Cancelar carga](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/cancel-loading.png)

Para continuar administrando experiencias en la actividad actual o agregar nuevas modificaciones, debe hacer clic en el botón **[!UICONTROL Recargar]**.

![Botón Recargar](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/reload-in-vec.png)

>[!NOTE]
>
>Actualmente existe un problema conocido con esta función que se solucionará en la próxima versión. Para obtener más información, consulte “Cancelación de la carga de una página dentro del VEC” en la página [Problemas conocidos y resueltos](/help/r-release-notes/known-issues-resolved-issues.md#cancel).

## Vídeos de formación

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Compositor de experiencias visuales (1 de 2) (7:17) ![Distintivo de tutorial](/help/assets/tutorial.png)

* Cambiar el contenido de una página
* Cambiar el diseño de una página

>[!VIDEO](https://video.tv.adobe.com/v/17399)

### Compositor de experiencias visuales (2 de 2) (7:29) ![Distintivo de tutorial](/help/assets/tutorial.png)

* Cambiar el nombre de una experiencia y duplicarla
* Crear una experiencia de redirección
* Segmentar una actividad en una sola dirección URL o un grupo de direcciones URL
* Crear una actividad de varias páginas
* Obtener una vista previa y generar experiencia para sitios web adaptables
* Usar superposiciones para destacar tipos de elementos

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Horario de oficina: Distintivo ![de tutorial del Compositor de experiencias visuales](/help/assets/tutorial.png)

Este vídeo es una grabación de “[Horario de oficina](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)”, una iniciativa dirigida por el equipo de atención al cliente de Adobe.

* Cómo funciona el Compositor de experiencias visuales
* Cómo evitar problemas comunes con el Compositor de experiencias visuales
* Soluciones alternativas con el Compositor de experiencias visuales

>[!VIDEO](https://video.tv.adobe.com/v/20784/)