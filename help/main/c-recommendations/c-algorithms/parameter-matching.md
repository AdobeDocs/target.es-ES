---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;dinámico;coincidencia de parámetros
description: Aprenda a filtrar dinámicamente en Adobe [!DNL Target] Recommendations comparando elementos (entidades) con un valor de la solicitud (API o mbox).
title: ¿Cómo Filtro Por Coincidencia De Parámetros En Actividades De Recommendations?
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 10%

---

# ![PREMIUM](/help/main/assets/premium.png) Coincidencia de parámetros

Filtre dinámicamente comparando elementos (entidades) con un valor de la solicitud (API o mbox).

Por ejemplo, recomendar solo contenido que coincida con el parámetro de página &quot;sector&quot; u otros parámetros, como dimensiones del dispositivo o ubicación geográfica, como en los ejemplos siguientes.

* Los parámetros de mbox para la anchura y la altura de la pantalla se pueden usar para dirigirse a visitantes móviles y recomendar solo dispositivos móviles y accesorios.
* Cree una regla de recomendaciones que devuelva solo los teléfonos móviles más vendidos que coincidan o superen la altura de pantalla del dispositivo móvil que el visitante esté utilizando para ver la página.
* Los parámetros de geolocalización regionales se pueden utilizar para devolver recomendaciones para herramientas durante el invierno. Se pueden recomendar sopladores de nieve y otras herramientas de reducción de nieve para visitantes en áreas donde nieva pero no recomendado para visitantes en áreas donde no nieva.

>[!NOTE]
>
>Si la actividad se creó antes del 31 de octubre de 2016, el envío fallará si utiliza el filtro &quot;Coincidencia de parámetros&quot;. Para evitar este problema:
>
>* Cree una nueva actividad y añádale sus criterios.
>* Use criterios que no contengan el filtro “Coincidencia de parámetros”.
>* Elimine el filtro &quot;Coincidencia de parámetros&quot; de sus criterios.


## Ejemplos de coincidencia de parámetros

[!UICONTROL Coincidencia de parámetros] le permite recomendar contenido que coincida con los parámetros de la página o los parámetros del visitante, como dimensiones del dispositivo o ubicación geográfica, como en el siguiente ejemplo:

[!DNL Recommendations] puede coincidir con los valores de parámetro enviados en la variable [!DNL Target] llamada a . En este caso, [!DNL Target] detecta que un visitante está usando un dispositivo móvil, según los parámetros de altura y anchura de la pantalla enviados en la variable [!DNL Target] y solo recomendará elementos que sean dispositivos móviles.

Consideremos el siguiente ejemplo de llamada de Target:

![Llamada de Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

En la página que está viendo un visitante, verá los productos de dispositivos móviles.

![Productos para dispositivos móviles](/help/main/c-recommendations/c-algorithms/assets/phones.png)
