---
keywords: inclusion rules;inclusion criteria;recommendations;create new criteria;promotion;promotions;dynamic filtering;dynamic;empty values;ignore filtering rule;static filter;filter by value;entity attribute matching;profile attribute matching;parameter matching;filter by value;static filter
description: Información sobre la creación de reglas de inclusión en Adobe Target Recommendations para criterios y promociones, y la adición de reglas de filtrado dinámicas o estáticas adicionales para obtener mejores resultados.
title: Usar reglas de inclusión dinámicas y estáticas en Adobe Target Recommendations
feature: criteria
mini-toc-levels: 3
uuid: f0ee2086-1126-44a4-9379-aa897dc0e06b
translation-type: tm+mt
source-git-commit: f1df23d94ab81002945b22c6468ba1d3a9030388
workflow-type: tm+mt
source-wordcount: '2135'
ht-degree: 36%

---


# ![PREMIUM](/help/assets/premium.png) Uso de reglas de inclusión dinámicas y estáticas{#use-dynamic-and-static-inclusion-rules}

Información sobre la creación de reglas de inclusión para criterios y promociones en Adobe Target y la adición de reglas de filtrado dinámicas o estáticas adicionales para lograr mejores resultados para las recomendaciones.

El proceso de creación y uso de reglas de inclusión para criterios y promociones es similar, al igual que los casos de uso y los ejemplos. En este tema se tratan los criterios y las promociones, así como el uso de reglas de inclusión.

## Agregación de reglas de filtrado a los criterios {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Mientras [crea criterios](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE), haga clic en **[!UICONTROL Agregar regla de filtrado]** en **[!UICONTROL Reglas de inclusión]**.

![](assets/inclusion_options_new.png)

Las opciones disponibles varían en función del sector seleccionado y la clave de recomendación.

## Agregación de reglas de filtrado a las promociones   {#section_D59AFB62E2EE423086281CF5D18B1076}

Mientras [crea una promoción](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), seleccione **[!UICONTROL Promocionar por atributo]** y, a continuación, haga clic en **[!UICONTROL Agregar regla de filtrado]**.

![](assets/inclusion_options.png)

## Tipos de filtro {#section_0125F1ED10A84C0EB45325122460EBCD}

La siguiente tabla indica los tipos de opciones de filtrado para criterios y promociones:

### Filtrado dinámico

Las reglas de inclusión dinámicas son más potentes que las reglas de inclusión estáticas y ofrecen mejores resultados y participación. Tenga en cuenta lo siguiente:

* Las reglas de inclusión dinámica ofrecen recomendaciones al hacer coincidir un atributo en el parámetro de perfil de un usuario o en una llamada de mbox.

   Por ejemplo, puede crear una recomendación de criterios más populares y, a continuación, del conjunto de recomendaciones devueltas, filtrar cualquier atributo pasado cuando el usuario accede a una página en la que se muestran las recomendaciones en tiempo real.

* Utilice reglas estáticas para limitar los artículos que se incluyen en la recomendación (en lugar de las colecciones).

* Puede crear tantas reglas de inclusión dinámicas como sea necesario. Las reglas de inclusión se unen mediante un operador Y. Deben cumplirse todas las reglas para incluir un artículo en una recomendación.

Las siguientes opciones están disponibles para el filtrado dinámico:

#### Coincidencia de atributos de entidad

Filtre dinámicamente comparando un grupo de posibles elementos de recomendaciones con un elemento específico con el que los usuarios han interactuado.

Por ejemplo, recomendar solo elementos que coincidan con la marca del elemento actual como en el siguiente ejemplo:

Si el mbox de una Página de aterrizaje de marca devuelve `entity.brand=Nike`, solo se devuelven los productos Nike y se muestran en esa página. Del mismo modo, en la Página de aterrizaje de marcas de Adidas, solo se devuelven productos Adidas. Con este tipo de regla de inclusión dinámica, el usuario solo tiene que especificar una regla de recomendación que devuelva resultados de marca relevantes en todas las páginas de marca en lugar de especificar una colección o un filtro estático para que coincida con cada nombre de marca.

Operadores disponibles:

* igual a
* no es igual
* está entre
* contiene
* no contiene
* comienza con
* termina con
* el valor está presente
* el valor no está presente
* es mayor o igual que
* es menor o igual que

#### Coincidencia de atributos de perfil

Filtre dinámicamente comparando elementos (entidades) con un valor en el perfil del usuario.

Utilice Coincidencia [!UICONTROL de atributos de] Perfil cuando desee mostrar recomendaciones que coincidan con un valor almacenado en el perfil del visitante, como tamaño o marca favorita.

Los siguientes ejemplos muestran cómo se puede utilizar la coincidencia de atributos de [!UICONTROL Perfil]:

* Una compañía que vende anteojos almacena el color de marco favorito de un visitante como &quot;nuez&quot;. Para ese visitante específico, las recomendaciones se configuran para devolver solo marcos de lentes que coincidan con &quot;nogal&quot; en color.
* Se puede definir un parámetro de perfil para el tamaño de la ropa (por ejemplo, Pequeño, Medio o Grande) de un visitante a medida que navegue por el sitio web de la compañía. Se puede configurar una recomendación para que coincida con ese parámetro de perfil y devuelva productos específicos solo al tamaño de ropa preferido por el usuario.

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

Al crear los criterios de recomendación, haga clic en [!UICONTROL Añadir regla]de filtrado y, a continuación, seleccione Coincidencia [!UICONTROL de atributos de]Perfil.

![Ilustración de coincidencia de atributos de perfil](/help/c-recommendations/c-algorithms/assets/profile-attribute-matching.png)

Si el `user.size` perfil se ha cargado en [!DNL Target], se muestra en la lista desplegable para que coincida al configurar la regla para que coincida con el valor pasado en la llamada de mbox (`size`) al nombre de la secuencia de comandos de perfil (`user.size`).

A continuación, puede seleccionar &quot;size&quot; &quot;es igual a&quot; el valor/texto almacenado en &quot;user.size&quot; para la coincidencia de atributos de perfil.

Una vez creadas las reglas de atributos de perfil, se filtrarán todas las recomendaciones que tengan atributos que no coincidan con el atributo de perfil almacenado del visitante.

Para ver un ejemplo visual de cómo la coincidencia de atributos de perfil afecta a las recomendaciones, considere un sitio web que vende seguidores.

Cuando un visitante hace clic en varias imágenes de seguidores en este sitio web, cada página establece el valor del `entity.size` parámetro en función de si el tamaño del ventilador de la imagen es pequeño o grande.

Supongamos que ha creado una secuencia de comandos de perfil para rastrear y contar el número de veces que el valor de `entity.size` se establece en pequeño vs. grande.

Si el visitante regresa a la Página de inicio, verá las recomendaciones filtradas en función de si se hizo clic en más seguidores pequeños o grandes.

Recommendations se basa en ver más seguidores pequeños en el sitio web:

![recomendaciones de seguidores pequeños](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations basado en la visualización de más ventiladores grandes en el sitio web:

![recomendaciones de seguidores grandes](/help/c-recommendations/c-algorithms/assets/large-fans.png)

#### Coincidencia de parámetros

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

### Filtrar por valor

La siguiente opción está disponible para el filtrado dinámico:

#### Filtro estático

Introduzca manualmente uno o varios valores estáticos para filtrar.

Por ejemplo, recomendar solo contenido con una clasificación MPAA de “G” o “PG”.

Operadores disponibles:

* igual a
* no es igual
* contiene
* no contiene
* comienza con
* termina con
* el valor está presente
* el valor no está presente
* es mayor o igual que
* es menor o igual que

>[!NOTE]
>
>Si está familiarizado con el modo en que se configuraban las reglas de inclusión antes de la versión de Target 17.6.1 (junio de 2017), notará que algunas de las opciones y operadores han cambiado. Solo se muestran los operadores aplicables a la opción seleccionada y el nombre de algunos ha cambiado (“coincide” es ahora “es igual que”), de modo que la experiencia sea más coherente e intuitiva. Todas las reglas de inclusión creadas antes de esta versión se migran automáticamente a la nueva estructura. No es necesaria reestructuración alguna por su parte.

Puede crear tantas reglas de inclusión como necesite. Las reglas de inclusión se unen mediante un operador Y. Deben cumplirse todas las reglas para incluir un artículo en una recomendación.

## Criterios dinámicos y ejemplos de promoción

Los criterios y promociones dinámicos son mucho más potentes que los estáticos y ofrecen mejores resultados y una mayor participación.

En los ejemplos siguientes encontrará ideas para usar las promociones dinámicas en las campañas de marketing:

### Es igual a

Con el operador &quot;es igual que&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en el sitio web (como un producto, un artículo o una película), puede promocionar otros elementos desde:

* la misma marca
* la misma categoría
* la misma categoría Y la marca propia
* la misma tienda

### No es igual a

Con el operador &quot;no es igual que&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en el sitio web (como un producto, un artículo o una película), puede promocionar otros elementos de:

* una serie de televisión distinta
* un género distinto
* una serie de productos distinta
* un ID de estilo distinto

### está entre

Con el operador &quot;está entre&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en el sitio web (como un producto, un artículo o una película), puede promocionar otros elementos que:

* sean más caros
* sean menos caros
* cuesten un 30 % más o menos
* sean episodios posteriores de la misma temporada
* sean los primeros libros de una saga

## Handling empty values when filtering by Entity Attribute Matching, Profile Attribute Matching, and Parameter Matching {#section_7D30E04116DB47BEA6FF840A3424A4C8}

You can choose several options to handle empty values when filtering by [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], and [!UICONTROL Parameter Matching] for exit criteria and promotions.

Anteriormente, si un valor estaba en blanco no se devolvía ningún resultado. La lista desplegable “Si *x* está en blanco” le permite elegir la acción que se debe realizar si los criterios contienen valores en blanco, como se muestra en la siguiente ilustración:

![](assets/empty_value.png)

Para seleccionar la acción deseada, pase el ratón sobre el icono del engranaje (![](assets/icon_gear.png)) y, a continuación, elija la acción deseada:

| Acción | Disponible para | Detalles |
|--- |--- |--- |
| Ignorar esta regla de filtrado | Coincidencia de atributo de perfil<br> Parámetro de coincidencia | Esta es la acción predeterminada para la coincidencia de atributos de perfil y la coincidencia de parámetros.<br>Esta opción especifica que la regla se ignora. Por ejemplo, si hay tres reglas de filtrado y la tercera no pasa ningún valor, en vez de no devolver resultado alguno, puede simplemente ignorar la tercera regla con valores en blanco. |
| No promocionar ningún elemento | Coincidencia de atributos de entidad<br>Coincidencia de atributos de perfil<br>Coincidencia de parámetros | Esta es la acción predeterminada para la coincidencia de atributos de entidad.<br>[!DNL Target]Esta acción es el modo en que gestiona los valores en blanco antes de la agregación de esta opción: no se mostrarán más resultados para este criterio. |
| Uso de un valor estático | Coincidencia de atributos de entidad<br>Coincidencia de atributo de perfil<br> Parámetro de coincidencia | Si un valor está en blanco, puede optar por usar un valor estático. |

## Ejemplos de coincidencia de atributos de perfil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL La coincidencia] de atributos de perfil permite recomendar solo los elementos que coinciden con un atributo del perfil del visitante, como en los ejemplos siguientes.

### Ejemplo 1: Recomendar artículos de la marca favorita del usuario

For example, you can use the [!UICONTROL Profile Attribute Matching] option to create a rule that recommends items only where the brand equals the value or text stored in `profile.favoritebrand`. Con una regla así, si un visitante está buscando pantalones de deporte cortos de una marca particular, solo se mostrarán las recomendaciones que coincidan con la marca favorita del usuario (el valor almacenado en `profile.favoritebrand` en el perfil del visitante).

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Ejemplo 2: Confrontación de trabajos con solicitantes de empleo

Supongamos que está tratando de relacionar los empleos con los buscadores de empleo. Solo desea recomendar los trabajos que se encuentran en la misma ciudad que el buscador de trabajo.

Puede utilizar reglas de inclusión para comparar la ubicación de un buscador de trabajo desde el perfil de su visitante con una lista de trabajos, como en el siguiente ejemplo:

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

## Ejemplos de coincidencia de atributos de entidad

[!UICONTROL La coincidencia] de atributos de entidad permite recomendar únicamente los elementos que coinciden con un atributo del artículo que el usuario está viendo actualmente, el artículo que el usuario ha visto más recientemente, el artículo que el usuario compró más recientemente, el artículo que el usuario ha visto con más frecuencia o un artículo almacenado en un atributo personalizado en el perfil del visitante, como en los ejemplos siguientes.

### Ejemplo 3: La venta al por mayor a un producto más caro

Supongamos que usted es un comerciante de ropa y desea animar a los usuarios a considerar artículos de mayor precio y, por lo tanto, más rentables. Puede utilizar los operadores &quot;es igual que&quot; y &quot;está entre&quot; para promocionar artículos más caros que procedan de la misma categoría y de la misma marca. Por ejemplo, un vendedor de zapatos puede promocionar zapatos deportivos más caros en un esfuerzo por vender un visitante mirando zapatillas de correr.

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

### Ejemplo 4: Promoción de productos con etiquetas privadas

Puede combinar filtros dinámicos y estáticos para promocionar productos de etiquetas privadas. Por ejemplo, una compañía de suministro de oficina puede promocionar cartuchos de tóner de la marca propia de la compañía para llevar a cabo una venta más rentable de un visitante mirando el tóner, y promocionar plumas de la marca propia de la compañía para llevar a cabo una venta más rentable de plumas para un visitante mirando las plumas.

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

## Advertencias {#section_A889FAF794B7458CA074DEE06DD0E345}

>[!IMPORTANT]
>
>Es posible que no se puedan usar atributos de tipo de datos diferentes en los criterios dinámicos o promociones durante el tiempo de ejecución con los operadores “es igual que” y “no es igual que”. You should use [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory], and [!UICONTROL Environment] values wisely on the right hand side if the left hand side has predefined attributes or custom attributes.

![](assets/left_right.png)

La tabla siguiente contiene reglas eficaces y reglas que pueden no ser compatibles durante el tiempo de ejecución:

| Reglas compatibles | Reglas potencialmente incompatibles |
|--- |--- |
| value - está entre - 90 % and 110 % de Elemento actual - salesValue | salesValue - está entre - 90 % y 110% de Elemento actual - value |
| value - está entre - 90 % y 110 % de Elemento actual - value | clearancePrice - está entre - 90 % y 110 % de Elemento actual - margin |
| margin - está entre - 90 % y 110 % de Elemento actual - margin | storeInventory - es igual que - Elemento actual - inventory |
| inventory - es igual que - Elemento actual - inventory |  |
