---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;dinámico;coincidencia de atributos de perfil
description: Aprenda a filtrar dinámicamente en  [!DNL Target Recommendations] comparando elementos (entidades) con un valor del perfil del usuario.
title: ¿Cómo filtro por coincidencia de atributos de perfil en las actividades de Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# Coincidencia de atributos de perfil

Filtre dinámicamente en [!DNL Adobe Target Recommendations] comparando elementos (entidades) con un valor del perfil del usuario.

Use [!UICONTROL Profile Attribute Matching] cuando quiera mostrar recomendaciones que coincidan con un valor almacenado en el perfil del visitante, como tamaño o marca favorita.

>[!NOTE]
>
>El [proceso para crear y usar reglas de inclusión](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) para criterios y promociones es similar, al igual que los ejemplos y casos de uso.

Los siguientes escenarios muestran cómo se puede usar [!UICONTROL Profile Attribute Matching]:

* Una empresa que vende gafas almacena el color de marco favorito de un visitante como &quot;nogal&quot;. Para ese visitante específico, las recomendaciones están configuradas para devolver solo marcos de gafas que coincidan con &quot;nogal&quot; en color.
* Se puede definir un parámetro de perfil para el tamaño de la ropa (por ejemplo, pequeña, Medium o grande) de un visitante que navega por el sitio web de la empresa. Se puede configurar una recomendación para que coincida con ese parámetro de perfil y devuelva productos específicos solo del tamaño de ropa preferido del usuario.

## Ejemplos de coincidencia de atributos de perfil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL Profile Attribute Matching] le permite recomendar únicamente los elementos que coincidan con un atributo del perfil del visitante, como en los ejemplos siguientes.

### Recomendar artículos de la marca favorita del usuario

Por ejemplo, puede usar la opción [!UICONTROL Profile Attribute Matching] para crear una regla que recomiende sólo elementos cuya marca sea igual al valor o al texto almacenado en `profile.favoritebrand`. Con una regla así, si un visitante está buscando pantalones de deporte cortos de una marca en particular, solo se mostrarán las recomendaciones que coincidan con la marca favorita del usuario (el valor almacenado en `profile.favoritebrand` en el perfil del visitante).

![Marca favorita](/help/main/c-recommendations/c-algorithms/assets/favorite-brand-new.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Empleos coincidentes con buscadores de empleo

Supongamos que está tratando de hacer coincidir los trabajos con los buscadores de empleo. Desea recomendar solo trabajos que se encuentren en la misma ciudad que el buscador de empleo.

Puede utilizar reglas de inclusión para hacer coincidir la ubicación de un buscador de empleo desde el perfil del visitante a una lista de trabajos, como en el siguiente ejemplo:

![Ciudad del usuario](/help/main/c-recommendations/c-algorithms/assets/city-new.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Recomendación de artículos en función del tamaño

Para ver un ejemplo visual de cómo la coincidencia de atributos de perfil afecta a las recomendaciones, consulte un sitio web que vende ventiladores eléctricos.

Cuando un visitante hace clic en varias imágenes de seguidores en este sitio web, cada página establece el valor del parámetro `entity.size` en función de si el tamaño del seguidor en la imagen es pequeño o grande.

Supongamos que ha creado un script de perfil para realizar el seguimiento y contar la cantidad de veces que el valor de `entity.size` se ha establecido en pequeño frente a grande.

Si el visitante vuelve a la página principal, verá recomendaciones filtradas basadas en si se hizo clic en seguidores más pequeños o más grandes.

Recommendations basado en la visualización de seguidores más pequeños en el sitio web:

![recomendaciones para pequeños fans](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations basado en la visualización de seguidores más grandes en el sitio web:

![recomendaciones para fans grandes](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
