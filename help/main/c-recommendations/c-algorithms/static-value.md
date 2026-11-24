---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;estático;filtro estático
description: Aprenda a escribir manualmente uno o más valores estáticos para filtrar mediante reglas de inclusión en Adobe [!DNL Target] Recommendations.
title: Filtro estático
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
TQID: 'https://experienceleague.adobe.com/-HTJO4YFi0-isyA-5LbVUaEPu7YX1WFgPy-OexMSXFY'
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
source-wordcount: '184'
ht-degree: 2%
---
# Filtro estático {#static-filter}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a filtrar recomendaciones introduciendo manualmente uno o más valores estáticos en reglas de inclusión en [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

**[!UICONTROL Filtro estático]** limita los elementos de una recomendación a los elementos que coinciden con los valores estáticos especificados manualmente. Se puede crear cualquier cantidad de reglas de inclusión. Las reglas de inclusión se unen con un operador AND, por lo que todas las reglas deben cumplirse para que un elemento se incluya en una recomendación. Para obtener información general acerca de las reglas de inclusión, vea [Usar reglas de inclusión dinámicas y estáticas](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Recomendar contenido con clasificación G o PG

Para recomendar únicamente contenido con una clasificación de asociación de imágenes en movimiento (MPA) de &quot;G&quot; o &quot;PG&quot; (excluyendo contenido &quot;R&quot; y &quot;NC17&quot;), cree una regla de filtrado con el operador &quot;la clasificación de película es igual a cualquiera de&quot; e introduzca los valores &quot;clasificación g&quot; y &quot;clasificación pg&quot;.
