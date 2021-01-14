---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;profile attribute matching
description: Filtre dinámicamente en Adobe Target Recommendations comparando elementos (entidades) con un valor en el perfil del usuario.
title: Filtrar por coincidencia de atributos de Perfil en reglas de inclusión dinámica en Adobe Target Recommendations
feature: Recommendations
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 7%

---


# ![Coincidencia de atributos ](/help/assets/premium.png) PREMIUMProfile

Filtre dinámicamente en [!DNL Adobe Target] [!DNL Recommendations] comparando elementos (entidades) con un valor en el perfil del usuario.

Utilice [!UICONTROL Coincidencia de atributos de Perfil] cuando desee mostrar recomendaciones que coincidan con un valor almacenado en el perfil del visitante, como tamaño o marca favorita.

>[!NOTE]
>
>El proceso [para crear y utilizar reglas de inclusión](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) para criterios y promociones es similar, al igual que los casos de uso y los ejemplos.

Los escenarios siguientes muestran cómo puede utilizar [!UICONTROL Coincidencia de atributos de Perfil]:

* Una compañía que vende anteojos almacena el color de marco favorito de un visitante como &quot;nuez&quot;. Para ese visitante específico, las recomendaciones se configuran para devolver solo marcos de lentes que coincidan con &quot;nogal&quot; en color.
* Se puede definir un parámetro de perfil para el tamaño de la ropa (por ejemplo, Pequeño, Medio o Grande) de un visitante a medida que navegue por el sitio web de la compañía. Se puede configurar una recomendación para que coincida con ese parámetro de perfil y devuelva productos específicos solo al tamaño de ropa preferido por el usuario.

## Ejemplos de coincidencia de atributos de perfil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL La ] coincidencia de atributos de perfil permite recomendar solo los elementos que coinciden con un atributo del perfil del visitante, como en los ejemplos siguientes.

### Recomendar artículos de la marca favorita del usuario

Por ejemplo, puede utilizar la opción [!UICONTROL Coincidencia de atributos de Perfil] para crear una regla que recomiende elementos sólo donde la marca sea igual al valor o al texto almacenado en `profile.favoritebrand`. Con una regla así, si un visitante está buscando pantalones de deporte cortos de una marca particular, solo se mostrarán las recomendaciones que coincidan con la marca favorita del usuario (el valor almacenado en `profile.favoritebrand` en el perfil del visitante).

![Marca favorita](/help/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Confrontación de trabajos con solicitantes de empleo

Supongamos que está tratando de relacionar los empleos con los buscadores de empleo. Solo desea recomendar los trabajos que se encuentran en la misma ciudad que el buscador de trabajo.

Puede utilizar reglas de inclusión para comparar la ubicación de un buscador de trabajo desde el perfil de su visitante con una lista de trabajos, como en el siguiente ejemplo:

![Ciudad del usuario](/help/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Recomendar artículos según el tamaño

Para ver un ejemplo visual de cómo la coincidencia de atributos de perfil afecta a las recomendaciones, considere un sitio web que vende ventiladores eléctricos.

Cuando un visitante hace clic en varias imágenes de seguidores en este sitio web, cada página establece el valor del parámetro `entity.size` en función de si el tamaño del ventilador en la imagen es pequeño o grande.

Supongamos que ha creado una secuencia de comandos de perfil para rastrear y contar el número de veces que el valor de `entity.size` se establece en pequeño vs. grande.

Si el visitante regresa a la Página de inicio, verá las recomendaciones filtradas en función de si se hizo clic en más seguidores pequeños o grandes.

Recommendations se basa en ver más seguidores pequeños en el sitio web:

![recomendaciones de seguidores pequeños](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations basado en la visualización de más ventiladores grandes en el sitio web:

![recomendaciones de seguidores grandes](/help/c-recommendations/c-algorithms/assets/large-fans.png)