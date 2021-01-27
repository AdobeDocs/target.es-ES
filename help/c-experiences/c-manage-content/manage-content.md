---
keywords: content;assets;manage content;offers;manage assets;enter selection mode;selection mode
description: ¿Cómo administro ofertas de código e imagen?
title: Ofertas
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 70547a05155aa2909b0e66a1f26b0fd2cc730dd9
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 40%

---


# Ofertas

Utilice la biblioteca [!UICONTROL Ofertas] de [!DNL Adobe Target] para administrar la oferta de código y el contenido de oferta de imágenes.

1. Haga clic en **[!UICONTROL Ofertas]** para abrir la biblioteca.

   La biblioteca contiene las ofertas que se han configurado mediante [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) y API. Las ofertas creadas en [!DNL Target Classic] o en otras soluciones pueden editarse en [!DNL Target Standard/Premium].

   La página [!UICONTROL Ofertas] tiene dos fichas a la derecha: [!UICONTROL Ofertas de código] y [!UICONTROL Ofertas de imagen] que le permiten vista de ofertas por tipo.

   ![Página ofertas que muestra las fichas Ofertas de código y Ofertas de imagen](/help/c-experiences/c-manage-content/assets/offers-page.png)

1. (Opcional) Haga clic en la lista desplegable **[!UICONTROL Tipo]** para filtrar ofertas por tipo (Oferta HTML, [Fragmentos de experiencia](/help/c-experiences/c-manage-content/aem-experience-fragments.md), [Oferta de redirección](/help/c-experiences/c-manage-content/offer-redirect.md), [Oferta remota](/help/c-experiences/c-manage-content/about-remote-offers.md), [Ofertas JSON](/help/c-experiences/c-manage-content/create-json-offer.md) y [ Carpetas](/help/c-experiences/c-manage-content/create-content-folder.md)).

   ![](assets/offers_filter.png)

1. (Opcional) Haga clic en la lista desplegable **[!UICONTROL Origen]** para filtrar ofertas por origen (Adobe Target, Adobe Target Classic y Adobe Experience Manager).

1. (Opcional) Para realizar tareas adicionales, coloque el puntero sobre la oferta o carpeta deseada en la ficha [!UICONTROL Ofertas de código] y haga clic en el icono deseado.

   ![Opciones de Ofertas de código](assets/offer-picker-large.png)

   Las opciones incluyen:

   * Vista (Para obtener más información, consulte [Visualización de definiciones de ofertas](#section_6B059DD121434E6292CAB393507D010E) más abajo).
   * Editar  
   * Copiar  
   * Mover (por ejemplo, para mover uno o más elementos a una carpeta, haga clic en el icono **[!UICONTROL Mover]** del elemento deseado, haga clic en la carpeta que desee y, a continuación, haga clic en **[!UICONTROL Colocar]**).
   * Eliminar

   Según los permisos, es posible que no vea iconos para todas las opciones. Por ejemplo, un usuario con permisos [!UICONTROL Observador] no tiene derechos para utilizar la opción [!UICONTROL Copiar].

1. (Opcional) Para realizar tareas adicionales, coloque el puntero sobre la oferta o carpeta de imágenes que desee en la ficha [!UICONTROL Ofertas de imágenes] y haga clic en el icono deseado.

   ![Opciones de Ofertas de imágenes](/help/c-experiences/c-manage-content/assets/image-offers-icons.png)

   Las opciones incluyen:

   * Select
   * Descargar  
   * Ver propiedades
   * Editar  
   * Anotar
   * Copiar  

## Visualización de definiciones de oferta {#section_6B059DD121434E6292CAB393507D010E}

Puede vista los detalles de la definición de oferta en una tarjeta emergente de la biblioteca [!UICONTROL Ofertas] sin abrir la oferta.

Por ejemplo, se accede a la siguiente tarjeta de definición de oferta para una oferta HTML pasando el ratón por encima de una oferta en la lista [!UICONTROL Contenido] y, a continuación, haciendo clic en el icono de información:

![](assets/offer-card-html.png)

Está disponible la siguiente información:

* Nombre
* Fuente
* Tipo
* ID de oferta
* Ruta de oferta
* Última modificación

En cada tarjeta emergente de definición de la oferta, puede hacer clic en la pestaña [!UICONTROL Uso de la oferta] para ver las actividades que hacen referencia a una oferta de código. Esta funcionalidad no se aplica a ofertas de imagen. De esta forma, puede evitar que otras actividades se vean influidas mientras edita las ofertas. La información incluye [!UICONTROL Actividades en directo] y [!UICONTROL Actividades inactivas].

![](assets/offer-card-usage.png)

La siguiente es la tarjeta de definición de una oferta de redireccionamiento:

![](assets/offer-card-redirect.png)

Está disponible la siguiente información:

* Nombre
* Fuente
* Tipo
* ID de oferta
* Ruta de oferta
* Última modificación
* URL de redireccionamiento
* Incluir todos los parámetros de URL (activado o desactivado)
* Transmitir ID de sesión de mbox (activado o desactivado)

La siguiente es la tarjeta de definición de una oferta remota:

![](assets/offer-card-remote.png)

Está disponible la siguiente información:

* Nombre
* Fuente
* Tipo
* ID de oferta
* Ruta de oferta
* Última modificación
* Tipo de URL de redireccionamiento
* URL absoluta o relativa

## Vídeo de formación: El repositorio de contenido  ![Distintivo de información general](/help/assets/overview.png)

Este vídeo incluye información sobre la administración de ofertas.

* Conexión entre la [biblioteca de activos de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) y la biblioteca de contenido de Target
* Ofertas HTML personalizadas
* Oferta HTML personalizada en el Compositor de experiencias visuales

>[!VIDEO](https://video.tv.adobe.com/v/17387)