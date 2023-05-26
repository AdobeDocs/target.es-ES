---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;dinámico;coincidencia de parámetros
description: Aprenda a filtrar dinámicamente en el Adobe [!DNL Target] Recommendations comparando elementos (entidades) con un valor de la solicitud (API o mbox).
title: ¿Cómo filtro por coincidencia de parámetros en las actividades de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 10%

---

# Coincidencia de parámetros

Filtre dinámicamente comparando elementos (entidades) con un valor de la solicitud (API o mbox).

Por ejemplo, recomendar solo contenido que coincida con el parámetro de página &quot;sector&quot; u otros parámetros, como dimensiones de dispositivo o ubicación geográfica, como en los siguientes ejemplos.

* Los parámetros de mbox para la anchura y altura de la pantalla se pueden utilizar para dirigirse a visitantes móviles y recomendar solo dispositivos móviles y accesorios.
* Cree una regla de recomendaciones que devuelva únicamente los teléfonos móviles más vendidos que coincidan o superen la altura de pantalla del dispositivo móvil que el visitante está utilizando para ver la página.
* Los parámetros de ubicación geográfica regional se pueden utilizar para devolver recomendaciones de herramientas durante el invierno. Los sopladores de nieve y otras herramientas de reducción de nieve pueden recomendarse para visitantes en áreas donde nieva, pero no para visitantes en áreas donde no nieva.

>[!NOTE]
>
>Si la actividad se creó antes del 31 de octubre de 2016, el envío fallará si utiliza el filtro Coincidencia de parámetros. Para evitar este problema:
>
>* Cree una nueva actividad y añádale sus criterios.
>* Use criterios que no contengan el filtro “Coincidencia de parámetros”.
>* Elimine el filtro &quot;Coincidencia de parámetros&quot; de sus criterios.


## Ejemplos de coincidencia de parámetros

[!UICONTROL Coincidencia de parámetros] le permite recomendar contenido que coincida con los parámetros de página o los parámetros del visitante, como dimensiones del dispositivo o ubicación geográfica, como en el siguiente ejemplo:

[!DNL Recommendations] puede coincidir con los valores de parámetro enviados en la [!DNL Target] llamada. En este caso, [!DNL Target] detecta que un visitante está utilizando un dispositivo móvil, en función de los parámetros de altura y anchura de pantalla enviados en la [!DNL Target] llama a y solo recomendará elementos que sean dispositivos móviles.

Consideremos el siguiente ejemplo de llamada de Target:

![Llamada de Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

En la página que está viendo un visitante, verá productos de dispositivos móviles.

![Productos para dispositivos móviles](/help/main/c-recommendations/c-algorithms/assets/phones.png)
