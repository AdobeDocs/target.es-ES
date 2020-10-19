---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;profile attribute matching
description: Filtre dinámicamente en Adobe Target Recommendations comparando elementos (entidades) con un valor en el perfil del usuario.
title: Filtrar por coincidencia de atributos de Perfil en reglas de inclusión dinámica en Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: c814215476ef6e40f4f175fe3f9dbb2c26b966eb
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 5%

---


# ![Coincidencia de atributos de Perfil PREMIUM](/help/assets/premium.png)

Filtre dinámicamente en [!DNL Adobe Target][!DNL Recommendations] comparando elementos (entidades) con un valor en el perfil del usuario.

Utilice Coincidencia [!UICONTROL de atributos de] Perfil cuando desee mostrar recomendaciones que coincidan con un valor almacenado en el perfil del visitante, como tamaño o marca favorita.

>[!NOTE]
>
>The [process for creating and using inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) for criteria and promotions is similar, as are the use cases and examples.

Los escenarios siguientes muestran cómo se puede utilizar la coincidencia de atributos de [!UICONTROL Perfil]:

* Una compañía que vende anteojos almacena el color de marco favorito de un visitante como &quot;nuez&quot;. Para ese visitante específico, las recomendaciones se configuran para devolver solo marcos de lentes que coincidan con &quot;nogal&quot; en color.
* Se puede definir un parámetro de perfil para el tamaño de la ropa (por ejemplo, Pequeño, Medio o Grande) de un visitante a medida que navegue por el sitio web de la compañía. Se puede configurar una recomendación para que coincida con ese parámetro de perfil y devuelva productos específicos solo al tamaño de ropa preferido por el usuario.

## Ejemplos de coincidencia de atributos de perfil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL La coincidencia] de atributos de perfil permite recomendar solo los elementos que coinciden con un atributo del perfil del visitante, como en los ejemplos siguientes.

### Recomendar artículos de la marca favorita del usuario

For example, you can use the [!UICONTROL Profile Attribute Matching] option to create a rule that recommends items only where the brand equals the value or text stored in `profile.favoritebrand`. Con una regla así, si un visitante está buscando pantalones de deporte cortos de una marca particular, solo se mostrarán las recomendaciones que coincidan con la marca favorita del usuario (el valor almacenado en `profile.favoritebrand` en el perfil del visitante).

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Confrontación de trabajos con solicitantes de empleo

Supongamos que está tratando de relacionar los empleos con los buscadores de empleo. Solo desea recomendar los trabajos que se encuentran en la misma ciudad que el buscador de trabajo.

Puede utilizar reglas de inclusión para comparar la ubicación de un buscador de trabajo desde el perfil de su visitante con una lista de trabajos, como en el siguiente ejemplo:

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Recomendar ropa que coincida con el tamaño de un visitante

Veamos un ejemplo para recomendar ropa que coincida con el tamaño de ropa establecido en el perfil del visitante.

La página del producto envía `entity.size` la llamada de mbox (flecha roja en la siguiente ilustración).

Puede crear una secuencia de comandos [de](/help/c-target/c-visitor-profile/profile-parameters.md) perfil para capturar los atributos y valores de perfil del visitante de la última página visitada por el visitante.

Por ejemplo,

```
if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'small')) { return 'small';
}

else if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'medium')) { return 'medium';
}

else if ((mbox.name=="target-global-mbox") &&(mbox.param('entity.size') == 'large')) { return 'large';
}
```

La secuencia de comandos de perfil captura el `entity.size` valor del mbox denominado `target-global-mbox` y lo devuelve como un atributo de perfil denominado `user.size` (flecha azul en la siguiente ilustración).

![cambiar tamaño de llamada de mbox](/help/c-recommendations/c-algorithms/assets/size.png)

Al crear los criterios de recomendación, haga clic en **[!UICONTROL Añadir regla]** de filtrado y, a continuación, seleccione Coincidencia **[!UICONTROL de atributos de]** Perfil.

![Ilustración de coincidencia de atributos de perfil](/help/c-recommendations/c-algorithms/assets/profile-attribute-matching.png)

Si el `user.size` perfil se ha cargado en [!DNL Target], se muestra en la lista desplegable para que coincida al configurar la regla para que coincida con el valor pasado en la llamada de mbox (`size`) al nombre de la secuencia de comandos de perfil (`user.size`).

A continuación, puede seleccionar &quot;size&quot; &quot;es igual a&quot; el valor/texto almacenado en &quot;user.size&quot; para la coincidencia de atributos de perfil.

![Ejemplo de tamaño](/help/c-recommendations/c-algorithms/assets/example-size.png)

Una vez creadas las reglas de atributos de perfil, se filtrarán todas las recomendaciones que tengan atributos que no coincidan con el atributo de perfil almacenado del visitante.

### Recomendar artículos según el tamaño

Para ver un ejemplo visual de cómo la coincidencia de atributos de perfil afecta a las recomendaciones, considere un sitio web que vende ventiladores eléctricos.

Cuando un visitante hace clic en varias imágenes de seguidores en este sitio web, cada página establece el valor del `entity.size` parámetro en función de si el tamaño del ventilador de la imagen es pequeño o grande.

Supongamos que ha creado una secuencia de comandos de perfil para rastrear y contar el número de veces que el valor de `entity.size` se establece en pequeño vs. grande.

Si el visitante regresa a la Página de inicio, verá las recomendaciones filtradas en función de si se hizo clic en más seguidores pequeños o grandes.

Recommendations se basa en ver más seguidores pequeños en el sitio web:

![recomendaciones de seguidores pequeños](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations basado en la visualización de más ventiladores grandes en el sitio web:

![recomendaciones de seguidores grandes](/help/c-recommendations/c-algorithms/assets/large-fans.png)