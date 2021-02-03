---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;dinámico;coincidencia de parámetros
description: Filtre dinámicamente en Adobe Target Recommendations comparando elementos (entidades) con un valor de la solicitud (API o mbox).
title: Filtrar por coincidencia de parámetros en reglas de inclusión dinámica en Destinatario Recommendations
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 10%

---


# ![Coincidencia de ](/help/assets/premium.png) parámetro PREMIUMP

Filtre dinámicamente comparando elementos (entidades) con un valor de la solicitud (API o mbox).

Por ejemplo, recomendar solo contenido que coincida con el parámetro de página &quot;sector&quot; u otros parámetros, como dimensiones de dispositivo o ubicación geográfica, como en los ejemplos siguientes.

* Los parámetros de mbox para la anchura y la altura de la pantalla se pueden usar para destinatario de visitantes móviles y recomendar solo dispositivos móviles y accesorios.
* Cree una regla de recomendaciones que devuelva solo los teléfonos móviles más vendidos que coincidan o superen la altura de pantalla del dispositivo móvil en el que el visitante utiliza la vista de la página.
* Los parámetros de ubicación geográfica regional se pueden utilizar para devolver recomendaciones para herramientas durante el invierno. Los sopladores de nieve y otras herramientas de reducción de nieve pueden ser recomendados para visitantes en áreas donde nieva pero no recomendados para visitantes en áreas donde no nieva.

>[!NOTE]
>
>Si la actividad se creó antes del 31 de octubre de 2016, su envío fallará si utiliza el filtro &quot;Coincidencia de parámetros&quot;. Para evitar este problema:
>
>* Cree una nueva actividad y añádale sus criterios.
>* Use criterios que no contengan el filtro “Coincidencia de parámetros”.
>* Elimine el filtro &quot;Coincidencia de parámetros&quot; de sus criterios.


## Ejemplos de coincidencia de parámetros

[!UICONTROL La ] coincidencia de parámetros le permite recomendar contenido que coincida con los parámetros de página o los parámetros del visitante, como dimensiones del dispositivo o ubicación geográfica, como en el siguiente ejemplo:

[!DNL Recommendations] puede coincidir con los valores de parámetro enviados en la  [!DNL Target] llamada. En este caso, [!DNL Target] detecta que un visitante está utilizando un dispositivo móvil, en función de los parámetros de altura y ancho de la pantalla enviados en la llamada [!DNL Target], y recomienda sólo elementos que sean dispositivos móviles.

Considere el siguiente ejemplo de llamada de Destinatario:

![Llamada de destinatario](/help/c-recommendations/c-algorithms/assets/example-target-call-2.png)

En la página que está viendo un visitante, verá productos de dispositivos móviles.

![Productos de dispositivos móviles](/help/c-recommendations/c-algorithms/assets/phones.png)
