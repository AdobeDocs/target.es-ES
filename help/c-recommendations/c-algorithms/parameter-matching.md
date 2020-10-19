---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;parameter matching
description: Filtre dinámicamente en Adobe Target Recommendations comparando elementos (entidades) con un valor de la solicitud (API o mbox).
title: Filtrar por coincidencia de parámetros en reglas de inclusión dinámica en Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 27%

---


# ![Coincidencia de parámetros PREMIUM](/help/assets/premium.png)

Filtre dinámicamente comparando elementos (entidades) con un valor de la solicitud (API o mbox).

Por ejemplo, recomendar solo contenido que coincida con el parámetro de página &quot;sector&quot; u otros parámetros, como dimensiones de dispositivo o ubicación geográfica, como en los ejemplos siguientes.

* Los parámetros de mbox para la anchura y la altura de la pantalla se pueden usar para destinatario de visitantes móviles y recomendar solo dispositivos móviles y accesorios.
* Los parámetros de ubicación geográfica regional se pueden utilizar para devolver recomendaciones para herramientas durante el invierno. Los sopladores de nieve y otras herramientas de reducción de nieve pueden ser recomendados para visitantes en áreas donde nieva pero no recomendados para visitantes en áreas donde no nieva.

>[!NOTE]
>
>Si la actividad se creó antes del 31 de octubre de 2016, su envío fallará si utiliza el filtro &quot;Coincidencia de parámetros&quot;. Para evitar este problema:
>
>* Cree una nueva actividad y añádale sus criterios.
>* Use criterios que no contengan el filtro “Coincidencia de parámetros”.
>* Elimine el filtro “Coincidencia de parámetros” de sus criterios.


Operadores disponibles:

* igual a
* no es igual
* contiene
* no contiene
* comienza con
* termina con
* es mayor o igual que
* es menor o igual que
* está entre