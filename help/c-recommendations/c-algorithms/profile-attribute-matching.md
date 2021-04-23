---
keywords: reglas de inclusión;criterios de inclusión;recomendaciones;promoción;promociones;filtrado dinámico;dinámico;coincidencia de atributos de perfil
description: Aprenda a filtrar dinámicamente en Adobe [!DNL Target] Recommendations comparando elementos (entidades) con un valor del perfil del usuario.
title: ¿Cómo Filtro Por Coincidencia De Atributos De Perfil En Las Actividades De Recommendations?
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 7%

---

# ![](/help/assets/premium.png) PREMIUMProfile Attribute Match

Filtre dinámicamente en [!DNL Adobe Target] [!DNL Recommendations] comparando elementos (entidades) con un valor del perfil del usuario.

Utilice [!UICONTROL Coincidencia de atributos de perfil] cuando quiera mostrar recomendaciones que coincidan con un valor almacenado en el perfil del visitante, como tamaño o marca favorita.

>[!NOTE]
>
>El proceso [para crear y usar reglas de inclusión](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) para criterios y promociones es similar, al igual que los casos de uso y los ejemplos.

Los siguientes escenarios muestran cómo se puede usar [!UICONTROL Coincidencia de atributos de perfil]:

* Una empresa que vende lentes de ojos almacena el color de marco favorito de un visitante como &quot;nogal&quot;. Para ese visitante específico, las recomendaciones se configuran para que solo devuelvan marcos de lentes de ojos que coincidan con &quot;nogal&quot; en color.
* Se puede definir un parámetro de perfil para el tamaño de la ropa (p. ej., Pequeño, Medio o Grande) de un visitante a medida que navega por el sitio web de su empresa. Se puede configurar una recomendación para que coincida con ese parámetro de perfil y devuelva productos específicos del tamaño de ropa preferido del usuario.

## Ejemplos de coincidencia de atributos de perfil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL La ] coincidencia de atributos de perfil le permite recomendar solo los elementos que coinciden con un atributo del perfil del visitante, como en los ejemplos siguientes.

### Recomendación de artículos de la marca favorita del usuario

Por ejemplo, puede utilizar la opción [!UICONTROL Coincidencia de atributos de perfil] para crear una regla que recomiende solo elementos cuya marca sea igual al valor o texto almacenado en `profile.favoritebrand`. Con una regla así, si un visitante está buscando pantalones de deporte cortos de una marca particular, solo se mostrarán las recomendaciones que coincidan con la marca favorita del usuario (el valor almacenado en `profile.favoritebrand` en el perfil del visitante).

![Marca favorita](/help/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Asignación de trabajos a solicitantes de empleo

Supongamos que está tratando de igualar los empleos con los buscadores de empleo. Desea recomendar solo los trabajos que se encuentran en la misma ciudad que el buscador de trabajos.

Puede utilizar reglas de inclusión para hacer coincidir la ubicación de un buscador de empleo desde el perfil de su visitante con una oferta de empleo, como en el siguiente ejemplo:

![Ciudad del usuario](/help/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Recomendar artículos según el tamaño

Para ver un ejemplo visual de cómo afecta la coincidencia de atributos de perfil a las recomendaciones, considere un sitio web que vende seguidores eléctricos.

Cuando un visitante hace clic en varias imágenes de seguidores en este sitio web, cada página establece el valor del parámetro `entity.size` en función de si el tamaño del ventilador en la imagen es pequeño o grande.

Supongamos que ha creado un script de perfil para rastrear y contar el número de veces que el valor de `entity.size` se define en pequeño frente a grande.

Si el visitante regresa a la página principal, verá recomendaciones filtradas en función de si se hizo clic en más seguidores pequeños o grandes.

Recommendations basado en la visualización de seguidores más pequeños en el sitio web:

![recomendaciones de seguidores pequeños](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations basado en la visualización de seguidores más grandes en el sitio web:

![recomendaciones de fans grandes](/help/c-recommendations/c-algorithms/assets/large-fans.png)
