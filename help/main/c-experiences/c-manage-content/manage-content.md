---
keywords: contenido;activos;administrar contenido;ofertas;administrar recursos;activar modo de selección;modo de selección
description: Obtenga información sobre cómo administrar ofertas de código e imagen mediante la biblioteca Ofertas en Adobe Target.
title: ¿Cómo administro las ofertas de código e imagen?
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: f93e33e91fb7be9c0d1772a2014864b46c1dfe47
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 16%

---

# Ofertas

Utilice el [!UICONTROL Offers] biblioteca en [!DNL Adobe Target] para administrar el contenido de ofertas de código y ofertas de imagen.

1. Clic **[!UICONTROL Offers]** para abrir la biblioteca.

   La biblioteca contiene las ofertas que se han configurado mediante [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) y API. Las ofertas creadas en [!DNL Target Classic] o en otras soluciones pueden editarse en [!DNL Target Standard/Premium].

   El [!UICONTROL Offers] tiene dos pestañas a lo largo del lado derecho: [!UICONTROL Code Offers] y [!UICONTROL Image Offers] que permiten ver las ofertas por tipo.

   ![Página Ofertas que muestra las pestañas Ofertas de código y Ofertas de imagen](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. (Opcional) Haga clic en **[!UICONTROL Type]** lista desplegable para filtrar ofertas por tipo (Oferta de HTML, [Fragmentos de experiencias](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [Oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Oferta remota](/help/main/c-experiences/c-manage-content/about-remote-offers.md), [Ofertas JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md), y [Carpetas](/help/main/c-experiences/c-manage-content/create-content-folder.md)).

   ![imagen offers_filter](assets/offers_filter.png)

1. (Opcional) Haga clic en **[!UICONTROL Source]** para filtrar ofertas por fuente (Adobe Target, Adobe Target Classic y Adobe Experience Manager).

1. (Opcional) Realice tareas adicionales pasando el puntero sobre la oferta o carpeta deseada en la [!UICONTROL Code Offers] y, a continuación, haciendo clic en el icono deseado.

   ![Opciones de Ofertas de código](assets/offer-picker-large.png)

   Las opciones incluyen:

   * Ver (para obtener más información, consulte [Visualización de definiciones de oferta](#section_6B059DD121434E6292CAB393507D010E) abajo.)
   * Editar  
   * Copiar  
   * Mover (por ejemplo, para mover uno o más elementos a una carpeta, haga clic en el icono **[!UICONTROL Move]** para el elemento deseado, haga clic en la carpeta deseada y luego haga clic en **[!UICONTROL Drop]**.)
   * Eliminar

   En función de sus permisos, es posible que no vea iconos para todas las opciones. Por ejemplo, un usuario con [!UICONTROL Observer] permisos no tiene derechos para utilizar el [!UICONTROL Copy] opción.

   Para obtener información detallada sobre las tareas que se pueden realizar en ofertas y carpetas, consulte [Trabajar con contenido en la biblioteca de recursos](/help/main/c-experiences/c-manage-content/assets-working.md).

1. (Opcional) Realice tareas adicionales pasando el puntero sobre la oferta de imagen o la carpeta que desee en la [!UICONTROL Image Offers] y, a continuación, haciendo clic en el icono deseado.

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

Por ejemplo, para acceder a la siguiente tarjeta de definición de oferta de una oferta de HTML, haga clic en el icono de información:

![imagen offer-card-html](assets/offer-card-html-new.png)

Está disponible la siguiente información:

* Nombre
* ID de oferta
* Tipo
* Última modificación

Haga clic en [!UICONTROL View Full Details] para ver el contenido de la oferta y las actividades que hacen referencia a una oferta de código. De esta forma, puede evitar que otras actividades se vean influidas mientras edita las ofertas. La información incluye [!UICONTROL Live Activities] y [!UICONTROL Inactive Activities].

La información disponible en cada tarjeta varía según el tipo de oferta: Oferta de HTML, [Fragmentos de experiencias](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [Oferta de redireccionamiento](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Oferta remota](/help/main/c-experiences/c-manage-content/about-remote-offers.md), o [Ofertas JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

La funcionalidad de detalles de la oferta no se aplica a las ofertas de imagen.

<!--

## Training video: The Content Repository ![Overview badge](/help/main/assets/overview.png)

This video includes information about managing offers.

* Connection between the [Experience Cloud Asset Library](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) and the Target Content Library 
* Custom HTML Offers 
* Custom HTML Offer in the [!UICONTROL Visual Experience Composer]

>[!VIDEO](https://video.tv.adobe.com/v/17387)

-->
