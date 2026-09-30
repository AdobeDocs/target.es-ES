---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;dinámico;coincidencia de parámetros
description: Aprenda a filtrar dinámicamente en Adobe [!DNL Target] Recommendations comparando elementos (entidades) con un valor de la solicitud (API o mbox).
title: ¿Cómo filtro por coincidencia de parámetros en las actividades de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
TQID: 'https://experienceleague.adobe.com/GTli-O1p4Gm2Fg9J-L0ukQ8dSw2t-da8OatFLP8Ks9g'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 10%
---
# [!UICONTROL Coincidencia de parámetros]

Filtre dinámicamente comparando elementos (entidades) con un valor de la solicitud (API o mbox).

Por ejemplo, recomendar solo contenido que coincida con el parámetro de página &quot;sector&quot; u otros parámetros, como dimensiones de dispositivo o ubicación geográfica, como en los siguientes ejemplos.

* Los parámetros de mbox para la anchura y altura de la pantalla se pueden utilizar para dirigirse a visitantes móviles y recomendar solo dispositivos móviles y accesorios.
* Cree una regla de recomendaciones que devuelva únicamente los teléfonos móviles más vendidos que coincidan o superen la altura de pantalla del dispositivo móvil que el visitante está utilizando para ver la página.
* Los parámetros de ubicación geográfica regional se pueden utilizar para devolver recomendaciones de herramientas durante el invierno. Los sopladores de nieve y otras herramientas de reducción de nieve pueden recomendarse para visitantes en áreas donde nieva, pero no para visitantes en áreas donde no nieva.

>[!NOTE]
>
>Si la actividad se creó antes del 31 de octubre de 2016, el envío falla si utiliza el filtro &quot;Coincidencia de parámetros&quot;. Para evitar este problema:
>
>* Cree una nueva actividad y añádale sus criterios.
>* Use criterios que no contengan el filtro “Coincidencia de parámetros”.
>* Elimine el filtro “Coincidencia de parámetros” de sus criterios.

## Ejemplos de coincidencia de parámetros

[!UICONTROL Coincidencia de parámetros] le permite recomendar contenido que coincida con los parámetros de página o los parámetros del visitante, como dimensiones de dispositivo o ubicación geográfica, como en el siguiente ejemplo:

[!DNL Recommendations] puede coincidir con los valores de parámetro enviados en la llamada a [!DNL Target]. En este caso, [!DNL Target] detecta que un visitante está usando un dispositivo móvil, basándose en los parámetros de altura y anchura de pantalla enviados en la llamada de [!DNL Target], y recomienda solo los elementos que sean dispositivos móviles.

Consideremos el siguiente ejemplo de llamada de Target:

![Llamada de destino](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

En la página que está viendo un visitante, verá productos de dispositivos móviles.

![Productos de dispositivos móviles](/help/main/c-recommendations/c-algorithms/assets/phones.png)
