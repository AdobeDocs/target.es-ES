---
keywords: activities list;activities;activity;activity types;edit activity;activity actions;activity attribute;activity list filter;activity limitations;personalize;personalization
description: Las actividades de Adobe Target le permiten personalizar el contenido para audiencias específicas y probar diseños de página
title: Las actividades de Adobe Target le permiten personalizar el contenido para audiencias específicas y probar diseños de página.
feature: Activities
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '2090'
ht-degree: 97%

---


# Actividades

Las actividades de [!DNL Adobe Target] le permiten personalizar el contenido para audiencias específicas y probar diseños de página.

Por ejemplo, podría diseñar una actividad que pruebe dos páginas de aterrizaje diferentes: una que destaque información sobre calzado de verano de mujer y otra que destaque ropa de verano más general. La actividad determina las condiciones que controlan cuándo aparece cada una de estas páginas de aterrizaje y las métricas que determinan qué página tiene mayor éxito. La actividad está configurada para comenzar y finalizar cuando se cumplan unas condiciones específicas como, por ejemplo, entre fechas concretas o que comience cuando se apruebe la actividad y finalice cuando se desactive.

Al diseñar una actividad, debería planificarla con mucho cuidado. Determine cuándo comenzará la actividad y la duración que tendrá. A continuación, enumere las ofertas y asigne una audiencia segmentada a cada una de ellas.

## Tipos de actividades

Target incluye varios tipos de actividades. En la tabla siguiente se proporciona una descripción general de cada tipo de actividad con vínculos para ayudarle a obtener más información. Para elegir mejor el mejor tipo de actividad, también hemos creado la [Guía de actividades de Adobe Target](/help/c-activities/target-activities-guide.md).

| Tipo de actividad | Descripción |
|--- |--- |
| [Prueba A/B](/help/c-activities/t-test-ab/test-ab.md) | Una prueba A/B compara dos o más versiones del contenido de su sitio web para comprobar cuál mejora más las conversiones durante un periodo previamente establecido.<br>**Nota:** Ahora puede incluir [recomendaciones dentro de las actividades de prueba A/B](/help/c-recommendations/recommendations-as-an-offer.md). Para esta funcionalidad, es necesaria una [licencia de Target Premium](/help/c-intro/intro.md#premium). |
| [Asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Asignación automática identifica un ganador entre dos o más experiencias y le reasigna automáticamente más tráfico para aumentar las conversiones mientras la prueba sigue ejecutándose y aprendiendo.<br>**Nota:** Ahora puede incluir [recomendaciones dentro de las actividades de asignación automática](/help/c-recommendations/recommendations-as-an-offer.md). Para esta funcionalidad, es necesaria una [licencia de Target Premium](/help/c-intro/intro.md#premium). |
| [Segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md)<br>![Target Premium](/help/assets/premium.png) | La segmentación automática utiliza aprendizaje automático avanzado para identificar varias experiencias de alto nivel de rendimiento definidas por expertos en marketing, y ofrece a cada visitante la experiencia más adaptada en función de su perfil de cliente y del comportamiento de visitantes anteriores con perfiles similares, todo ello con el fin de personalizar el contenido y dirigir las conversiones.<br>**Nota:** Ahora puede incluir [recomendaciones dentro de las actividades de segmentación automática](/help/c-recommendations/recommendations-as-an-offer.md). Para esta funcionalidad, es necesaria una [licencia de Target Premium](/help/c-intro/intro.md#premium). |
| [Uso de datos de Analytics](/help/c-activities/t-test-ab/t-test-create-ab/create-a4t.md) (A4T) | Puede configurar una actividad para que use [!DNL Adobe Analytics] como fuente de informes. Para este tipo de actividad es necesario que vincule su cuenta de [!DNL Adobe Experience Cloud] con [!DNL Analytics] y [!DNL Target]. |
| [Prueba multivariable](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | La prueba multivariable (MVT) compara combinaciones de ofertas de elementos en una página para determinar qué combinación ofrece el mejor rendimiento para una audiencia específica, además de identificar qué elemento tiene el mayor impacto en el éxito de la actividad. |
| [Segmentación de experiencias](/help/c-activities/t-experience-target/experience-target.md) | Segmentación de experiencias (XT) ofrece contenido a una audiencia específica en función de un conjunto de reglas y criterios definidos por expertos en marketing.<br>**Nota:** Ahora puede incluir [recomendaciones dentro de las actividades de segmentación de experiencias](/help/c-recommendations/recommendations-as-an-offer.md). Para esta funcionalidad, es necesaria una [licencia de Target Premium](/help/c-intro/intro.md#premium). |
| [Personalización automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>![Target Premium](/help/assets/premium.png) | La personalización automatizada (AP) combina ofertas o mensajes, y utiliza aprendizaje automático avanzado para asignar diferentes variaciones a cada visitante en función de su perfil de cliente, con el fin de personalizar el contenido y dirigir las conversiones. |
| [Recommendations](/help/c-recommendations/recommendations.md)<br>![ Target Premium](/help/assets/premium.png) | Una recomendación determina el modo en que se sugiere un producto a un usuario del sitio web según las actividades que este realice en el sitio.<br>Por ejemplo, puede que quiera animar a los usuarios que compran una mochila a que consideren la opción de comprar botas y bastones de senderismo. Podría crear una recomendación que muestre artículos que a menudo se compran juntos, empleando el algoritmo “Otras personas que compraron esto también compraron aquello”. O puede que quiera animar a los visitantes a pasar más tiempo en su sitio multimedia mediante la recomendación de un vídeo similar al que están viendo, empleando el algoritmo “Otras personas que han visto esto también vieron aquello”.<br>**Nota:** Ahora puede incluir recomendaciones dentro de la prueba A/B (incluidas las actividades de asignación automática y segmentación automática) y actividades de segmentación de experiencias (XT). Consulte [Recommendations como oferta](/help/c-recommendations/recommendations-as-an-offer.md). |

## lista de actividades {#section_DE8E2DB30D534962A931EF8BB48240F5}

La lista [!UICONTROL Actividades] es la vista predeterminada al abrir [!DNL Target]. Desde esta página, puede crear nuevas actividades y administrar las actividades existentes.

También puede mostrar la lista [!UICONTROL Actividades] haciendo clic en la pestaña [!UICONTROL Actividades] en la parte superior de la [!DNL Target]interfaz de usuario.

![lista de actividades](/help/c-activities/assets/activities-list.png)

En la lista Actividades encontrará una descripción general de todas las actividades:

| Elemento | Descripción |
|--- |--- |
| Tipo | El tipo de actividad, como A/B o MVT. |
| Nombre | El nombre de la actividad. |
| Dirección URL | La dirección URL aparece en el texto más claro debajo del nombre.<br>La dirección URL de la actividad indica dónde se muestra la actividad. De este modo, se puede identificar rápidamente una actividad y determinar si ya se está realizando una prueba en una página en particular.<br>Si se realiza una prueba en varias direcciones URL, se indica mediante un vínculo cuántas direcciones URL más se están usando. Haga clic en el vínculo para ver la lista completa de direcciones URL de esa actividad.<br>Puede buscar según la dirección URL. Utilice la lista desplegable situada junto al cuadro de búsqueda y seleccione [!UICONTROL Buscar URL]. |
| Estado | Las actividades pueden tener uno de los estados siguientes:<ul><li>**Activa:** la actividad está ejecutándose.</li><li>**Borrador:** se ha iniciado la configuración de la actividad, pero aún no está lista para ejecutarse.</li><li>**Programada:** la actividad está preparada para activarse en la fecha y hora de inicio especificadas.</li><li>**Inactiva:** la actividad se ha pausado o desactivado.</li><li>**Sincronizando**: la actividad se ha guardado y se está sincronizando con la red de entrega de Target.</li><li>**Completada**: se han alcanzado la fecha y hora de finalización especificadas para la actividad y esta ya no se sirve.</li><li>**Archivada**: se archivó la actividad. Puede activar una actividad archivada para volver a usarla.</li></ul>**Nota:** Cuando se realizan determinadas acciones (por ejemplo, activar una actividad fuera de la interfaz de usuario empleando métodos API), los cambios pueden tardar hasta 10 minutos en propagarse a la IU. |
| Fuente | Muestra dónde se creó la actividad:<ul><li>Adobe Target</li><li>Adobe Target Classic</li><li>Adobe Experience Manager.  (AEM)</li><li>Adobe Mobile Services (AMS)</li></ul> |
| Propiedad | Muestra la [propiedad](/help/administrating-target/c-user-management/property-channel/property-channel.md) de la actividad. |
| Alza estimada en ingresos | Muestra el aumento previsto en ingresos si el 100 % de la audiencia ve la experiencia ganadora.<br>Se calcula utilizando la fórmula siguiente:<br>`(<winning experience> - <control experience>)*<total number of visitors>`<br> el número resultante se redondea a un decimal, como máximo, si la forma corta tiene un solo dígito antes del decimal. Por ejemplo: 1,6 millones de dólares, 60 mil dólares, 900 dólares, 8500 dólares, 205 mil dólares<br> En esta columna se muestra “---” para las actividades que no tienen datos suficientes para convocar un concurso ganador o que no tienen una previsión del coste.Para obtener más información, <br>consulte [Alza estimada en ingresos](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md). |
| Última actualización | La fecha y el autor de la última actualización de la actividad. |

Desplace el cursor sobre una actividad para ver las acciones disponibles.

![Acciones de la lista de actividades](/help/c-activities/assets/activities_list_hover.png)

Las siguientes acciones están disponibles (en función de sus permisos):

| Acción | Descripción |
| --- | --- |
| Editar | Cambia la actividad. Todas las actividades se pueden editar.<br>Para obtener más información sobre las distintas formas de editar actividades, consulte [Editar una actividad o guardarla como borrador](/help/c-activities/edit-activity.md). |
| Desactivar | Detiene una actividad activa o programada. Las campañas desactivadas se pueden reactivar o archivar<br>Si desactiva o archiva una actividad y la reactiva más adelante, el visitante seguirá formando parte de esa actividad después de la reactivación, si estaba en ella antes de la desactivación o del archivado. No se atribuirá a esa actividad ninguna métrica de conversión registrada durante el tiempo entre los dos eventos. |
| Activar | Inicia una actividad inactiva o preparada. |
| Archivar | Enviar la actividad al archivo. De forma predeterminada, las actividades archivadas se dejan de incluir en la lista de actividades. Si quiere verlas, cambie el filtro de la lista de actividades para que se incluyan. Puede activar una actividad archivada para volver a usarla.<br>Si desactiva o archiva una actividad y luego la reactiva más tarde, un visitante seguirá formando parte de esa actividad después de la reactivación si estaba en ella antes de la desactivación o del archivado. No se atribuirá a esa actividad ninguna métrica de conversión registrada durante el tiempo entre los dos eventos. |
| Copiar | Copia una actividad. Se pueden copiar todas las actividades. Al copiar una actividad, se crea una nueva actividad con el mismo nombre y se anexa el texto “copia”. Por ejemplo, una prueba llamada “Ofertas de navegador” se copiará en “Ofertas de navegador copia”.<br>Las ofertas visuales se copian con la actividad. Puede editar las ofertas de forma segura en la copia sin que la actividad original se vea afectada. La única excepción son las imágenes y las ofertas guardadas en la carpeta Contenido/Recursos. |
| Eliminar | Eliminar un borrador o una actividad.<BR>**NOTA**: Las actividades eliminadas no se pueden recuperar. A menos que esté absolutamente seguro de que nunca necesitará esta actividad, utilice la acción [!UICONTROL Archivar]. A continuación, puede volver a activar la actividad si es necesario. |

Tenga en cuenta los detalles siguientes sobre la lista de Actividades:

* Las actividades archivadas y finalizadas no se incluyen en la lista [!UICONTROL Actividades]. Para verlas, fíltrelas con la configuración avanzada de filtrado del carril izquierdo.
* En cuanto una actividad creada originalmente en [!DNL Target Classic] se desactiva o elimina, se elimina de [!DNL Target Standard/Premium]. Las actividades eliminadas creadas originalmente en [!DNL Target Classic] no se envían a la carpeta [!UICONTROL Archivo] de [!DNL Target Standard/Premium]. La funcionalidad de carpeta archivada se aplica solo a las actividades creadas en [!DNL Target Standard/Premium].
* Todos los tipos de actividades que no son [!UICONTROL Personalización automatizada](AP), [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] le dan la opción de usar [!DNL Target] o [!DNL Adobe Analytics] como fuente de datos. [!UICONTROL La personalización automatizada], [!UICONTROL la asignación automática] y [!UICONTROL la segmentación automática] *siempre* utilizan datos de [!DNL Target].
* Las actividades están disponibles en varios canales:

   * Sitios web y móviles
   * Pantallas y dispositivos conectados a Internet, incluidos los quioscos y cajeros automáticos
   * Correo electrónico y otros canales de adquisición o sitios de socios
   * Aplicaciones móviles
   * Cualquier otro sitio donde se pueda publicar contenido etiquetado

## Organización y filtro de la lista de actividades {#section_41DAD479FFF740E2BB67BF4825955670}

De manera predeterminada, la lista se ordena por la fecha de la última modificación de la actividad, con la más reciente al principio. Sin embargo, hay varias opciones de filtrado que le pueden ayudar a personalizar la lista para que se muestren las actividades que le interesa consultar.

### Búsqueda   {#search-heading}

Utilice el campo de búsqueda para buscar las actividades que cumplen sus criterios de búsqueda.

![Búsqueda de actividades](/help/c-activities/assets/activities_search_new.png)

El campo de búsqueda incluye un menú desplegable para ayudarle a limitar la búsqueda. Solo tiene que especificar uno de los siguientes filtros de búsqueda:  [!UICONTROL Nombre de la actividad] y [!UICONTROL URL].

### Filtros de la lista de actividades

Puede seleccionar filtros de la lista de actividades para determinar qué actividades aparecen en la lista.

![Filtro de las actividades por tipo](/help/c-activities/assets/activities_filters_new.png)

Se puede filtrar por las siguientes opciones. En cada categoría, si no hay nada seleccionado, el valor predeterminado es Todos.

| Categoría de filtro | Filtro |
|--- |--- |
| Tipo | Prueba A/B: [manual](/help/c-activities/t-test-ab/test-ab.md), [asignación automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) y [segmentación automática](/help/c-activities/auto-target/auto-target-to-optimize.md).<br>[Personalización automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>[Segmentación de experiencias](/help/c-activities/t-experience-target/experience-target.md)<br>[Prueba multivariable](/help/c-activities/c-multivariate-testing/multivariate-testing.md)<br>[Recommendations](/help/c-recommendations/recommendations.md) |
| Estado | Activa<br>Borrador<br>Programada<br>Inactiva<br>Sincronizando<br>Completada<br>Archivada |
| Fuente de informes | Target<br>Analytics |
| Compositor de experiencias | Visual<br>Basadas en formularios |
| Tipo de métricas | Conversión<br>Ingreso<br>Participación |
| Fuente de la actividad | Adobe Target<br>Adobe Target Classic<br>Adobe Experience Manager<br>Adobe Mobile Services |

### Organización por atributo de actividad

Haga clic en uno de los encabezados siguientes para cambiar si las actividades se muestran en orden ascendente o descendente, según el encabezado seleccionado.

* Nombre de la actividad
* Tipo de actividad

![Orden ascendente de la lista de actividades](/help/c-activities/assets/activities_list_ascending.png)

## Sugerencias y trucos {#section_F77F30A246A14B538D9363B7F3639F97}

Saque el máximo provecho de Adobe Target aprendiendo más cosas acerca de las distintas funciones y vea los motivos por los cuales debe darles una oportunidad. La función Sugerencias y trucos proporciona vínculos a vídeos, casos de uso, blogs, documentación y mucho más.

La función Sugerencias y trucos se muestra periódicamente en la página de la lista de Actividades. Después de leer o descartar una sugerencia, no se vuelve a mostrar hasta que la próxima sugerencia esté disponible. Opcionalmente, puede deshabilitar la visualización de todas las sugerencias haciendo clic en el icono Ayuda > [!UICONTROL Deshabilitar sugerencia del día].

![Deshabilitación de la sugerencia del día](/help/c-activities/assets/tip-disable-new.png)

## Limitaciones {#section_049D4684403A4E07B998067EB8E9BE56}

Cada actividad de Target tiene las siguientes limitaciones de contenido:

| Elemento | Límite |
|--- |--- |
| Selectores únicos | 300 Si un selector se repite en otra experiencia, se contabiliza una vez. Pero si se repite en la misma experiencia, se vuelve a contabilizar. |
| Ofertas en cada experiencia | 350 |
| Selectores de seguimiento de clics en métricas | 50 |
| Mboxes en métricas | 50 |
| Audiencias y ubicaciones | 50 La combinación de audiencias y ubicaciones (mbox) no debería superar el límite de 50. |

La actividad no se puede guardar si supera alguno de estos límites.

Si incrementa los números de estos artículos en su actividad, también se incrementa el tiempo que se tarda en sincronizar la actividad en Target.

Para límites adicionales del Compositor de experiencias visuales, consulte [Limitaciones del Compositor de experiencias visuales](/help/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Atributos importados en Target para actividades actualizadas fuera de Target {#section_802B0D174E6A44E1A96F404CA81AAE44}

Si las actividades creadas en [!DNL Target] se actualizan desde fuera de [!DNL Target] (por ejemplo, mediante Adobe I/O), los siguientes atributos de actividad se importan de vuelta en [!DNL Target]:

`thirdpartyId`

`startDate`

`endDate`

`status`

`priority`

`marketingCloudMetadata(remoteModifiedBy)`

Este trabajo de importación se ejecuta cuando se abre la página de actividades, con un retardo máximo de diez minutos. (KB-1526)

## Vídeos de formación {#section_BE80D13A2E81460C885F902010E1AD87}

Los siguientes vídeos contienen más información sobre los conceptos mencionados en este artículo.

### Tipos de actividades (9:03) ![Distintivo de información general](/help/assets/overview.png)

En este vídeo se describen los tipos de actividades disponibles en [!DNL Target Standard/Premium].

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Administración de Actividades (5:55) ![Distintivo de información general](/help/assets/overview.png)

En este vídeo se explica cómo usar la lista Actividades para gestionar las actividades.

* Definir el término *actividad*
* Buscar actividades en la lista Actividades
* Editar, desactivar, copiar y eliminar actividades

>[!VIDEO](https://video.tv.adobe.com/v/18550)
