---
keywords: biblioteca de contenido;recursos;anotar;copiar;eliminar recurso;descargar recurso;editar contenido;compartir tarjeta;ver propiedades de contenido
description: Aprenda a administrar ofertas de código e imagen en la biblioteca de ofertas de Adobe [!DNL Target] . Obtenga información sobre cómo ver los detalles de una oferta y cómo editar, copiar, mover o eliminar ofertas.
title: ¿Cómo se trabaja con el contenido en la biblioteca de ofertas?
feature: Experiencias y ofertas
exl-id: 2668ba68-29c8-4c3f-bebc-ba62760a8a61
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 37%

---

# Trabajar con contenido en la biblioteca de recursos

Información sobre las tareas que puede realizar en un recurso de la Biblioteca de contenido en [!DNL Adobe Target], incluidas las tareas de anotación, copia, eliminación, descarga, edición, uso compartido y visualización de propiedades.

1. Haga clic en **[!UICONTROL Ofertas]** > **[!UICONTROL Ofertas de código]** u **[!UICONTROL Ofertas de imágenes]**.

   ![Pestañas Ofertas de código y Ofertas de imágenes](/help/c-experiences/c-manage-content/assets/offers-both.png)

   Para obtener más información sobre la búsqueda en la biblioteca de ofertas y la creación de colecciones inteligentes, consulte [Filtro y búsqueda de contenido](/help/c-experiences/c-manage-content/filter-and-search-content.md#concept_3B59B8F025BF4CEA82ECC5199D365276).

1. (Opcional) Alterne entre [!UICONTROL Vista de tarjeta] y [!UICONTROL Vista de lista], haga clic en el icono [!UICONTROL Vista de tarjeta] o en el icono [!UICONTROL Vista de lista] en la esquina superior derecha de la biblioteca de contenido. También puede utilizar [!UICONTROL Ver configuración] para seguir configurando las columnas al ver la [!UICONTROL Vista de lista].

   La siguiente ilustración muestra las opciones disponibles al ver la [!UICONTROL Vista de lista]:

   ![Opciones de vista de lista](/help/c-experiences/c-manage-content/assets/view-settings-options.png)

1. Realice la acción deseada, tal como se explica en las secciones siguientes:

## Opciones de Ofertas de código

Al ver la página [!UICONTROL Ofertas de código], puede realizar las siguientes acciones en un elemento pasando el puntero sobre una oferta o carpeta y seleccionado el icono apropiado.

![Pase el ratón sobre los iconos de la ficha Ofertas de código](/help/c-experiences/c-manage-content/assets/code-offers-hover-icons.png)

* **Información**: Vea la información de la oferta.
* **Editar**: Edite la carpeta u oferta.
* **Copiar**: Copie la oferta. Copiar y luego editar la oferta le permite crear fácilmente una oferta nueva similar.
* **Mover**: Haga clic en el icono Mover , navegue hasta la ubicación a la que desea mover la oferta o carpeta y, a continuación, haga clic en el  **** menú desplegable. Por ejemplo, puede mover una o más carpetas a otra carpeta para crear subcarpetas. Haga clic en [!UICONTROL Borrar selección] para anular la selección de las ofertas o carpetas seleccionadas.
* **Eliminar**: Elimine la oferta o la carpeta. Consulte [Consideraciones al eliminar elementos](#delete).

## Opciones de Ofertas de imágenes

Al ver la página [!UICONTROL Ofertas de imágenes], puede realizar las siguientes acciones en un elemento pasando el puntero sobre una oferta o carpeta y seleccionado el icono apropiado.

La siguiente ilustración muestra los iconos al pasar el ratón por encima cuando se ve la [!UICONTROL Vista de tarjeta].

![Coloque el ratón sobre los iconos de la ficha Ofertas de imágenes cuando se encuentre en la vista de tarjeta](/help/c-experiences/c-manage-content/assets/image-offers-hover-icons.png)

La siguiente ilustración muestra los iconos al pasar el ratón por encima cuando se ve la [!UICONTROL Vista de lista]. Para mostrar los iconos, haga clic en un elemento de la lista.

![Coloque el ratón sobre los iconos de la ficha Ofertas de imágenes cuando se encuentre en la vista de lista](/help/c-experiences/c-manage-content/assets/list-view-hover.png)

* **Seleccione**: Seleccione una o varias carpetas en las que realizar las siguientes acciones:

   * Descargar
   * Copiar
   * Mover
   * Eliminar (Consulte [Consideraciones al eliminar elementos](#delete)).

   Seleccione una o varias ofertas de imágenes en las que realizar las siguientes acciones:

   * Compartir
   * Descargar  
   * Ver propiedades
   * Editar  
   * Anotar
   * Mover  


* **Descargar**: Descargue la oferta de imágenes o la carpeta y su contenido.
* **Ver propiedades**: Vea las propiedades del elemento. Asegúrese de hacer clic en la pestaña [!UICONTROL Basic] y en la pestaña [!UICONTROL Advanced] para ver toda la información disponible. Haga clic en el icono con forma de lápiz en la página de propiedades para editar las propiedades y agregar más información. Puede agregar información de metadatos, estado de publicación y datos de licencias.
* **Más acciones**: Mostrar opciones adicionales en la vista  [!UICONTROL de tarjeta].
* **Editar**: Edite la carpeta u oferta.
* **Anotar**: Agregue una nota al recurso. Haga clic en el recurso y, a continuación, seleccione el área donde quiera realizar una anotación y escriba la nota.
* **Copiar**: Copie la oferta. Copiar y luego editar la oferta le permite crear fácilmente una oferta nueva similar.

## Consideraciones al eliminar elementos {#delete}

* Puede eliminar una carpeta entera que contenga cualquier cantidad de activos y subcarpetas. Esta función está disponible en la interfaz de usuario de Target también en la interfaz de usuario de Recursos de Adobe Experience Cloud.
* Si elimina una carpeta con un gran número de imágenes, el proceso que se ejecuta detrás de las escenas puede tardar cierto tiempo (varios minutos) antes de que la interfaz de usuario se actualice para mostrar el estado final. La cantidad de tiempo necesaria es una función del número de imágenes, no del tamaño de estas. Diez minutos para 2000 imágenes sería una buena estimación. Puede continuar con otros trabajos y comprobar el estado final después de varios minutos para verificar la eliminación.
* Las carpetas que no estén vacías en la biblioteca de ofertas de imágenes se pueden eliminar. Si no se hace referencia a todas las imágenes de la carpeta en ninguna actividad, se eliminará toda la carpeta y su contenido. Si se hace referencia a algunas imágenes dentro de la carpeta en cualquier actividad, se eliminan todas las imágenes sin referencia, pero se conservan las imágenes y carpetas que contienen esas imágenes.

## Vídeo de formación: El ![distintivo Información general](/help/assets/overview.png) del repositorio de contenido

Este vídeo incluye información sobre la administración de contenido. (4:56)

* Conexión entre la [biblioteca de activos de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) y la biblioteca de contenido de Target
* Ofertas HTML personalizadas
* Oferta HTML personalizada en el Compositor de experiencias visuales

>[!VIDEO](https://video.tv.adobe.com/v/17387)
