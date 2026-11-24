---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;dinámico;coincidencia de atributos de entidad
description: Aprenda a filtrar dinámicamente en [!DNL Target Recommendations] comparando un grupo de elementos potenciales con un elemento específico con el que el usuario ha interactuado.
title: Coincidencia de atributos de entidad
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
TQID: 'https://experienceleague.adobe.com/2cBSfWXS96u7iumehPd7enxPjQcebkQCdSBSHWOUcJg'
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
source-wordcount: '505'
ht-degree: 5%
---
# Coincidencia de atributos de entidad {#entity-attribute-matching}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a filtrar recomendaciones dinámicamente en [!DNL Adobe Target Recommendations] comparando un grupo de posibles elementos recomendados con un elemento específico con el que el visitante ha interactuado.

>[!ENDSHADEBOX]

**[!UICONTROL Coincidencia de atributos de entidad]** solo recomienda los elementos que coincidan con un atributo de un elemento con el que el visitante haya interactuado. El proceso de creación y uso de reglas de inclusión para criterios y promociones es similar, al igual que los casos de uso y los ejemplos. Para obtener más información, vea [Usar reglas de inclusión dinámicas y estáticas](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Ejemplos de coincidencia de atributos de entidad

**[!UICONTROL Coincidencia de atributos de entidad]** solo puede recomendar los elementos que coincidan, por ejemplo:

* Atributo del elemento que el visitante está viendo en este momento
* El artículo que vio más recientemente el visitante
* El artículo que compró el visitante más recientemente
* El artículo que el visitante vio con mayor frecuencia
* Un elemento almacenado en un atributo personalizado en el perfil del visitante

### Recomendación de artículos según la marca

Una vez creadas las reglas de atributos de entidad, filtran todas las recomendaciones con atributos que no coinciden con el valor de entidad pasado a la página. El valor `entity.brand` debe entregarse en el mbox de las páginas para que este proceso funcione.

Con este tipo de regla de inclusión dinámica, solo se debe especificar una regla de recomendación para devolver resultados de marca relevantes en todas las páginas de marca, en lugar de una colección o un filtro estático para cada nombre de marca.

Por ejemplo, cuando se muestra una página que incluye un producto de la marca A, la página establece el valor del parámetro `entity.brand` en &quot;MarcaA&quot;. En una página de aterrizaje de marca, el mbox devuelve `entity.brand=brandA`.

![Ejemplo de llamada de Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

Las recomendaciones de la página contienen únicamente productos de la marca A.

![Recomendaciones de marca A](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

Cuando se muestra una página de producto de la Marca B, el valor `entity.brand` se restablece a &quot;Marca B&quot; y solo se recomiendan los productos de la Marca B. Del mismo modo, en la página de aterrizaje de la marca B, solo se devuelven los productos de la marca B.

![Recomendaciones de marca B](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### Ampliación de ventas a un producto más caro

Para animar a los visitantes a considerar artículos de mayor precio y, por lo tanto, más rentables, los operadores &quot;es igual que&quot; y &quot;está entre&quot; pueden promocionar artículos más caros de la misma categoría y de la misma marca. Por ejemplo, un retailer de zapatos puede promocionar zapatillas de running más caras para mejorar la venta de un visitante que esté mirando zapatillas de running, como en el siguiente ejemplo:

![Ampliación de ventas](/help/main/c-recommendations/c-algorithms/assets/upsell-new.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And 
Entity Attribute Matching
brand - equals - current item's - brand 
And 
Entity Attribute Matching
value - is between - 100% and 1000% of - current item's - value
```

### Promoción de productos de marca privada

Los filtros dinámicos y estáticos se pueden mezclar para promocionar productos de marca privada. Por ejemplo, una empresa de suministros de oficina puede promocionar cartuchos de tóner de la marca de la empresa para impulsar una venta más rentable para un visitante que esté viendo el tóner, y plumas de la marca de la empresa para un visitante que esté mirando plumas, como en el siguiente ejemplo:

![Marca de la casa](/help/main/c-recommendations/c-algorithms/assets/housebrand-new.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
