---
keywords: actividades;actividades;tipos de actividades;editar actividad;acciones de actividades;atributo de actividad;filtro de lista de actividades;limitaciones de actividades;personalizar;personalización;actividades
description: Descubra cómo funcionan las actividades en Adobe [!DNL Target] le permite personalizar el contenido para audiencias específicas y probar los diseños de página.
title: ¿Cómo puedo personalizar el contenido y probar los diseños de página con [!DNL Target]?
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: dba58f591b60ccfa1cdcd27d2704ebf28c40ba10
workflow-type: tm+mt
source-wordcount: '2465'
ht-degree: 45%

---

# Actividades

Las actividades de [!DNL Adobe Target] le permiten personalizar el contenido para audiencias específicas y probar los diseños de página.

Por ejemplo, podría diseñar una actividad que pruebe dos páginas de aterrizaje diferentes: una que destaque información sobre calzado de verano de mujer y otra que destaque ropa de verano más general. La actividad determina las condiciones que controlan cuándo aparece cada una de estas páginas de aterrizaje y las métricas que determinan qué página tiene mayor éxito. La actividad está configurada para comenzar y finalizar cuando se cumplan unas condiciones específicas como, por ejemplo, entre fechas concretas o que comience cuando se apruebe la actividad y finalice cuando se desactive.

Al diseñar una actividad, debería planificarla con mucho cuidado. Determine cuándo se inicia la actividad y cuánto dura. A continuación, enumere las ofertas y asigne una audiencia segmentada a cada una de ellas.

## lista de actividades {#section_DE8E2DB30D534962A931EF8BB48240F5}

La lista [!UICONTROL Actividades] es la vista predeterminada al abrir [!DNL Target]. Puede crear actividades desde esta página y administrar las actividades existentes.

También puede mostrar la lista [!UICONTROL Actividades] haciendo clic en la pestaña [!UICONTROL Actividades] en la parte superior de la [!DNL Target]interfaz de usuario.

![lista de actividades](/help/main/c-activities/assets/activities-list-new.png)

El [!UICONTROL Actividades] proporciona una descripción general de todas las actividades y permite realizar varias acciones:

| Elemento | Descripción |
|--- |--- |
| Carril de navegación izquierdo | Cambie entre las actividades guardadas o activas y las fallidas o [actividades de borrador](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL Mostrar filtros] icono<P>![Mostrar icono de filtros](/help/main/c-activities/assets/show-filters-icon.png) | Acceder a filtros haciendo clic en **[!UICONTROL Mostrar filtros]** cerca de la parte superior de la lista.<P>Para obtener más información, consulte [Aplicar filtros a la lista Actividades](#filters) más abajo. |
| Cuadro de búsqueda | Busque rápidamente una actividad o reduzca el número de actividades que se muestran en la [!UICONTROL Actividad] lista. Puede buscar por [!UICONTROL Nombre], [!UICONTROL URL], o [!UICONTROL ID]. |
| [!UICONTROL Crear actividad] | Cree una actividad. Para obtener más información sobre la creación de los distintos tipos de actividades, consulte: <ul><li>[Crear una prueba A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[Creación de una actividad de asignación automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[Creación de una actividad de segmentación automática](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[Cree una actividad de Automated Personalization](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[Crear una actividad de segmentación de experiencias](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[Crear una prueba multivariable](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[Crear una actividad de Recommendations](/help/main/c-recommendations/recommendations.md)</li></ul>Para obtener más información sobre cada tipo, consulte [Tipos de actividades](#types) más abajo. |
| [!UICONTROL Crear vínculo de vista previa para móviles]<P>![Menú Más acciones](/help/main/c-activities/assets/icon-create-mobile-link.png) | Uso [vínculos de vista previa para móviles](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html?lang=es) para realizar sencillos controles de calidad integrales para actividades de aplicaciones móviles.<P>Haga clic en **Más opciones** (los puntos suspensivos verticales), seleccione el icono **Crear vínculo de vista previa para móviles** y, a continuación, elija las actividades que desea probar en dispositivos móviles. |
| Personalizar tabla<P>![Icono Personalizar tabla](/help/main/c-activities/assets/icon-customize-table.png) | Cambiar qué columnas se muestran en la [!UICONTROL Actividad] haciendo clic en el icono **[!UICONTROL Personalizar tabla]** en la parte superior derecha de la tabla y, a continuación, seleccione o anule la selección de las columnas deseadas.<P>Los cambios se aplican a su cuenta y permanecen activos incluso después de cerrar sesión en [!DNL Target]. |
| Casillas de verificación de operaciones masivas | Realizar operaciones masivas en todas las actividades o en las actividades seleccionadas.<P>Para obtener una lista de las acciones disponibles (en función de los permisos y el estado de la actividad), consulte [Realizar acciones rápidas](#quick-actions) más abajo. |
| [!UICONTROL Tipo] | El tipo de actividad. El [!UICONTROL Tipo] permite identificar rápidamente cada actividad por tipo. <ul><li>AB-M: manual [!UICONTROL Prueba A/B]</li><li>AB-AA: [!UICONTROL Asignación automática]</li><li>AB-AT: [!UICONTROL Segmentación automática]</li><li>AP: [!UICONTROL Automated Personalization]</li><li>XT: [!UICONTROL Segmentación de experiencias]</li><li>MVT: [!UICONTROL Prueba multivariable]</li><li>GRABAR: [!UICONTROL Recommendations]</li></ul>Para obtener más información sobre cada tipo, consulte [Tipos de actividades](#types) más abajo. |
| [!UICONTROL Nombre] | El nombre de la actividad. Haga clic en el nombre de una actividad para mostrar el [!UICONTROL Información general] página. <P>Haga clic en **[!UICONTROL Información rápida]** junto al nombre de cada actividad para ver más información sobre esa actividad en una tarjeta emergente.<p>Haga clic en **[!UICONTROL Más acciones]** (los puntos suspensivos horizontales) junto al nombre de cada actividad para abrir un menú que le permita realizar acciones rápidas en una actividad. Las siguientes acciones están disponibles (según los permisos y el estado de la actividad): [!UICONTROL Editar], [!UICONTROL Activar], [!UICONTROL Desactivar], [!UICONTROL Copiar], [!UICONTROL Eliminar], y [!UICONTROL Archivar]. Para obtener más información sobre cada acción, consulte [Realizar acciones rápidas](#quick-actions) más abajo.<P>Haga clic en el encabezado de la tabla para ordenar la lista alfabéticamente en orden ascendente o descendente por nombre. |
| [!UICONTROL Estado] | Las actividades pueden tener uno de los estados siguientes:<ul><li>**Activa:** la actividad está ejecutándose.</li><li>**Borrador**: se ha iniciado la configuración de la actividad, pero la actividad se encuentra en [modo borrador](/help/main/c-activities/edit-activity.md) y aún no está listo para ejecutarse.</li><li>**Programada:** la actividad está preparada para activarse en la fecha y hora de inicio especificadas.</li><li>**Inactiva:** la actividad se ha pausado o desactivado.</li><li>**Sincronizando**[!DNL Target]: la actividad se ha guardado y se está sincronizando con la red de entrega de </li><li>**Finalizado**: se han alcanzado la fecha y hora de finalización especificadas para la actividad y esta ya no se sirve.</li><li>**Archivada**: se archivó la actividad. Puede activar una actividad archivada para volver a usarla.</li></ul>**Nota:**[!DNL Target] Cuando se realizan determinadas acciones (por ejemplo, activar una actividad fuera de la interfaz de usuario empleando métodos API), los cambios pueden tardar hasta 10 minutos en propagarse a la IU.[!DNL Target] |
| [!UICONTROL Última actualización] | La fecha y hora en que se actualizó la actividad por última vez y quién la actualizó.<P>Haga clic en el encabezado de la tabla para ordenar la lista en orden ascendente o descendente por fecha. |
| [!UICONTROL Prioridad] | La prioridad de la actividad.<P>La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.<P>En función de su [configuración](/help/main/administrating-target/reporting.md), el [!DNL Target] IU y opciones de [!UICONTROL Prioridad] variar. Puede usar la configuración heredada de bajo, medio o alto, o habilitar prioridades específicas de 0 a 999. |
| [!UICONTROL Propiedad] | Muestra la [propiedad](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) de la actividad.<P>Los permisos de usuario de Enterprise son un [Target Premium](/help/main/c-intro/intro.md#premium) función. |
| [!UICONTROL Alza estimada en ingresos] | Muestra el aumento previsto en ingresos si el 100 % de la audiencia ve la experiencia ganadora.<P>Se calcula mediante la fórmula siguiente:<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>El número se redondea con un decimal como máximo si la forma condensada tiene un solo dígito antes del decimal. Por ejemplo: 1,6 millones de dólares, 60 000 dólares, 900 dólares, 8500 dólares, 205 000 dólares<P>En esta columna se muestra &quot;---&quot; para las actividades que no tienen datos suficientes para convocar un concurso ganador o que no tienen una previsión del coste.<P>Para obtener más información, consulte [Alza estimada en ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md). |
| [!UICONTROL Fuente] | Muestra dónde se creó la actividad: [!DNL Adobe Target], [API de Adobe Target](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=es), [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=es), [Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html), o [Adobe Mobile Services](https://developer.adobe.com/client-sdks/documentation/). |
| [!UICONTROL Ubicación] | La dirección URL de la actividad indica dónde se muestra la actividad. Esta columna le ayuda a identificar rápidamente una actividad y determinar si una página en particular ya tiene una actividad en ejecución.<P>Si una actividad se ejecuta en varias direcciones URL, se indica mediante un vínculo cuántas direcciones URL más se están utilizando. Haga clic en el vínculo para ver la lista completa de direcciones URL de esa actividad.<P>Puede buscar según la dirección URL. Utilice la lista desplegable situada junto al cuadro de búsqueda y seleccione [!UICONTROL URL]. |
| Autor | El nombre de la persona que creó la actividad. |
| [!UICONTROL Método de toma de decisiones] | El método de toma de decisiones utilizado en cada actividad: [Del Lado Del Servidor](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=es) o [Lado del cliente](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html). |

## Tipos de actividades.  {#types}

[!DNL Target] incluye varios tipos de actividades. En la tabla siguiente se proporciona una descripción general de cada tipo de actividad con vínculos para ayudarle a obtener más información. Para elegir mejor el mejor tipo de actividad, también hemos creado la [Guía de actividades de Adobe Target](/help/main/c-activities/target-activities-guide.md).

| Tipo de actividad | Descripción |
|--- |--- |
| [Prueba A/B](/help/main/c-activities/t-test-ab/test-ab.md) | Las pruebas A/B comparan dos o más versiones del contenido de su sitio web para ver cuál mejora más las conversiones durante un período de prueba previamente establecido. |
| [Asignación automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL Asignación automática], un tipo de prueba A/B, identifica un ganador entre dos o más experiencias y le reasigna automáticamente a este más tráfico para aumentar las conversiones mientras la prueba sigue ejecutándose y aprendiendo. |
| [Segmentación automática](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | La segmentación automática, un tipo de prueba A/B, utiliza aprendizaje automático avanzado para identificar varias experiencias de alto nivel de rendimiento definidas por expertos en marketing, y ofrece a cada visitante la experiencia más adaptada en función del perfil de cada cliente y del comportamiento de visitantes anteriores con perfiles similares, para personalizar el contenido y dirigir las conversiones. |
| [Prueba multivariable](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] (MVT) compara combinaciones de ofertas de elementos en una página para determinar qué combinación ofrece el mejor rendimiento para una audiencia específica, además de identificar qué elemento tiene el mayor impacto en el éxito de la actividad. |
| [Segmentación de experiencias](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL Segmentación de experiencias] (XT) ofrece contenido a una audiencia específica en función de un conjunto de reglas y criterios definidos por expertos en marketing. |
| [Personalización automatizada](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] (AP) combina ofertas o mensajes, y utiliza aprendizaje automático avanzado para asignar diferentes variaciones a cada visitante en función de su perfil de cliente, personalizar el contenido y dirigir las conversiones. |
| [Recommendations](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | Una recomendación determina el modo en que se sugiere un producto al visitante de un sitio web según las actividades que este realice en el sitio.<P>Por ejemplo, puede que quiera animar a los usuarios que compran una mochila a que consideren la opción de comprar botas y bastones de senderismo. Podría crear una recomendación que muestre artículos que a menudo se compran juntos, empleando el algoritmo “Otras personas que compraron esto también compraron aquello”. O puede que quiera animar a los visitantes a pasar más tiempo en su sitio multimedia mediante la recomendación de vídeos similares al vídeo que están viendo, empleando el algoritmo &quot;Otras personas que han visto esto también vieron aquello&quot;.<P>**NOTA**: También puede incluir recomendaciones dentro de [!UICONTROL Prueba A/B], [!UICONTROL Asignación automática], [!UICONTROL Segmentación automática], y [!UICONTROL Segmentación de experiencias] Actividades de (XT). Para obtener más información, consulte [Recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md). Para esta funcionalidad, es necesaria una [licencia de Target Premium](/help/main/c-intro/intro.md#premium). |

## Aplicar filtros a la lista Actividades {#filters}

Acceder a filtros haciendo clic en **[!UICONTROL Mostrar filtros]** cerca de la parte superior de la lista.

![Opciones de filtro](/help/main/c-activities/assets/show-filters-options.png)

El menú permite filtrar las actividades según los atributos siguientes: |Detalles|de atributo| | — | — | |[!UICONTROL Tipo]|Filtrar por [tipo de actividad](#types).| |[!UICONTROL Estado]|Filtrar por estado de actividad.| |[!UICONTROL Fuente de informes]|Filtrar por fuente de informes.<ul><li>[Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md): muestra las actividades que utilizan [!UICONTROL Analytics for Target] (A4T) como fuente de informes.</li><li>[Target](/help/main/c-reports/reports.md): muestra las actividades que utilizan [!DNL Target] como fuente de informes.</li></ul>| |[!UICONTROL Compositor de experiencias]|Filtro con el que se ha utilizado el compositor de experiencias durante la creación de la actividad:<ul><li>[Visual](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md): Muestra las actividades creadas con el [!UICONTROL Compositor de experiencias visuales] (VEC).</li><li>[Basado en formulario](/help/main/c-experiences/form-experience-composer.md): muestra las actividades creadas con el [!UICONTROL Compositor de experiencias basadas en formularios].</li></ul>| |[!UICONTROL Tipo de métrica]|Filtro por el que [métrica de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md) se eligió durante la creación de la actividad.<ul><li>Conversión</li><li>Ingresos</li><li>Participación</li></ul>| |[!UICONTROL Método de toma de decisiones]|Filtre por el método de toma de decisiones utilizado en cada actividad<ul><li>[Del Lado Del Servidor](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=es): muestra las actividades que utilizan la toma de decisiones del lado del servidor.</li><li>[Lado del cliente](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html): muestra las actividades que utilizan la toma de decisiones del lado del cliente.</li></ul>| |[!UICONTROL Origen de actividad]|Filtre por el origen de actividad utilizado para crear cada actividad.<ul><li>[!DNL Adobe Target]</li><li>[API de Adobe Target](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=es)</li><li>[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=es)</li><li>[Adobe Experience Manager. ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html)</li><li>[Servicios Adobe Mobile](https://developer.adobe.com/client-sdks/documentation/)</li></ul>| |[!UICONTROL Propiedad]|Filtrar por [propiedad](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) en el que se creó la actividad.|

## Realizar acciones rápidas {#quick-actions}

Haga clic en **[!UICONTROL Más acciones]** (los puntos suspensivos horizontales) junto al nombre de cada actividad para abrir un menú que le permita realizar acciones rápidas en una actividad.

![Opciones de acciones rápidas](/help/main/c-activities/assets/quick-actions.png)

Las siguientes acciones están disponibles (según los permisos y el estado de la actividad):

| Acción | Descripción |
| --- | --- |
| [!UICONTROL Editar  ] | Cambia la actividad. Todas las actividades se pueden editar.<P>Para obtener más información sobre las distintas formas de editar actividades, consulte [Editar una actividad o guardarla como borrador](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL Desactivar] | Detiene una actividad activa o programada. Una actividad desactivada se puede reactivar o archivar.<P>Si desactiva o archiva una actividad y luego la reactiva más tarde, un visitante seguirá formando parte de esa actividad después de la reactivación si estaba en ella antes de la desactivación o del archivado. No se atribuirá a esa actividad ninguna métrica de conversión registrada durante el tiempo entre los dos eventos. |
| [!UICONTROL Activar] | Inicie una actividad inactiva o una actividad que esté lista para activarse. |
| [!UICONTROL Archivar] | Enviar la actividad al archivo. De forma predeterminada, las actividades archivadas ya no aparecen en [!UICONTROL Actividades] lista. Si quiere verlas, cambie el filtro de la lista de actividades para que se incluyan. Puede activar una actividad archivada para volver a usarla.<P>Si desactiva o archiva una actividad y luego la reactiva más tarde, un visitante seguirá formando parte de esa actividad después de la reactivación si estaba en esa actividad antes de la desactivación o del archivado. No se atribuirá a esa actividad ninguna métrica de conversión registrada durante el tiempo entre los dos eventos. |
| [!UICONTROL Copiar] | Copia una actividad. Se pueden copiar todas las actividades. Al copiar una actividad, se crea una nueva actividad con el mismo nombre y se anexa el texto “copia”. Por ejemplo, una prueba llamada “Ofertas de navegador” se copiará en “Ofertas de navegador copia”.<P>Las ofertas visuales se copian con la actividad. Puede editar las ofertas de forma segura en la copia sin que la actividad original se vea afectada. La única excepción son las imágenes y las ofertas guardadas en la carpeta Contenido/Recursos. |
| [!UICONTROL Eliminar] | Eliminar un borrador o una actividad.<P>**NOTA**: Las actividades eliminadas no se pueden recuperar. A menos que esté seguro de que nunca necesitará esta actividad, utilice el [!UICONTROL Archivar] acción. A continuación, puede reactivar la actividad si es necesario. |

## Consideraciones

Tenga en cuenta los siguientes detalles sobre [!UICONTROL Actividad] lista:

* Las actividades archivadas y finalizadas no se incluyen en la lista [!UICONTROL Actividades]. Para ver estas actividades, filtre mediante la variable [Icono Filtros](#filters) al principio de la lista.
* Cuando se cree una actividad originalmente en [!DNL Target Classic] se desactiva o elimina, y se elimina de [!DNL Target Standard/Premium]. Las actividades eliminadas creadas originalmente en [!DNL Target Classic] no se envían a la carpeta [!UICONTROL Archivo] de [!DNL Target Standard/Premium]. La funcionalidad de carpeta archivada se aplica solo a las actividades creadas en [!DNL Target Standard/Premium].
* Todos los tipos de actividades que no son [!UICONTROL Personalización automatizada](AP), [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] le dan la opción de usar [!DNL Target] o [!DNL Adobe Analytics] como fuente de datos. [!UICONTROL La personalización automatizada], [!UICONTROL la asignación automática] y [!UICONTROL la segmentación automática] *siempre* utilizan datos de [!DNL Target].
* Las actividades están disponibles en varios canales:

   * Sitios web y móviles
   * Pantallas y dispositivos conectados a Internet, incluidos los quioscos y cajeros automáticos
   * Correo electrónico y otros canales de adquisición o sitios de socios
   * Aplicaciones móviles
   * Cualquier otro sitio donde se pueda publicar contenido etiquetado

## Limitaciones   {#section_049D4684403A4E07B998067EB8E9BE56}

Cada actividad de Target tiene las siguientes limitaciones de contenido:

| Elemento | Límite |
|--- |--- |
| Selectores únicos | 300 Si un selector se repite en otra experiencia, se contabiliza una vez. Pero si se repite en la misma experiencia, se vuelve a contabilizar. |
| Ofertas en cada experiencia | 350 |
| Selectores de seguimiento de clics en métricas | 50 |
| Mboxes en métricas | 50 |
| Audiencias y ubicaciones | 50 combinaciones de audiencias y ubicaciones (mbox) no deben superar el límite de 50. |

La actividad no se puede guardar si supera alguno de estos límites.

El aumento del número de estos elementos en la actividad también aumenta el tiempo que se tarda en sincronizar la actividad [!DNL Target].

Para límites adicionales de la V[!UICONTROL Compositor de experiencias visuales] VEC, consulte [Limitaciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Atributos importados en [!DNL Target] para actividades actualizadas fuera de [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

Si las actividades creadas en [!DNL Target] se actualizan desde fuera de [!DNL Target] (por ejemplo, mediante API), los siguientes atributos de actividad se importan de nuevo en [!DNL Target]: `thirdpartyId`, `startDate`, `endDate`, `status`, `priority`, y `marketingCloudMetadata(remoteModifiedBy)`.

Este trabajo de importación se ejecuta cuando se abre la página de actividades, con un retraso máximo de diez minutos.

## Vídeos de formación {#section_BE80D13A2E81460C885F902010E1AD87}

El siguiente vídeo contiene más información sobre los conceptos mencionados en este artículo.

### Tipos de actividad (9:03)

En este vídeo se describen los tipos de actividades disponibles en [!DNL Target Standard/Premium].

* Describe los tipos de actividades incluidas en [!DNL Adobe Target]
* Seleccionar el tipo de actividad adecuado para lograr los objetivos
* Describir el flujo de trabajo guiado de tres pasos que sirve para todos los tipos de actividad

>[!VIDEO](https://video.tv.adobe.com/v/17386)

