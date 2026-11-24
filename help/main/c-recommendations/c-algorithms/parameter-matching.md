---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;dinámico;coincidencia de parámetros
description: Aprenda a filtrar dinámicamente en Adobe [!DNL Target] Recommendations comparando elementos (entidades) con un valor de la solicitud (API o mbox).
title: Coincidencia de parámetros
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
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
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 8%
---
# Coincidencia de parámetros {#parameter-matching}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a filtrar recomendaciones dinámicamente en [!DNL Adobe Target Recommendations] comparando elementos (entidades) con un valor de la solicitud (API o mbox).

>[!ENDSHADEBOX]

**[!UICONTROL Coincidencia de parámetros]** recomienda solo el contenido que coincida con los parámetros de página o los parámetros del visitante, como las dimensiones del dispositivo o la ubicación geográfica. Por ejemplo, solo se puede recomendar contenido que coincida con el parámetro de página &quot;sector&quot;. El proceso de creación y uso de reglas de inclusión para criterios y promociones es similar, al igual que los casos de uso y los ejemplos. Para obtener más información, vea [Usar reglas de inclusión dinámicas y estáticas](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

Otros ejemplos son:

* Los parámetros de mbox para la anchura y altura de la pantalla se pueden utilizar para dirigirse a visitantes móviles y recomendar solo dispositivos móviles y accesorios.
* Una regla de recomendaciones solo puede devolver los teléfonos móviles más vendidos que coincidan con la altura de pantalla del dispositivo móvil que el visitante utiliza para ver la página o superen dicha altura.
* Los parámetros de ubicación geográfica regional se pueden utilizar para devolver recomendaciones de herramientas durante el invierno. Se pueden recomendar sopladores de nieve y otras herramientas de reducción de nieve para visitantes en áreas donde nieva, pero no para visitantes en áreas donde no nieva.

## Ejemplos de coincidencia de parámetros

[!DNL Recommendations] puede coincidir con los valores de parámetro enviados en la llamada a [!DNL Target]. En el siguiente ejemplo, [!DNL Target] detecta que un visitante está usando un dispositivo móvil, basándose en los parámetros de altura y anchura de pantalla enviados en la llamada de [!DNL Target], y recomienda solo los elementos que son dispositivos móviles.

Consideremos la siguiente llamada de ejemplo [!DNL Target]:

![Llamada de destino](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

En la página que está viendo un visitante, se muestran los productos de dispositivos móviles.

![Productos de dispositivos móviles](/help/main/c-recommendations/c-algorithms/assets/phones.png)
