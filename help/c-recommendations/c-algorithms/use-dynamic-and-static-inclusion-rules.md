---
keywords: inclusion rules;inclusion criteria;recommendations;create new criteria;promotion;promotions;dynamic filtering;dynamic;empty values;ignore filtering rule;static filter;filter by value;entity attribute matching;profile attribute matching;parameter matching;filter by value;static filter
description: Información sobre la creación de reglas de inclusión en Adobe Target Recommendations para criterios y promociones, y la adición de reglas de filtrado dinámicas o estáticas adicionales para obtener mejores resultados.
title: Usar reglas de inclusión dinámicas y estáticas en Adobe Target Recommendations
feature: criteria
mini-toc-levels: 3
uuid: f0ee2086-1126-44a4-9379-aa897dc0e06b
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 45%

---


# ![PREMIUM](/help/assets/premium.png) Uso de reglas de inclusión dinámicas y estáticas{#use-dynamic-and-static-inclusion-rules}

Information about creating inclusion rules for criteria and promotions in [!DNL Adobe Target] and adding additional dynamic or static filtering rules to achieve better results for your recommendations.

El proceso de creación y uso de reglas de inclusión para criterios y promociones es similar, al igual que los casos de uso y los ejemplos. Tanto los criterios como las promociones y el uso de las reglas de inclusión están cubiertos en esta sección.

## Agregación de reglas de filtrado a los criterios {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Mientras [crea criterios](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE), haga clic en **[!UICONTROL Agregar regla de filtrado]** en **[!UICONTROL Reglas de inclusión]**.

![](assets/inclusion_options_new.png)

Las opciones disponibles varían en función del sector seleccionado y la clave de recomendación.

## Agregación de reglas de filtrado a las promociones   {#section_D59AFB62E2EE423086281CF5D18B1076}

Mientras [crea una promoción](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), seleccione **[!UICONTROL Promocionar por atributo]** y, a continuación, haga clic en **[!UICONTROL Agregar regla de filtrado]**.

![](assets/inclusion_options.png)

## Tipos de filtro {#section_0125F1ED10A84C0EB45325122460EBCD}

Las siguientes secciones lista los tipos de opciones de filtrado para criterios y promociones, Filtro dinámico y Filtrar por valor:

### Filtrado dinámico

Las reglas de inclusión dinámicas son más potentes que las reglas de inclusión estáticas y ofrecen mejores resultados y participación. Tenga en cuenta lo siguiente:

* Las reglas de inclusión dinámica ofrecen recomendaciones al hacer coincidir un atributo en el parámetro de perfil de un usuario o en una llamada de mbox.

   Por ejemplo, puede crear una recomendación &quot;Criterios más populares&quot; y, a continuación, del conjunto de recomendaciones devueltas, filtrar cualquier atributo que se pase cuando el usuario acceda a una página en la que se muestren las recomendaciones en tiempo real.

* Utilice reglas estáticas para limitar los artículos que se incluyen en la recomendación (en lugar de las colecciones).

* Puede crear tantas reglas de inclusión dinámicas como sea necesario. Las reglas de inclusión se unen mediante un operador Y. Deben cumplirse todas las reglas para incluir un artículo en una recomendación.

Las siguientes opciones están disponibles para el filtrado dinámico:

| Opción de filtrado dinámico | Detalles |
| --- | --- |
| [Coincidencia de atributos de entidad](/help/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtre dinámicamente comparando un grupo de posibles elementos de recomendaciones con un elemento específico con el que los usuarios han interactuado.<br>Utilice Coincidencia de atributos de entidad cuando desee mostrar las recomendaciones que más probablemente atraigan al visitante, como la marca favorita del visitante. |
| [Coincidencia de atributos de perfil](/help/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtre dinámicamente comparando elementos (entidades) con un valor en el perfil del usuario.<br>Utilice Coincidencia [!UICONTROL de atributos de] Perfil cuando desee mostrar recomendaciones que coincidan con un valor almacenado en el perfil del visitante, como tamaño o marca favorita. |
| [Coincidencia de parámetros](/help/c-recommendations/c-algorithms/parameter-matching.md) | Filtre dinámicamente comparando elementos (entidades) con un valor de la solicitud (API o mbox).<br>Utilice la coincidencia de parámetros para recomendar contenido que coincida con los parámetros de página o los parámetros de visitantes, como las dimensiones del dispositivo o la ubicación geográfica. |

### Filtrar por valor

La siguiente opción está disponible para filtrar por valor:

| Filtrado por valor, opción | Detalles |
| --- | --- |
| [Filtro estático](/help/c-recommendations/c-algorithms/static-value.md) | Introduzca manualmente uno o varios valores estáticos para filtrar. |

## Criterios dinámicos y ejemplos de promoción

Los criterios y promociones dinámicos son mucho más potentes que los estáticos y ofrecen mejores resultados y una mayor participación.

Los siguientes ejemplos le proporcionarán ideas generales sobre cómo puede utilizar las promociones dinámicas en sus esfuerzos de mercadotecnia:

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
