---
keywords: contenido;activos;administrar contenido;ofertas;administrar recursos;activar modo de selección;modo de selección
description: Obtenga información sobre cómo administrar ofertas de código e imagen mediante la biblioteca Ofertas.
title: ¿Cómo administro las ofertas de código e imagen?
feature: Experiences and Offers
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#beta newtab=true" tooltip="¿Qué son las funciones beta en  [!DNL Adobe Target]?"
hide: true
hidefromtoc: true
exl-id: f64aec3d-5f83-4bd1-8e64-df1779809812
source-git-commit: 5d14dfd700cb1cec0fa62f66da1400bc8d7fd109
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 17%

---

# Ofertas

Utilice el [!UICONTROL Offers] biblioteca en [!DNL Adobe Target] para administrar el código y el contenido de ofertas de imagen.

>[!NOTE]
>
>Este artículo contiene información sobre las actualizaciones de [!DNL Target] interfaz de usuario que actualmente forma parte de un programa beta. El [!DNL Adobe Target] A menudo, el equipo de habilita nuevas funciones para clientes seleccionados con fines de prueba y comentarios. Una vez completado el periodo de prueba, estas funciones se habilitarán para todos los clientes en el futuro [!DNL Target Standard/Premium] Versiones de y anunciadas en las notas de la versión.

Haga clic en **[!UICONTROL Offers]** en la parte superior de la pestaña [!DNL Target] IU para mostrar la [!UICONTROL Offers] biblioteca.

![Biblioteca de ofertas en Adobe Target](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

El [!UICONTROL Offers] La biblioteca de contiene ofertas que se han configurado mediante [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] AEM (), [!DNL Adobe Mobile Services] (AMS) y API. Las ofertas creadas en [!DNL Target Classic] o en otras soluciones pueden editarse en [!DNL Target Standard/Premium].

La biblioteca Ofertas proporciona una descripción general de todas las ofertas de código e imagen y permite realizar varias acciones:

| Elemento | Descripción |
|--- |--- |
| Carril de navegación izquierdo | Cambiar entre listados [!UICONTROL Code Offers] o [!UICONTROL Image Offers]. |
| [!UICONTROL Show filters] icono<P>![Mostrar icono de filtros](/help/main/c-activities/assets/show-filters-icon.png) | Haga clic en **[!UICONTROL Show filters]** icono para filtrar ofertas por [!UICONTROL Type], [!UICONTROL Source], y [!UICONTROL AEM Type]<P>Para obtener más información, consulte [Aplicar filtros a la lista Ofertas](#filters) más abajo. |
| Campos de búsqueda | Utilice el **[!UICONTROL Search in]** para encontrar rápidamente una oferta o reducir el número de ofertas mostradas en la [!UICONTROL Offers] biblioteca. Puede buscar por [!UICONTROL Offer Name], [!UICONTROL AEM Paths], o [!UICONTROL AEM Tags]. |
| [!UICONTROL Create Folder] | Haga clic en Crear carpeta para crear carpetas en [!UICONTROL Offer] biblioteca para albergar ofertas de código, ofertas de imágenes y otras carpetas para crear una estructura de subcarpetas. Para obtener más información, consulte [Creación de carpetas de ofertas](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| [!UICONTROL [!UICONTROL Create Offer]] | Cree una oferta. Para obtener más información sobre la creación de los distintos tipos de oferta, consulte: <ul><li>Oferta HTML</li><li>[Oferta JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[Oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[Oferta remota](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| Casillas de verificación de operaciones masivas | Realizar operaciones masivas en todas las actividades o en las actividades seleccionadas.<P>Para ver una lista de las acciones disponibles (en función de los permisos y el estado de la oferta), consulte [Realizar acciones rápidas](#quick-actions) más abajo. |
| [!UICONTROL Name] | Nombre de cada oferta.<P>Haga clic en **[!UICONTROL Quick Info]** junto a cada nombre de oferta para ver más información sobre esa oferta en una tarjeta emergente, incluido el ID de oferta, el tipo, la fecha de la última modificación de la oferta y quién la modificó, etc.<p>Haga clic en **[!UICONTROL More actions]** (los puntos suspensivos horizontales) junto al nombre de cada oferta para abrir un menú que le permita realizar acciones rápidas en una actividad. Las siguientes acciones están disponibles (según los permisos y el estado de la oferta): [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete], y [!UICONTROL Move]. Para obtener más información sobre cada acción, consulte [Realizar acciones rápidas](#quick-actions) más abajo.<P>Haga clic en el encabezado de la tabla para ordenar la lista alfabéticamente en orden ascendente o descendente por nombre. |
| [!UICONTROL Type] | El tipo de oferta: Ofertas de HTML, [Ofertas de redirección](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Ofertas remotas](/help/main/c-experiences/c-manage-content/about-remote-offers.md), y [Ofertas JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md). |
| [!UICONTROL Source] | Muestra dónde se creó la oferta: [!DNL Adobe Target], [!DNL Adobe Target Classic], y [!DNL Adobe Experience Manager]. |

## Aplicar filtros a la biblioteca Ofertas {#filters}

Haga clic en **[!UICONTROL Show filters]** icono ( ![Mostrar icono de filtros en la página Ofertas](/help/main/c-experiences/c-manage-content/assets/show-filters-icon.png) ) para filtrar ofertas por [!UICONTROL Type], [!UICONTROL Source], y [!UICONTROL AEM Type].

![imagen offers_filter](assets/offers-filter-new.png)

El **[!UICONTROL Show filters]** El icono permite filtrar ofertas por las siguientes categorías:

* **Tipo**: Oferta de HTML, [Oferta JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md), [Oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Oferta remota](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

* **Origen**: [!DNL Adobe Target], [!DNL Adobe Target Classic], y [!DNL Adobe Experience Manager].

* **AEM Tipo de**: [Fragmentos de contenido](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) y [Fragmentos de experiencias](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md). Para obtener más información sobre los distintos tipos de fragmento, consulte [AEM Resumen de fragmentos de contenido y fragmentos de experiencias](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## Realizar acciones rápidas {#quick-actions}

Puede realizar las siguientes acciones rápidas haciendo clic en el icono correspondiente:

### Información rápida

Haga clic en **[!UICONTROL Quick Info]** junto a cada nombre de oferta para ver más información sobre esa oferta en una tarjeta emergente, incluido el ID de oferta, el tipo, la fecha de la última modificación de la oferta y quién la modificó, etc. Las opciones disponibles dependen del tipo de oferta: Oferta de HTML, [Oferta JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md), [Oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Oferta remota](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

![](/help/main/c-experiences/c-manage-content/assets/quick-actions.png)

### Más acciones

Las acciones disponibles para Ofertas de código y para Ofertas de imágenes difieren ligeramente. Las secciones siguientes contienen más información:

#### [!UICONTROL Code Offer] opciones

Haga clic en **[!UICONTROL More actions]** (los puntos suspensivos horizontales) junto al nombre de cada oferta para abrir un menú que le permita realizar acciones rápidas en una actividad. Las siguientes acciones están disponibles (según los permisos y el estado de la oferta): [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete], y [!UICONTROL Move].

![Opción Más acciones en la biblioteca de ofertas de Target](/help/main/c-experiences/c-manage-content/assets/more-actions.png)

* Editar  
* Copiar  
* Eliminar
* Mover (por ejemplo, para mover uno o más elementos a una carpeta, haga clic en el icono **[!UICONTROL Move]** para el elemento deseado, haga clic en la carpeta deseada y luego haga clic en **[!UICONTROL Drop]**.)

En función de sus permisos, es posible que no vea iconos para todas las opciones. Por ejemplo, un usuario con [!UICONTROL Observer] permisos no tiene derechos para utilizar el [!UICONTROL Copy] opción.

Para obtener información detallada sobre las tareas que se pueden realizar en ofertas y carpetas, consulte [Trabajar con contenido en la biblioteca de recursos](/help/main/c-experiences/c-manage-content/assets-working.md).

#### [!UICONTROL Image Offer] opciones

Para realizar tareas adicionales, pase el ratón sobre la oferta de imagen o la carpeta que desee en la [!UICONTROL Image Offers] y, a continuación, haciendo clic en el icono deseado.

![Opciones de ofertas de imágenes](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

Las opciones incluyen:

* Seleccionar
* Descargar  
* Ver propiedades
* Editar  
* Anotar
* Copiar  

Para obtener información detallada sobre las tareas que se pueden realizar en ofertas y carpetas, consulte [Trabajar con contenido en la biblioteca de recursos](/help/main/c-experiences/c-manage-content/assets-working.md).

>[!NOTE]
>
>Las ofertas de imágenes no forman parte de [Permisos de usuario de Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) modelo.

## Visualización de definiciones de oferta {#section_6B059DD121434E6292CAB393507D010E}

Puede ver los detalles de la definición de la oferta en una tarjeta emergente de la [!UICONTROL Offers] sin abrir la oferta.

Por ejemplo, para acceder a la siguiente definición de oferta de una oferta de HTML, pase el ratón sobre una oferta de la [!UICONTROL Content] y, a continuación, haciendo clic en el icono de información:

![imagen offer-card-html](assets/offer-card-html.png)

Está disponible la siguiente información:

* Nombre
* Fuente
* Tipo
* ID de oferta
* Ruta de oferta
* Última modificación

Haga clic en [!UICONTROL Offer Usage] para ver las actividades que hacen referencia a una oferta de código en la tarjeta emergente de definición de cada oferta. Esta funcionalidad no se aplica a ofertas de imagen. De esta forma, puede evitar que otras actividades se vean influidas mientras edita las ofertas. La información incluye [!UICONTROL Live Activities] y [!UICONTROL Inactive Activities].

![imagen offer-card-usage](assets/offer-card-usage.png)

La siguiente es la tarjeta de definición de una oferta de redireccionamiento:

![imagen de redireccionamiento de tarjeta de oferta](assets/offer-card-redirect.png)

Está disponible la siguiente información:

* Nombre
* Fuente
* Tipo
* ID de oferta
* Ruta de oferta
* Última modificación
* URL de redireccionamiento
* Incluir todos los parámetros de URL (activado o desactivado)
* Transferir ID de sesión de mbox (activado o desactivado)

La siguiente es la tarjeta de definición de una oferta remota:

![imagen offer-card-remote](assets/offer-card-remote.png)

Está disponible la siguiente información:

* Nombre
* Fuente
* Tipo
* ID de oferta
* Ruta de oferta
* Última modificación
* Tipo de URL de redireccionamiento
* URL absoluta o relativa

## Vídeo de formación: El repositorio de contenido ![Distintivo Información general](/help/main/assets/overview.png)

Este vídeo incluye información sobre la administración de ofertas.

* Conexión entre la [biblioteca de activos de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) y la biblioteca de contenido de Target
* Ofertas HTML personalizadas
* Oferta HTML personalizada en el Compositor de experiencias visuales

>[!VIDEO](https://video.tv.adobe.com/v/17387)
