---
description: Los criterios son reglas que determinan qué productos se recomiendan en función de un conjunto predeterminado de comportamientos del visitante.
keywords: recomendaciones;actividad de recomendaciones;criterios;algoritmo
seo-description: Los criterios de Adobe Target son reglas que determinan qué productos se recomiendan en función de un conjunto predeterminado de comportamientos del visitante.
seo-title: Criterios
solution: Target
title: Criterios
title-outputclass: premium
topic: Premium
uuid: 738db164-174b-45b8-bb8a-778f6494f1d7
badge: premium
translation-type: tm+mt
source-git-commit: 0fa977d249a83232deb1448db2131038f6f2173f

---


# ![PREMIUM](/help/assets/premium.png) Criterios{#criteria}

Los criterios son reglas que determinan qué productos se recomiendan en función de un conjunto predeterminado de comportamientos del visitante.

Los criterios determinan qué acción se obtendrá en cada recomendación. Puede probar distintos tipos de recomendaciones entre sí si se agregan varios criterios.

## Sector {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Puede seleccionar un sector según los objetivos de la actividad de recomendación:

| Sector | Objetivo |
|--- |--- |
| Venta minorista/Comercio electrónico | Conversión que termina en compra |
| Generación de vanguardia/B2B/Servicios financieros | Conversión sin compra |
| Medios/Publicación | Participación |

## Clave de recomendación.  {#section_885B3BB1B43048A88A8926F6B76FC482}

La clave de recomendación que seleccione determina el tipo de criterio. Existen varios tipos de criterios que se representan como tarjetas de criterio cuando configura una actividad de [!DNL Recommendations].

| Tipo de criterio | Claves |
|--- |--- |
| Actividad de la página actual | Recomiende artículos en función de lo que los usuarios hacen en la página actual. Por ejemplo, a los visitantes que ven un determinado artículo podría interesarles ver otros artículos de la misma categoría.<ul><li>Artículo actual</li><li>Categoría actual</li></ul> |
| Personalizado | Recomendar artículos según atributos personalizados.<ul><li>Atributo personalizado</li></ul>Cuando basa las recomendaciones en atributos personalizados, debe seleccionar el atributo personalizado y luego seleccionar el tipo de recomendación.<br>Puede realizar el filtrado en tiempo real sobre su propia salida de criterios personalizados. Por ejemplo, puede limitar sus artículos recomendados solo a aquellos de la categoría o marca favorita de un visitante. Esto le da la capacidad de combinar cálculos sin conexión con filtrado en tiempo real.<br>Esta funcionalidad significa que puede usar Target para agregar una personalización además de sus recomendaciones calculadas sin conexión o listas personalizadas. Esto combina el poder de sus científicos e investigadores de datos con la entrega probada y comprobada de Adobe, el filtrado en tiempo de ejecución, las pruebas A/B, la orientación, los informes, las integraciones y más.<br>Con la adición de reglas de inclusión en Criterios personalizados, convierte las recomendaciones estáticas en recomendaciones dinámicas basadas en los intereses de los visitantes.<ul><li>Los criterios personalizados se pueden configurar, como otros criterios en las recomendaciones.</li><li>Puede usar [colecciones](/help/c-recommendations/c-products/collections.md), [exclusiones](/help/c-recommendations/c-products/exclusions.md) e [inclusiones](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluyendo las reglas especiales para Precio e Inventario) de la misma forma que cualquier otro criterio.</li></ul>Los posibles casos de uso incluyen:<ul><li>Desea recomendar películas de una lista personalizada, pero solo si el visitante no las ha visto.</li><li>Desea ejecutar un algoritmo sin conexión y usar los resultados para potenciar sus recomendaciones, pero debe asegurarse de que los artículos agotados no sean recomendados.</li><li>Desea incluir solo los elementos que pertenecen a la categoría favorita de este visitante.</li></ul> |
| Comportamiento anterior | Recomiende artículos en función de cómo hayan respondido los visitantes a un artículo en el pasado. Por ejemplo, las personas que compraron una determinada marca son más propensas a comprar otro artículo de la misma marca.<ul><li>Último artículo comprado</li><li>Último artículo visitado</li><li>Artículo más visitado</li><li>Categoría favorita</li></ul> |
| Popularidad | Recomiende los artículos más populares, como los vídeos más populares de una categoría relacionada o los productos que se han visto con más frecuencia en su sitio.<ul><li>Popularidad</li></ul> |
| Artículos vistos recientemente | Recomiende los artículos que un visitante ha visto más recientemente, como los artículos que vio la última vez que estuvo en el sitio o los artículos más de moda en este momento.<br>El algoritmo de artículos vistos recientemente devuelve los resultados específicos de la actividad de un visitante dentro de un [entorno](/help/administrating-target/hosts.md). Si dos sitios pertenecen a entornos diferentes y un visitante cambia entre los dos, el algoritmo devuelve solamente los artículos vistos recientemente en el sitio apropiado.<br>Este tipo de criterios no está limitado por colecciones.<ul><li>Artículos vistos recientemente</li></ul>**Nota:** No puede usar los criterios de Artículos vistos recientemente para recomendaciones de copia de seguridad.<br>Los elementos/medios vistos recientemente se pueden filtrar para que solo se muestren los elementos con un atributo en particular.<ul><li>Los criterios visualizados recientemente se pueden configurar, como otros criterios en las recomendaciones.</li><li>Puede usar [colecciones](/help/c-recommendations/c-products/collections.md), [exclusiones](/help/c-recommendations/c-products/exclusions.md) e [inclusiones](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluyendo las reglas especiales para Precio e Inventario) de la misma forma que cualquier otro criterio.</li></ul>Los posibles casos de uso incluyen:<ul><li>Una empresa multinacional con múltiples negocios podría tener elementos de visualización de visitantes en múltiples propiedades digitales. En este caso, se pueden limitar los elementos vistos recientemente para que solo se muestren en relación con la propiedad respectiva en la que se visualizaron. Esto impide que los Elementos visualizados recientemente se muestren en el sitio de otra propiedad digital.</li></ul> |


## Criterios y algoritmos.  {#criteria-algorithms}

[!DNL Target Recommendations] emplea sofisticados algoritmos que determinan si las acciones de un visitante cumplen los criterios establecidos en su actividad. La clave de recomendación determina las opciones de lógica de recomendaciones que se encuentran disponibles.

| Criterios | Descripción |
|--- |--- |
| Elementos/Medios con atributos similares | Recomienda artículos o medios similares a artículos o medios según la actividad de la página actual o el comportamiento de visitantes anteriores.<br>**Nota:** Si selecciona Artículos/Medios con atributos similares, tendrá la opción de definir reglas de contenido similares. |
| Los usuarios que vieron esto, vieron aquello. | Recomienda artículos que se visitan con mayor frecuencia en la misma sesión en que se ve el artículo especificado. |
| Los usuarios que vieron esto, compraron aquello. | Recomienda artículos que se compran con mayor frecuencia en la misma sesión en que se ve el artículo especificado. Este criterio devuelve otros productos que otras personas compraron después de haber visto el producto especificado. Este producto no se incluye en el conjunto de resultados. |
| Los usuarios que compraron esto, compraron aquello. | Recomienda artículos que se compran con mayor frecuencia junto al artículo especificado. |
| Afinidad del sitio | Recomienda elementos según la certeza de una relación entre artículos. Puede configurar este criterio para determinar la cantidad de datos que se requiere antes de presentar una recomendación con el regulador Reglas de inclusión. Por ejemplo, si selecciona Muy fuerte, se recomiendan los productos con la certeza más sólida de una coincidencia.<br>Por ejemplo, si establece una afinidad muy fuerte y el diseño incluye cinco artículos, tres de los cuales cumplen la seguridad de umbral de conexión, los dos artículos que no cumplen los requisitos mínimos de seguridad no se muestran en las recomendaciones y son reemplazados por sus artículos de copia de seguridad definidos. Los artículos con la mayor afinidad se muestran primero.<br>Es posible que algunos clientes con diferentes colecciones de productos y diversos comportamientos de sitio obtengan mejores resultados si establecen una afinidad de sitio débil. |
| Principales vendedores | Los artículos que están incluidos en los pedidos más completados. Varias unidades del mismo artículo en un único pedido se cuentan como un solo pedido. |
| Más visitados | Los artículos o medios que se visitan con mayor frecuencia. |
| Elementos/Medios vistos recientemente | Artículos que el visitante ha visto recientemente. Cuando utilice este criterio, deberá actualizar el diseño de Target para controlar los casos en los que se mostrarían recomendaciones en blanco cuando no hubiera suficientes artículos vistos previamente para mostrar. |
| Recomendaciones basadas en el usuario | Recomienda artículos en función del historial de exploración, visualización y compra de cada visitante. Estos artículos generalmente se conocen como "Recomendado para usted".<br>Este criterio le permite entregar contenido y experiencias personalizados tanto a visitantes nuevos como a visitantes que regresan. La lista de recomendaciones se centra en la actividad más reciente del visitante y se actualiza durante la sesión y se personaliza a medida que el usuario navega por el sitio.<br>Tanto las vistas como las compras se utilizan para determinar los artículos recomendados. La clave de recomendación especificada (por ejemplo, Elemento actual) se utiliza para aplicar cualquier filtro de regla de inclusión que seleccione. Por ejemplo, puede:<ul><li>Excluir elementos que no cumplen determinados criterios (productos sin existencias, artículos publicados hace más de 30 días, películas clasificadas como R, etc.)</li><li>Limitar los artículos incluidos a una sola categoría o a la categoría actual</li></ul> |

>[!NOTE] {class="- topic/note "}
>
>Si está ejecutando una recomendación y cambia su criterio, perderá los datos de informes.

También puede utilizar información adicional conocida acerca de un visitante para mejorar sus recomendaciones.

Todos los criterios de un día se ejecutan dos veces al día. Todos los criterios de una semana y un período mayor se ejecutan una vez al día. Los criterios de afinidad del sitio se ejecutan una vez al día. Los criterios de copia de seguridad se ejecutan dos veces al día.

## Información sobre los criterios de visualización.  {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Para ver los detalles de los criterios de una tarjeta emergente, pase el cursor sobre una tarjeta y haga clic en el icono Información sin necesidad de abrir los criterios.

![Mantener el puntero encima de la tarjeta de criterios](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

Haga clic en la pestaña **[!UICONTROL Información del algoritmo]** para ver información general sobre los criterios seleccionados, como Nombre, Descripciones, Sector, Tipos de página, Clave de recomendación, Lógica de recomendación e ID del algoritmo.

![Pestaña Información del algoritmo](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

Haga clic en la pestaña **[!UICONTROL Uso del algoritmo]** para ver una lista de actividades que hacen referencia a los criterios seleccionados. La tarjeta enumera las actividades activas e inactivas. Haga clic en las listas desplegables Actividades activas o Inactividades para ver la lista completa de actividades que hacen referencia a ese criterio. Puede hacer clic en el vínculo de la actividad para abrirla y modificarla.

![Pestaña Uso de criterios](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

## Determinación de cuándo los resultados de criterios están listos para mostrarse.  {#section_03F328C07F234692B6D996DF745584B3}

En el diagrama de actividad, las tarjetas de criterios ahora indican cuándo los resultados están listos para mostrarse. Saber si los resultados están listos para mostrarse ayuda a determinar si la actividad está preparada para su activación. Saber si los resultados están listos para mostrarse también ayuda a saber si hay algún problema con los criterios.

>[!NOTE]
>
>Para consultar la cuestión sobre los tiempo de carga, vea “Tiempo esperado de procesamiento de criterios” en [Creación de criterios](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

En la siguiente ilustración se muestra el diagrama de actividad en la página Información general de una actividad de Recommendations. También puede ver el diagrama de actividad con los resultados de estado de los criterios, obtenidos en el paso 2 del flujo de trabajo de creación de la actividad.

![Estado de criterios en la página Información general](/help/c-recommendations/c-algorithms/assets/criteria_status.png)

Los resultados de estado pueden ser: Resultados preparados, Resultados no preparados y Error de fuente, como se muestra en el diagrama siguiente:

![](assets/criteria_status_multi.png)

