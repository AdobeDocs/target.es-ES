---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;dinámico;coincidencia de atributos de perfil
description: Aprenda a filtrar dinámicamente en [!DNL Target Recommendations] comparando elementos (entidades) con un valor del perfil del usuario.
title: Coincidencia de atributos de perfil
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
TQID: 'https://experienceleague.adobe.com/Gm91Mww5ylvNjUcmzp6KwxIG6LTibvI44LnW67KFzqk'
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
source-wordcount: '503'
ht-degree: 5%
---
# Coincidencia de atributos de perfil {#profile-attribute-matching}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a filtrar recomendaciones dinámicamente en [!DNL Adobe Target Recommendations] comparando elementos (entidades) con un valor del perfil del visitante.

>[!ENDSHADEBOX]

Use **[!UICONTROL Coincidencia de atributos de perfil]** para mostrar recomendaciones que coincidan con un valor almacenado en el perfil del visitante, como tamaño o marca favorita. El proceso de creación y uso de reglas de inclusión para criterios y promociones es similar, al igual que los casos de uso y los ejemplos. Para obtener más información, vea [Usar reglas de inclusión dinámicas y estáticas](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

Los siguientes escenarios muestran cómo se puede usar **[!UICONTROL Coincidencia de atributos de perfil]**:

* Una empresa que vende gafas almacena el color de marco favorito de un visitante como &quot;nogal&quot;. Para ese visitante, las recomendaciones están configuradas para devolver solo marcos de gafas que coincidan con &quot;nogal&quot; en color.
* Se puede definir un parámetro de perfil para el tamaño de la ropa (por ejemplo, pequeña, Medium o grande) de un visitante a medida que este navega por el sitio web de la compañía. Se puede configurar una recomendación para que coincida con ese parámetro de perfil y devuelva solo los productos con la talla de ropa preferida del visitante.

## Ejemplos de coincidencia de atributos de perfil

**[!UICONTROL Coincidencia de atributos de perfil]** solo recomienda los elementos que coincidan con un atributo del perfil del visitante, como en los ejemplos siguientes.

### Recomendar artículos de la marca favorita del usuario

La opción **[!UICONTROL Coincidencia de atributos de perfil]** puede crear una regla que recomiende solo elementos cuya marca sea igual al valor o texto almacenado en `profile.favoritebrand`. Con una regla así, si un visitante está buscando pantalones de deporte cortos de una marca en particular, solo se mostrarán las recomendaciones que coincidan con la marca favorita de ese visitante (el valor almacenado en `profile.favoritebrand` en el perfil del visitante).

![Marca favorita](/help/main/c-recommendations/c-algorithms/assets/favorite-brand-new.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Empleos coincidentes con buscadores de empleo

Para relacionar los trabajos con los buscadores de empleo, solo se recomiendan los trabajos que están en la misma ciudad que el buscador de empleo. Las reglas de inclusión pueden coincidir con la ubicación de un buscador de trabajos desde el perfil del visitante a una lista de trabajos, como en el siguiente ejemplo:

![Ciudad del usuario](/help/main/c-recommendations/c-algorithms/assets/city-new.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Recomendación de artículos en función del tamaño

El siguiente ejemplo muestra cómo la coincidencia de atributos de perfil afecta a las recomendaciones de un sitio web que vende ventiladores eléctricos.

Cuando un visitante hace clic en varias imágenes de seguidores en este sitio web, cada página establece el valor del parámetro `entity.size` en función de si el tamaño del seguidor en la imagen es pequeño o grande. Un script de perfil realiza un seguimiento y cuenta el número de veces que el valor de `entity.size` se establece en pequeño en comparación con el grande.

Si el visitante vuelve a la página principal, se muestran recomendaciones filtradas basadas en si se hizo clic en seguidores más pequeños o más grandes.

Recomendaciones basadas en la visualización de seguidores más pequeños en el sitio web:

![recomendaciones para pequeños fans](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recomendaciones basadas en la visualización de seguidores más grandes en el sitio web:

![recomendaciones para fans grandes](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
