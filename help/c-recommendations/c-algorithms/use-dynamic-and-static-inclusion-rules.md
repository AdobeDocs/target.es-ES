---
keywords: reglas de inclusión;criterios de inclusión;Recommendations;creación de nuevos criterios;promoción;promociones;filtrado dinámico;dinámico;valores en blanco;ignorar regla de filtrado;filtro estático;filtrar por valor;coincidencia de atributos de entidad;coincidencia de atributos de perfil;coincidencia de parámetros;filtrado por valor;filtro estático
description: Aprenda a crear reglas de inclusión en Adobe Target Recommendations para criterios y promociones. Añada reglas de filtrado dinámicas o estáticas adicionales para obtener mejores resultados.
title: ¿Cómo utilizo las reglas de inclusión dinámicas y estáticas en Recommendations?
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
translation-type: tm+mt
source-git-commit: 6ba670ef69fa23c0023636a1920eed15dcd9dd06
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 41%

---

# ![PREMIUM](/help/assets/premium.png) Uso de reglas de inclusión dinámicas y estáticas{#use-dynamic-and-static-inclusion-rules}

Información sobre la creación de reglas de inclusión para criterios y promociones en [!DNL Adobe Target] y la adición de reglas de filtrado dinámicas o estáticas adicionales para obtener mejores resultados para sus recomendaciones.

>[!NOTE]
>
>El proceso de creación y uso de reglas de inclusión para criterios y promociones es similar, al igual que los casos de uso y los ejemplos. Tanto los criterios como las promociones y el uso de reglas de inclusión se tratan en esta sección.

## Agregación de reglas de filtrado a los criterios {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Mientras [crea criterios](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE), haga clic en **[!UICONTROL Agregar regla de filtrado]** en **[!UICONTROL Reglas de inclusión]**.

![](assets/inclusion_options_new.png)

Las opciones disponibles varían en función del sector seleccionado y la clave de recomendación.

## Agregación de reglas de filtrado a las promociones    {#section_D59AFB62E2EE423086281CF5D18B1076}

Mientras [crea una promoción](/help/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), seleccione **[!UICONTROL Promocionar por atributo]** y, a continuación, haga clic en **[!UICONTROL Agregar regla de filtrado]**.

![](assets/inclusion_options.png)

## Tipos de filtro {#section_0125F1ED10A84C0EB45325122460EBCD}

En las secciones siguientes se enumeran los tipos de opciones de filtrado para [!UICONTROL Filtrado dinámico] y [!UICONTROL Filtrar por valor] tanto para criterios como para promociones:

### Filtrado dinámico

Las reglas de inclusión dinámicas son más potentes que las reglas de inclusión estáticas y ofrecen mejores resultados y una mayor participación. Tenga en cuenta lo siguiente:

* Las reglas de inclusión dinámica ofrecen recomendaciones al hacer coincidir un atributo en un parámetro de perfil de usuario o en una llamada de mbox.

   Por ejemplo, puede crear una recomendación &quot;Criterios más populares&quot; y luego filtrar el conjunto de recomendaciones devueltas, luego filtrar cualquier recomendación (en tiempo real) contra un atributo que se pase cuando el usuario acceda a una página donde se muestran las recomendaciones.

* Utilice reglas estáticas para limitar qué artículos se incluyen en la recomendación (en lugar de usar colecciones).

* Puede crear tantas reglas de inclusión dinámicas como sea necesario. Las reglas de inclusión se unen mediante un operador Y. Deben cumplirse todas las reglas para incluir un artículo en una recomendación.

Las siguientes opciones están disponibles para el filtrado dinámico:

| Opción de filtrado dinámico | Detalles |
| --- | --- |
| [Coincidencia de atributos de entidad](/help/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtre dinámicamente comparando un grupo de posibles elementos de recomendaciones con un elemento específico con el que los usuarios han interactuado.<br>Utilice la  [!UICONTROL Coincidencia de atributos de ] entidad cuando desee mostrar recomendaciones que puedan atraer al visitante, como la marca favorita del visitante. |
| [Coincidencia de atributos de perfil](/help/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtre dinámicamente comparando elementos (entidades) con un valor del perfil del usuario.<br>Utilice  [!UICONTROL Coincidencia de atributos de ] perfil cuando desee mostrar recomendaciones que coincidan con un valor almacenado en el perfil del visitante, como el tamaño o la marca favorita. |
| [Coincidencia de parámetros](/help/c-recommendations/c-algorithms/parameter-matching.md) | Filtre dinámicamente comparando elementos (entidades) con un valor de la solicitud (API o mbox).<br>Utilice  [!UICONTROL Coincidencia de ] parámetros para recomendar contenido que coincida con los parámetros de página o los parámetros del visitante, como dimensiones de dispositivo o ubicación geográfica. |

### Filtrar por valor

La siguiente opción está disponible para filtrar por valor:

| Filtrado por valor, opción | Detalles |
| --- | --- |
| [Filtro estático](/help/c-recommendations/c-algorithms/static-value.md) | Introduzca manualmente uno o varios valores estáticos para filtrar. |

## Criterios dinámicos y ejemplos de promoción

Los criterios y promociones dinámicos son mucho más potentes que los estáticos y ofrecen mejores resultados y una mayor participación.

Los siguientes ejemplos proporcionan ideas generales sobre cómo usar las promociones dinámicas en las campañas de marketing:

| Operador | Ejemplos |
| --- | --- |
| Es igual a | Con el operador &quot;es igual que&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en nuestro sitio web (como un producto, un artículo, una película, etc.), podemos promocionar otros elementos de:<ul><li>la misma marca</li><li>la misma categoría</li><li>la misma categoría Y la marca propia</li><li>la misma tienda</li></ul> |
| Does Not Equal | Con el operador &quot;no es igual que&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en nuestro sitio web (como un producto, un artículo, una película, etc.), podemos promocionar otros elementos de:<ul><li>una serie de televisión distinta</li><li>un género distinto</li><li>una serie de productos distinta</li><li>un ID de estilo distinto</li></ul> |
| está entre | Usando el operador &quot;está entre&quot; en las promociones dinámicas, cuando un visitante está viendo un elemento en nuestro sitio web (como un producto, un artículo, una película, etc.), podemos promocionar otros elementos que:<ul><li>sean más caros</li><li>sean menos caros</li><li>cuesten un 30 % más o menos</li><li>sean episodios posteriores de la misma temporada</li><li>sean los primeros libros de una saga</li></ul> |

## Gestión de valores vacíos al filtrar por coincidencia de atributos de entidad, coincidencia de atributos de perfil y coincidencia de parámetros {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Puede elegir varias opciones para gestionar valores vacíos al filtrar por [!UICONTROL Coincidencia de atributos de entidad], [!UICONTROL Coincidencia de atributos de perfil] y [!UICONTROL Coincidencia de parámetros] para criterios de salida y promociones.

Anteriormente, si un valor estaba en blanco no se devolvía ningún resultado. La lista desplegable “Si *x* está en blanco” le permite elegir la acción que se debe realizar si los criterios contienen valores en blanco, como se muestra en la siguiente ilustración:

![](assets/empty_value.png)

Para seleccionar la acción deseada, pase el ratón sobre el icono del engranaje (![](assets/icon_gear.png)) y, a continuación, elija la acción deseada:

| Acción | Disponible para | Detalles |
|--- |--- |--- |
| [!UICONTROL Ignorar esta regla de filtrado] | [!UICONTROL Coincidencia de atributos de perfil ] y coincidencia  [!UICONTROL de parámetros] | Esta es la acción predeterminada para [!UICONTROL Coincidencia de atributos de perfil] y [!UICONTROL Coincidencia de parámetros].<br>Esta opción especifica que la regla se ignora. Por ejemplo, si hay tres reglas de filtrado y la tercera no pasa ningún valor, en vez de no devolver resultado alguno, puede simplemente ignorar la tercera regla con valores en blanco. |
| [!UICONTROL No mostrar ningún resultado para estos criterios]<br> (solo criterios) | [!UICONTROL Coincidencia] de atributos de entidad, coincidencia de atributos de  [!UICONTROL perfil] y coincidencia  [!UICONTROL de parámetros] | Esta es la acción predeterminada para [!UICONTROL Coincidencia de atributos de entidad].<br>[!DNL Target]Esta acción es el modo en que gestiona los valores en blanco antes de la agregación de esta opción: no se mostrarán más resultados para este criterio. |
| [!UICONTROL No promocionar ningún elemento<br> (solo promociones)] | [!UICONTROL Coincidencia] de atributos de entidad, coincidencia de atributos de  [!UICONTROL perfil] y coincidencia  [!UICONTROL de parámetros] | Esta es la acción predeterminada para [!UICONTROL Coincidencia de atributos de entidad].<br>[!DNL Target]Esta acción es el modo en que gestiona los valores en blanco antes de la agregación de esta opción: no se mostrarán más resultados para este criterio. |
| [!UICONTROL Uso de un valor estático] | [!UICONTROL Coincidencia] de atributos de entidad, coincidencia de atributos de  [!UICONTROL perfil] y coincidencia  [!UICONTROL de parámetros] | Si un valor está en blanco, puede optar por usar un valor estático. |

## Advertencias {#section_A889FAF794B7458CA074DEE06DD0E345}

>[!IMPORTANT]
>
>Es posible que no se puedan usar atributos de tipo de datos diferentes en los criterios dinámicos o promociones durante el tiempo de ejecución con los operadores “es igual que” y “no es igual que”. Debe utilizar los valores [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory] y [!UICONTROL Environment] sabiamente en el lado derecho si el lado izquierdo tiene atributos predefinidos o personalizados.

![](assets/left_right.png)

La tabla siguiente contiene reglas eficaces y reglas que pueden no ser compatibles durante el tiempo de ejecución:

| Reglas compatibles | Reglas potencialmente incompatibles |
|--- |--- |
| value - está entre - 90 % and 110 % de Elemento actual - salesValue | salesValue - está entre - 90 % y 110% de Elemento actual - value |
| value - está entre - 90 % y 110 % de Elemento actual - value | clearancePrice - está entre - 90 % y 110 % de Elemento actual - margin |
| margin - está entre - 90 % y 110 % de Elemento actual - margin | storeInventory - es igual que - Elemento actual - inventory |
| inventory - es igual que - Elemento actual - inventory |  |
