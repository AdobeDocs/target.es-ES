---
keywords: contenido;activos;administrar contenido;ofertas;administrar recursos;activar modo de selección;modo de selección
description: Descubra cómo administrar de forma eficaz las ofertas de código e imagen mediante la biblioteca [!UICONTROL Ofertas].
title: ¿Cómo administro las ofertas de código e imagen?
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
TQID: https://experienceleague.adobe.com/A8ZLHW-FrWHGPJR7P-mhl2pO6SPoDc--LWpFEjtQzBY
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 958
ht-degree: 7%

---

# Ofertas

Descubra cómo administrar de forma eficaz las ofertas de código e imagen mediante la biblioteca [!UICONTROL Ofertas] en [!DNL Adobe Target].

Para mostrar la biblioteca [!UICONTROL Ofertas], haga clic en la ficha **[!UICONTROL Ofertas]** en la parte superior de la interfaz de usuario de [!DNL Target].

![Página de ofertas](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

La biblioteca [!UICONTROL Ofertas] contiene ofertas que se han configurado mediante [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) y API. Las ofertas creadas en [!DNL Target Classic] o en otras soluciones pueden editarse en [!DNL Target Standard/Premium].

La biblioteca [!UICONTROL Ofertas] proporciona una descripción general de todas las ofertas de código e imagen y le permite realizar diversas acciones:

| Elemento | Descripción |
|--- |--- |
| Carril de navegación izquierdo | Cambiar entre mostrar [!UICONTROL Ofertas de código] u [!UICONTROL Ofertas de imagen]. |
| [!UICONTROL Mostrar carpetas] / [!UICONTROL Ocultar carpetas]<P>![Icono Mostrar filtros/Ocultar filtros](/help/main/assets/icons/RailLeft.svg) | Haga clic en el icono **[!UICONTROL Mostrar carpetas]** o **[!UICONTROL Ocultar carpetas]** para alternar entre mostrar la estructura de carpetas de ofertas o no mostrar la estructura de carpetas.<P>Para obtener más información, consulte [Crear carpetas de ofertas](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| [!UICONTROL Mostrar filtros] icono<P>![Icono Mostrar filtros](/help/main/assets/icons/Filter.svg) | Haga clic en el icono **[!UICONTROL Mostrar filtros]** para filtrar ofertas por [!UICONTROL Tipo], [!UICONTROL Source] y [!UICONTROL Tipo de AEM].<P>Para obtener más información, consulte [Aplicar filtros a la lista de ofertas](#filters) a continuación. |
| Buscar campos | Use **[!UICONTROL Buscar en]** campos para encontrar rápidamente una oferta o para reducir el número de ofertas mostradas en la biblioteca [!UICONTROL Ofertas]. Puede buscar por [!UICONTROL Nombre de oferta], [!UICONTROL Rutas de AEM] o [!UICONTROL Etiquetas de AEM]. Las opciones de búsqueda son persistentes entre sesiones. |
| [!UICONTROL Crear carpeta] | Haga clic en **[!UICONTROL Crear carpeta]** para crear carpetas en la biblioteca [!UICONTROL Oferta] que contendrá ofertas de código, ofertas de imágenes y otras carpetas para crear una estructura de subcarpetas.<P>Para obtener más información, consulte [Crear carpetas de ofertas](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| [!UICONTROL [!UICONTROL Crear oferta]] | Haga clic en **[!UICONTROL Crear oferta]** para crear una oferta.<P>Para obtener más información sobre la creación de los distintos tipos de oferta, consulte: <ul><li>Oferta HTML</li><li>[Oferta JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[Oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[Oferta remota](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| Casillas de verificación de operaciones masivas<P>![Icono de operaciones en lotes](/help/main/assets/icons/Rectangle.svg) | Haga clic en las casillas de verificación de [!UICONTROL Operaciones masivas] para realizar operaciones masivas en todas las ofertas o en las ofertas seleccionadas.<P>Para obtener una lista de las acciones disponibles (según los permisos y el estado de la oferta), consulte [Realizar acciones rápidas](#quick-actions) a continuación. |
| [!UICONTROL Nombre] | Nombre de cada oferta.<P>Haga clic en el icono **[!UICONTROL Información rápida]** ( ![Icono de información rápida](/help/main/assets/icons/InfoOutline.svg) ) junto a cada nombre de oferta para ver más información sobre esa oferta en una tarjeta emergente, incluidos el ID de oferta, el tipo, la fecha de la última modificación de la oferta y quién la modificó, etc.<p>Haga clic en el icono **[!UICONTROL Más acciones]** ( ![Icono de más acciones](/help/main/assets/icons/MoreSmallList.svg) ) junto a cada nombre de oferta para abrir un menú que le permita realizar acciones rápidas en una actividad. Las siguientes acciones están disponibles (según los permisos y el estado de la oferta): [!UICONTROL Editar], [!UICONTROL Copiar], [!UICONTROL Eliminar] y [!UICONTROL Mover]. Para obtener más información sobre cada acción, consulte [Realizar acciones rápidas](#quick-actions) a continuación.<P>Haga clic en el encabezado de la tabla para ordenar la lista alfabéticamente en orden ascendente o descendente por nombre. |
| [!UICONTROL Tipo] | El tipo de oferta: [!UICONTROL Ofertas HTML], [[!UICONTROL Ofertas de redireccionamiento]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Ofertas remotas]](/help/main/c-experiences/c-manage-content/about-remote-offers.md) y [[!UICONTROL Ofertas JSON]](/help/main/c-experiences/c-manage-content/create-json-offer.md). |
| [!UICONTROL Source] | Muestra dónde se creó la oferta: [!DNL Adobe Target], [!DNL Adobe Target Classic] y [!DNL Adobe Experience Manager]. |
| [!UICONTROL Última actualización] | Muestra la fecha y la hora de la última modificación de la oferta y quién la modificó.<P>Haga clic en el encabezado de la tabla para ordenar la lista en orden ascendente o descendente por fecha. |

## Aplicar filtros a la biblioteca Ofertas {#filters}

Haga clic en el icono **[!UICONTROL Mostrar filtros]** (![Mostrar filtros en la página Ofertas](/help/main/assets/icons/Filter.svg)) para filtrar ofertas por [!UICONTROL Tipo], [!UICONTROL Source] y [!UICONTROL Tipo de AEM].

El icono **[!UICONTROL Mostrar filtros]** le permite filtrar ofertas según las siguientes categorías:

* **[!UICONTROL Tipo]**: [!UICONTROL Oferta HTML], [[!UICONTROL Oferta de redireccionamiento]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Oferta remota]](/help/main/c-experiences/c-manage-content/about-remote-offers.md) y [[!UICONTROL Oferta JSON]](/help/main/c-experiences/c-manage-content/create-json-offer.md).

* **[!UICONTROL Source]**: [!DNL Adobe Target], [!DNL Adobe Target Classic] y [!DNL Adobe Experience Manager].

* **Tipo de AEM**: [Fragmentos de contenido](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) y [Fragmentos de experiencias](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md). Para obtener más información sobre los distintos tipos de fragmento, consulte [Información general sobre fragmentos de contenido y fragmentos de experiencias de AEM](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

Los filtros son persistentes en la sesión.

## Realizar acciones rápidas {#quick-actions}

Puede realizar las siguientes acciones rápidas haciendo clic en el icono correspondiente:

### Información rápida

Haga clic en el icono **[!UICONTROL Información rápida]** ( ![Icono de información rápida](/help/main/assets/icons/InfoOutline.svg) ) junto a cada nombre de oferta para ver más información sobre esa oferta en una tarjeta emergente, incluidos el ID de oferta, el tipo, la fecha de la última modificación de la oferta y quién la modificó, etc. Las opciones disponibles dependen del tipo de oferta: [!UICONTROL Oferta HTML], [[!UICONTROL Oferta JSON]](/help/main/c-experiences/c-manage-content/create-json-offer.md), [[!UICONTROL Oferta de redireccionamiento]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Oferta remota]](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

### Más acciones

Las acciones disponibles para [!UICONTROL Ofertas de código] y para [!UICONTROL Ofertas de imagen] difieren ligeramente. Las secciones siguientes contienen más información:

#### [!UICONTROL Oferta de código] opciones

Haga clic en el icono **[!UICONTROL Más acciones]** ( ![Icono de Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) junto a cada nombre de oferta para abrir un menú que le permita realizar acciones rápidas en una actividad.

Las siguientes acciones están disponibles (según los permisos y el estado de la oferta):

* [!UICONTROL Editar]
* [!UICONTROL Copiar]
* [!UICONTROL Eliminar]
* [!UICONTROL Mover] (por ejemplo, para mover uno o más elementos a una carpeta, haga clic en **[!UICONTROL Mover]** junto al elemento deseado, haga clic en la carpeta deseada y, a continuación, haga clic en **[!UICONTROL Mover]**).

En función de sus permisos, es posible que no vea iconos para todas las opciones. Por ejemplo, un usuario con permisos de [!UICONTROL Observer] no tiene derechos para usar la opción [!UICONTROL Copiar].

Para obtener información detallada sobre las tareas que puede realizar en ofertas y carpetas, consulte [Trabajar con contenido en la biblioteca de recursos](/help/main/c-experiences/c-manage-content/assets-working.md).

#### Opciones de [!UICONTROL oferta de imagen]

Para realizar tareas adicionales, pase el ratón sobre la carpeta u oferta de imágenes que quiera en la ficha [!UICONTROL Ofertas de imágenes] y luego haga clic en el icono que quiera.

Las opciones incluyen:

* [!UICONTROL Select]
* [!UICONTROL Descargar]
* [!UICONTROL Ver propiedades]
* [!UICONTROL Más acciones]
* [!UICONTROL Editar]
* [!UICONTROL Anotar]
* [!UICONTROL Copiar]

Para obtener información detallada sobre las tareas que puede realizar en ofertas y carpetas, consulte [Trabajar con contenido en la biblioteca de recursos](/help/main/c-experiences/c-manage-content/assets-working.md).

>[!NOTE]
>
>Las ofertas de imágenes no forman parte del modelo [Permisos de usuario de Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

## Visualización de definiciones de oferta {#section_6B059DD121434E6292CAB393507D010E}

Para ver los detalles de la definición de la oferta en una tarjeta emergente de la biblioteca [!UICONTROL Ofertas] sin abrir la oferta, haga clic en ( ![icono de información rápida](/help/main/assets/icons/InfoOutline.svg) ).

Está disponible la siguiente información:

* [!UICONTROL Nombre]
* [!UICONTROL ID de oferta]
* [!UICONTROL Tipo]
* [!UICONTROL Última modificación]

Haga clic en el vínculo [!UICONTROL Ver detalles completos] para ver los atributos y actividades de la oferta que hacen referencia a una oferta de código en la tarjeta emergente de definición de cada oferta. Esta funcionalidad no se aplica a ofertas de imagen. De esta forma, puede evitar que otras actividades se vean influidas mientras edita las ofertas. La información incluye detalles de [!UICONTROL Actividades activas] y [!UICONTROL Actividades inactivas].
