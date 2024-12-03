---
keywords: contenido;activos;administrar contenido;ofertas;administrar recursos;activar modo de selección;modo de selección
description: Descubra cómo administrar de forma eficaz las ofertas de código e imagen mediante la biblioteca [!UICONTROL Offers].
title: ¿Cómo administro las ofertas de código e imagen?
feature: Experiences and Offers
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#beta newtab=true" tooltip="¿Qué son las funciones beta en  [!DNL Adobe Target]?"
hide: true
hidefromtoc: true
exl-id: f64aec3d-5f83-4bd1-8e64-df1779809812
source-git-commit: 6d18b76da95ad5c5b4d4144c75921a1c42313789
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 8%

---

# Ofertas

Descubra cómo administrar de forma eficaz las ofertas de código e imagen mediante la biblioteca [!UICONTROL Offers] en [!DNL Adobe Target].

>[!NOTE]
>
>Este artículo contiene información sobre las actualizaciones realizadas en la interfaz de usuario [!DNL Target] que actualmente forma parte de un programa de Beta. El equipo [!DNL Adobe Target] a menudo habilita nuevas características para clientes seleccionados con fines de prueba y comentarios. Una vez completado el período de prueba, estas características se habilitarán para todos los clientes en futuras versiones de [!DNL Target] y se anunciarán en [notas de la versión](/help/main/r-release-notes/release-notes.md).

Para mostrar la biblioteca [!UICONTROL Offers], haga clic en la ficha **[!UICONTROL Offers]** en la parte superior de la interfaz de usuario de [!DNL Target].

![Página de ofertas](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

AEM La biblioteca [!UICONTROL Offers] contiene ofertas que se han configurado mediante [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (), [!DNL Adobe Mobile Services] (AMS) y API. Las ofertas creadas en [!DNL Target Classic] o en otras soluciones pueden editarse en [!DNL Target Standard/Premium].

La biblioteca [!UICONTROL Offers] proporciona una descripción general de todas las ofertas de código e imagen y le permite realizar diversas acciones:

| Elemento | Descripción |
|--- |--- |
| Carril de navegación izquierdo | Cambiar entre mostrar [!UICONTROL Code Offers] o [!UICONTROL Image Offers]. |
| [!UICONTROL Show Folders] / [!UICONTROL Hide Folders]<P>![Icono Mostrar filtros/Ocultar filtros](/help/main/assets/icons/RailLeft.svg) | Haga clic en el icono **[!UICONTROL Show Folders]** o **[!UICONTROL Hide Folders]** para alternar entre mostrar la estructura de carpetas de ofertas o no mostrar la estructura de carpetas.<P>Para obtener más información, consulte [Crear carpetas de ofertas](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| Icono [!UICONTROL Show filters]<P>![Icono Mostrar filtros](/help/main/assets/icons/Filter.svg) | Haga clic en el icono **[!UICONTROL Show filters]** para filtrar ofertas por [!UICONTROL Type], [!UICONTROL Source] y [!UICONTROL AEM Type].<P>Para obtener más información, consulte [Aplicar filtros a la lista de ofertas](#filters) a continuación. |
| Campos de búsqueda | Utilice los campos **[!UICONTROL Search in]** para encontrar rápidamente una oferta o para reducir el número de ofertas mostradas en la biblioteca [!UICONTROL Offers]. Puede buscar por [!UICONTROL Offer Name], [!UICONTROL AEM Paths] o [!UICONTROL AEM Tags]. Las opciones de búsqueda son persistentes entre sesiones. |
| [!UICONTROL Create Folder] | Haga clic en **[!UICONTROL Create Folder]** para crear carpetas en la biblioteca [!UICONTROL Offer] para albergar ofertas de código, ofertas de imágenes y otras carpetas con el fin de crear una estructura de subcarpetas.<P>Para obtener más información, consulte [Crear carpetas de ofertas](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| [!UICONTROL [!UICONTROL Create Offer]] | Haga clic en **[!UICONTROL Create Offer]** para crear una oferta.<P>Para obtener más información sobre la creación de los distintos tipos de oferta, consulte: <ul><li>Oferta HTML</li><li>[Oferta JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[Oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[Oferta remota](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| Casillas de verificación de operaciones masivas<P>![Icono de operaciones en lotes](/help/main/assets/icons/Rectangle.svg) | Haga clic en las casillas de verificación [!UICONTROL Bulk Operations] para realizar operaciones masivas en todas las ofertas o en las ofertas seleccionadas.<P>Para obtener una lista de las acciones disponibles (según los permisos y el estado de la oferta), consulte [Realizar acciones rápidas](#quick-actions) a continuación. |
| [!UICONTROL Name] | Nombre de cada oferta.<P>Haga clic en el icono **[!UICONTROL Quick Info]** ( ![icono de información rápida](/help/main/assets/icons/InfoOutline.svg) ) junto a cada nombre de oferta para ver más información acerca de esa oferta en una tarjeta emergente, incluido el ID de oferta, el tipo, la fecha de la última modificación de la oferta y quién la modificó por última vez, etc.<p>Haga clic en el icono **[!UICONTROL More Actions]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) junto a cada nombre de oferta para abrir un menú que le permita realizar acciones rápidas en una actividad. Las siguientes acciones están disponibles (según los permisos y el estado de la oferta): [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete] y [!UICONTROL Move]. Para obtener más información sobre cada acción, consulte [Realizar acciones rápidas](#quick-actions) a continuación.<P>Haga clic en el encabezado de la tabla para ordenar la lista alfabéticamente en orden ascendente o descendente por nombre. |
| [!UICONTROL Type] | El tipo de oferta: [!UICONTROL HTML Offers], [[!UICONTROL Redirect Offers]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offers]](/help/main/c-experiences/c-manage-content/about-remote-offers.md) y [[!UICONTROL JSON Offers]](/help/main/c-experiences/c-manage-content/create-json-offer.md). |
| [!UICONTROL Source] | Muestra dónde se creó la oferta: [!DNL Adobe Target], [!DNL Adobe Target Classic] y [!DNL Adobe Experience Manager]. |
| [!UICONTROL Last updated] | Muestra la fecha y la hora de la última modificación de la oferta y quién la modificó.<P>Haga clic en el encabezado de la tabla para ordenar la lista en orden ascendente o descendente por fecha. |

## Aplicar filtros a la biblioteca Ofertas {#filters}

Haga clic en el icono **[!UICONTROL Show filters]** (icono ![Mostrar filtros en la página Ofertas](/help/main/assets/icons/Filter.svg)) para filtrar ofertas por [!UICONTROL Type], [!UICONTROL Source] y [!UICONTROL AEM Type].

El icono **[!UICONTROL Show filters]** le permite filtrar ofertas por las siguientes categorías:

* **[!UICONTROL Type]**: [!UICONTROL HTML Offer], [[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md) y [[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md).

* **[!UICONTROL Source]**: [!DNL Adobe Target], [!DNL Adobe Target Classic] y [!DNL Adobe Experience Manager].

* AEM **Tipo de**: [Fragmentos de contenido](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) y [Fragmentos de experiencias](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md). AEM Para obtener más información acerca de los distintos tipos de fragmentos, consulte [Información general sobre fragmentos de contenido y fragmentos de experiencias](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

Los filtros son persistentes en la sesión.

## Realizar acciones rápidas {#quick-actions}

Puede realizar las siguientes acciones rápidas haciendo clic en el icono correspondiente:

### Información rápida

Haga clic en el icono **[!UICONTROL Quick Info]** ( ![icono de información rápida](/help/main/assets/icons/InfoOutline.svg) ) junto a cada nombre de oferta para ver más información acerca de esa oferta en una tarjeta emergente, incluido el ID de oferta, el tipo, la fecha de la última modificación de la oferta y quién la modificó por última vez, etc. Las opciones disponibles dependen del tipo de oferta: [!UICONTROL HTML Offer], [[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md), [[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

### Más acciones

Las acciones disponibles para [!UICONTROL Code Offers] y para [!UICONTROL Image Offers] difieren ligeramente. Las secciones siguientes contienen más información:

#### [!UICONTROL Code Offer] opciones

Haga clic en el icono **[!UICONTROL More actions]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) junto a cada nombre de oferta para abrir un menú que le permita realizar acciones rápidas en una actividad.

Las siguientes acciones están disponibles (según los permisos y el estado de la oferta):

* [!UICONTROL Edit]
* [!UICONTROL Copy]
* [!UICONTROL Delete]
* [!UICONTROL Move] (por ejemplo, para mover uno o más elementos a una carpeta, haga clic en **[!UICONTROL Move]** junto al elemento deseado, haga clic en la carpeta deseada y, a continuación, haga clic en **[!UICONTROL Move]**.)

En función de sus permisos, es posible que no vea iconos para todas las opciones. Por ejemplo, un usuario con permisos de [!UICONTROL Observer] no tiene derechos para utilizar la opción [!UICONTROL Copy].

Para obtener información detallada sobre las tareas que puede realizar en ofertas y carpetas, consulte [Trabajar con contenido en la biblioteca de recursos](/help/main/c-experiences/c-manage-content/assets-working.md).

#### [!UICONTROL Image Offer] opciones

Para realizar tareas adicionales, pase el ratón sobre la oferta de imagen o la carpeta que quiera en la ficha [!UICONTROL Image Offers] y luego haga clic en el icono que quiera.

Las opciones incluyen:

* [!UICONTROL Select]
* [!UICONTROL Download]
* [!UICONTROL View Properties]
* [!UICONTROL More Actions]
* [!UICONTROL Edit]
* [!UICONTROL Annotate]
* [!UICONTROL Copy]

Para obtener información detallada sobre las tareas que puede realizar en ofertas y carpetas, consulte [Trabajar con contenido en la biblioteca de recursos](/help/main/c-experiences/c-manage-content/assets-working.md).

>[!NOTE]
>
>Las ofertas de imágenes no forman parte del modelo [Permisos de usuario de Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

## Visualización de definiciones de oferta {#section_6B059DD121434E6292CAB393507D010E}

Para ver los detalles de la definición de la oferta en una tarjeta emergente de la biblioteca [!UICONTROL Offers] sin abrir la oferta, haga clic en ( ![icono de información rápida](/help/main/assets/icons/InfoOutline.svg) ).

Está disponible la siguiente información:

* [!UICONTROL Name]
* [!UICONTROL Offer ID]
* [!UICONTROL Type]
* [!UICONTROL Last Modified]

Haga clic en el vínculo [!UICONTROL View Full Details] para ver los atributos y las actividades de la oferta que hacen referencia a una oferta de código en la tarjeta emergente de definición de cada oferta. Esta funcionalidad no se aplica a ofertas de imagen. De esta forma, puede evitar que otras actividades se vean influidas mientras edita las ofertas. La información incluye detalles para [!UICONTROL Live Activities] y [!UICONTROL Inactive Activities].
