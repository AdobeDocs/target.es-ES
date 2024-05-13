---
keywords: biblioteca de contenido;recursos;anotar;copiar;eliminar recurso;descargar recurso;editar contenido;compartir tarjeta;ver propiedades de contenido
description: Obtenga información sobre cómo administrar ofertas de código e imagen en la [!DNL Target] [!UICONTROL Offers] biblioteca.
title: ¿Cómo puedo trabajar con contenido en? [!UICONTROL Offers] ¿Biblioteca?
feature: Experiences and Offers
hide: true
hidefromtoc: true
source-git-commit: 5931aef4a16e6e9777112fdda4b3277f8e6f7386
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 33%

---

# Trabajar con contenido en la biblioteca de recursos

Información sobre las tareas que se pueden realizar en un recurso de la biblioteca de contenido en [!DNL Adobe Target] incluida la anotación, copia, eliminación, descarga, edición, uso compartido y visualización de propiedades.

1. Clic **[!UICONTROL Offers]** > **[!UICONTROL Code Offers]** o **[!UICONTROL Image Offers]**.

   ![Pestañas Ofertas de código y Ofertas de imágenes](/help/main/c-experiences/c-manage-content/assets/offers-both.png)

   Para obtener más información sobre la búsqueda en la biblioteca de ofertas y la creación de colecciones inteligentes, consulte [Filtro y búsqueda de contenido](/help/main/c-experiences/c-manage-content/filter-and-search-content.md#concept_3B59B8F025BF4CEA82ECC5199D365276).

1. (Opcional) Alternar entre las [!UICONTROL Card View] y [!UICONTROL List View], haga clic en [!UICONTROL Card View] o el icono [!UICONTROL List View] en la esquina superior derecha de la biblioteca de contenido. También puede utilizar [!UICONTROL View Settings] para configurar las columnas al ver el [!UICONTROL List View].

   La siguiente ilustración muestra las opciones disponibles al ver el [!UICONTROL List View]:

   ![Opciones de vista de lista](/help/main/c-experiences/c-manage-content/assets/view-settings-options.png)

1. Realice la acción deseada, tal como se explica en las siguientes secciones:

## Opciones de Ofertas de código

Al ver el [!UICONTROL Code Offers] , puede realizar las siguientes acciones en un elemento pasando el puntero sobre una oferta o carpeta y seleccionando el icono correspondiente.

![Iconos de activación en la pestaña Ofertas de código](/help/main/c-experiences/c-manage-content/assets/code-offers-hover-icons.png)

* **Información**: vea la información de la oferta.
* **Editar**: edite la carpeta u oferta.
* **Copiar**: copie la oferta. Copiar y luego editar la oferta permite crear fácilmente una oferta nueva similar.
* **Mover**: haga clic en el icono Mover, navegue hasta la ubicación a la que desee mover la oferta o carpeta y, a continuación, haga clic en **[!UICONTROL Drop]** icono. Por ejemplo, puede mover una o más carpetas a otra carpeta para crear subcarpetas. Clic [!UICONTROL Clear Selection] para anular la selección de ofertas o carpetas seleccionadas.
* **Eliminar**: elimine la oferta o la carpeta. Consulte [Consideraciones al eliminar elementos](#delete).

## Opciones de Ofertas de imágenes

Al ver el [!UICONTROL Image Offers] , puede realizar las siguientes acciones en un elemento pasando el puntero sobre una oferta o carpeta y seleccionando el icono correspondiente.

La siguiente ilustración muestra los iconos de desplazamiento cuando se visualiza el [!UICONTROL Card View].

![Pase el ratón sobre los iconos de la pestaña Ofertas de imágenes en la vista de tarjeta](/help/main/c-experiences/c-manage-content/assets/image-offers-hover-icons.png)

La siguiente ilustración muestra los iconos de desplazamiento cuando se visualiza el [!UICONTROL List View]. Para mostrar los iconos, haga clic en un elemento de la lista.

![Pase el ratón sobre los iconos de la pestaña Ofertas de imágenes en la vista de lista](/help/main/c-experiences/c-manage-content/assets/list-view-hover.png)

* **Seleccionar**: seleccione una o varias carpetas en las que realizar las siguientes acciones:

   * Descargar
   * Copiar
   * Mover
   * Eliminar (consulte [Consideraciones al eliminar elementos](#delete).)

  Seleccione una o varias ofertas de imágenes en las que realizar las siguientes acciones:

   * Compartir
   * Descargar  
   * Ver propiedades
   * Editar  
   * Anotar
   * Mover  

* **Descargar**: Descargue la oferta de imagen para la carpeta y su contenido.
* **Ver propiedades**: vea las propiedades del elemento. Asegúrese de hacer clic en [!UICONTROL Basic] y la pestaña [!UICONTROL Advanced] para ver toda la información disponible. Haga clic en el icono con forma de lápiz en la página de propiedades para editar las propiedades y agregar más información. Puede agregar información de metadatos, estado de publicación y datos de licencias.
* **Más acciones**: mostrar opciones adicionales al entrar en [!UICONTROL Card View].
* **Editar**: edite la carpeta u oferta.
* **Anotar**: agregue una nota al recurso. Haga clic en el recurso y, a continuación, seleccione el área donde quiera realizar una anotación y escriba la nota.
* **Copiar**: copie la oferta. Copiar y luego editar la oferta permite crear fácilmente una oferta nueva similar.

## Consideraciones al eliminar elementos {#delete}

* Puede eliminar una carpeta entera que contenga cualquier número de recursos y subcarpetas. Esta función está disponible en la interfaz de usuario de Target también en la interfaz de usuario de Recursos de Adobe Experience Cloud.
* Si elimina una carpeta con un gran número de imágenes, el proceso que se ejecuta detrás de las escenas puede tardar cierto tiempo (varios minutos) antes de que la interfaz de usuario se actualice para mostrar el estado final. La cantidad de tiempo necesaria es una función del número de imágenes, no del tamaño de estas. Diez minutos para 2000 imágenes sería una buena estimación. Puede continuar con otros trabajos y comprobar el estado final después de varios minutos para verificar la eliminación.
* Las carpetas que no estén vacías en la biblioteca de ofertas de imágenes se pueden eliminar. Si no se hace referencia a todas las imágenes de la carpeta en ninguna actividad, se eliminará toda la carpeta y su contenido. Si se hace referencia a algunas imágenes dentro de la carpeta en cualquier actividad, se eliminan todas las imágenes sin referencia, pero se conservan las imágenes y carpetas que contienen esas imágenes.

## Vídeo de formación: El repositorio de contenido ![Distintivo Información general](/help/main/assets/overview.png)

Este vídeo incluye información sobre la administración de contenido. (4:56)

* Conexión entre la [biblioteca de activos de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) y la biblioteca de contenido de Target
* Ofertas HTML personalizadas
* Oferta HTML personalizada en el Compositor de experiencias visuales

>[!VIDEO](https://video.tv.adobe.com/v/17387)