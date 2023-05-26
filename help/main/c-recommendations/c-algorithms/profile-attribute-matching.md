---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;dinámico;coincidencia de atributos de perfil
description: Aprenda a filtrar dinámicamente en el Adobe [!DNL Target] Recommendations comparando elementos (entidades) con un valor del perfil del usuario.
title: ¿Cómo filtro por coincidencia de atributos de perfil en las actividades de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 7%

---

# Coincidencia de atributos de perfil

Filtrado dinámico en [!DNL Adobe Target] [!DNL Recommendations] comparando elementos (entidades) con un valor del perfil del usuario.

Uso [!UICONTROL Coincidencia de atributos de perfil] si desea mostrar recomendaciones que coincidan con un valor almacenado en el perfil del visitante, como tamaño o marca favorita.

>[!NOTE]
>
>El [proceso para crear y utilizar reglas de inclusión](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) para criterios y promociones es similar, al igual que los casos de uso y ejemplos.

Los siguientes escenarios muestran cómo se puede utilizar [!UICONTROL Coincidencia de atributos de perfil]:

* Una empresa que vende gafas almacena el color de marco favorito de un visitante como &quot;nogal&quot;. Para ese visitante específico, las recomendaciones están configuradas para devolver solo marcos de gafas que coincidan con &quot;nogal&quot; en color.
* Se puede definir un parámetro de perfil para el tamaño de la ropa (por ejemplo, pequeña, mediana o grande) de un visitante que navega por el sitio web de la compañía. Se puede configurar una recomendación para que coincida con ese parámetro de perfil y devuelva productos específicos solo del tamaño de ropa preferido del usuario.

## Ejemplos de coincidencia de atributos de perfil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL Coincidencia de atributos de perfil] permite recomendar únicamente los elementos que coinciden con un atributo del perfil del visitante, como en los ejemplos siguientes.

### Recomendar artículos de la marca favorita del usuario

Por ejemplo, puede utilizar la variable [!UICONTROL Coincidencia de atributos de perfil] para crear una regla que recomiende solo elementos cuya marca sea igual al valor o texto almacenado en `profile.favoritebrand`. Con una regla así, si un visitante está buscando pantalones de deporte cortos de una marca particular, solo se mostrarán las recomendaciones que coincidan con la marca favorita del usuario (el valor almacenado en `profile.favoritebrand` en el perfil del visitante).

![Marca favorita](/help/main/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Empleos coincidentes con buscadores de empleo

Supongamos que está tratando de hacer coincidir los trabajos con los buscadores de empleo. Desea recomendar solo trabajos que se encuentren en la misma ciudad que el buscador de empleo.

Puede utilizar reglas de inclusión para hacer coincidir la ubicación de un solicitante de empleo desde su perfil de visitante a una oferta de empleo, como en el siguiente ejemplo:

![Ciudad del usuario](/help/main/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Recomendación de artículos en función del tamaño

Para ver un ejemplo visual de cómo la coincidencia de atributos de perfil afecta a las recomendaciones, consulte un sitio web que vende ventiladores eléctricos.

Cuando un visitante hace clic en varias imágenes de seguidores en este sitio web, cada página establece el valor del `entity.size` parámetro basado en si el tamaño del ventilador de la imagen es pequeño o grande.

Supongamos que ha creado un script de perfil para realizar un seguimiento y contar el número de veces que se ha recuperado el valor de `entity.size` se establece en pequeño frente a grande.

Si el visitante vuelve a la página principal, verá recomendaciones filtradas basadas en si se hizo clic en seguidores más pequeños o más grandes.

Recommendations basado en la visualización de seguidores más pequeños en el sitio web:

![recomendaciones para fans pequeños](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations basado en la visualización de seguidores más grandes en el sitio web:

![recomendaciones para fans grandes](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
