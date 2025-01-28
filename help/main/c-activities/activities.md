---
keywords: actividades;actividades;tipos de actividades;editar actividad;acciones de actividades;atributo de actividad;filtro de lista de actividades;limitaciones de actividades;personalizar;personalización;actividades
description: Personalice el contenido y pruebe los diseños de página para audiencias específicas con  [!DNL Adobe Target] actividades.
title: ¿Cómo puedo personalizar el contenido y probar los diseños de página con  [!DNL Target]?
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: d92c09b905b10c6d0175a5de137d573f8cd475d7
workflow-type: tm+mt
source-wordcount: '2234'
ht-degree: 26%

---

# Información general sobre las actividades

Personalice el contenido y pruebe los diseños de página para audiencias específicas con [!DNL Adobe Target] actividades.

Por ejemplo, podría diseñar una actividad que pruebe dos páginas de aterrizaje diferentes: una que destaque información sobre calzado de verano de mujer y otra que destaque ropa de verano más general. La actividad determina las condiciones que controlan cuándo se muestra cada una de estas páginas de aterrizaje y las métricas que determinan qué página tiene más éxito. La actividad está configurada para comenzar y finalizar cuando se cumplen condiciones específicas, como entre fechas específicas. O puede elegir comenzar cuando se apruebe la actividad y finalizar cuando se desactive.

Al diseñar una actividad, debería planificarla con mucho cuidado. Determine cuándo se inicia la actividad y cuánto dura. A continuación, enumere las ofertas y asigne una audiencia segmentada a cada una de ellas.

## Lista de actividades {#section_DE8E2DB30D534962A931EF8BB48240F5}

La lista [!UICONTROL Activities] es la vista predeterminada al abrir [!DNL Target]. Puede crear actividades desde esta página y administrar las actividades existentes.

También puede mostrar la lista [!UICONTROL Activities] si hace clic en la ficha [!UICONTROL Activities] en la parte superior de la interfaz de usuario de [!DNL Target].

![lista de actividades](/help/main/c-activities/assets/activities-list-new.png)

La lista [!UICONTROL Activities] proporciona una descripción general de todas las actividades de su implementación de [!DNL Target] y le permite realizar diversas acciones.

La siguiente tabla le ayuda a comprender varios elementos de la lista [!UICONTROL Activities] en la interfaz de usuario de [!DNL Target]:

| Elemento | Descripción |
|--- |--- |
| Carril de navegación izquierdo | Cambie entre las actividades guardadas o activas y las [actividades de borrador](/help/main/c-activities/edit-activity.md) con errores. |
| Icono [!UICONTROL Show filters]<P>![Icono Mostrar filtros](/help/main/assets/icons/Filter.svg) | Obtenga acceso a los filtros haciendo clic en el icono **[!UICONTROL Show Filters]** cerca de la parte superior de la lista para filtrar actividades por [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], [!UICONTROL Decisioning Source], [!UICONTROL Activity Source] y [!UICONTROL Properties].<P>Para obtener más información, consulte [Aplicar filtros a la lista [!UICONTROL Activities]](#filters) a continuación. |
| Campos de búsqueda | Busque rápidamente una actividad o reduzca el número de actividades mostradas en la lista [!UICONTROL Activity]. Puede buscar por [!UICONTROL Activity Name], [!UICONTROL URL] o [!UICONTROL ID] mediante la lista desplegable. |
| [!UICONTROL Create Activity] | Cree una actividad.<P>Para obtener más información sobre la creación de los distintos tipos de actividades, consulte: <ul><li>[Crear una actividad [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[Crear una actividad [!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[Crear una actividad [!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[Crear una actividad [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[Crear una actividad [!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[Crear una actividad](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[Crear una actividad [!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)</li></ul>Para obtener más información sobre cada tipo, consulte [Tipos de actividades](#types) a continuación. |
| [!UICONTROL Create mobile preview link]<P>![Menú de acciones más](/help/main/assets/icons/MoreVertical.svg) | Use [vínculos de vista previa para móviles](https://experienceleague.adobe.com/en/docs/target-dev/developer/mobile-apps/target-mobile-preview) para realizar sencillos controles de calidad integrales de las actividades de aplicaciones móviles.<P>Haga clic en el icono **Más opciones**, seleccione **Crear vínculo de vista previa para móviles** y, a continuación, elija las actividades que desea probar en dispositivos móviles. |
| Personalizar tabla<P>![Icono Personalizar tabla](/help/main/assets/icons/ColumnSetting.svg) | Para cambiar qué columnas se muestran en la lista [!UICONTROL Activity], haga clic en el icono **[!UICONTROL Customize Table]** en la parte superior derecha de la página y seleccione o anule la selección de las columnas que desee.<P>Los cambios se aplicarán a su cuenta y permanecerán activos incluso después de que cierre la sesión de [!DNL Target]. |
| Casillas de verificación de operaciones masivas<P>![Icono de operaciones en lotes](/help/main/assets/icons/Rectangle.svg) | Realizar operaciones masivas en todas las actividades o en las actividades seleccionadas.<P>Para obtener una lista de las acciones disponibles (según sus permisos y el estado de la actividad), consulte [Realizar acciones rápidas](#quick-actions) a continuación. |
| [!UICONTROL Type] | El tipo de actividad. La columna [!UICONTROL Type] le permite identificar rápidamente cada actividad por tipo. <ul><li>**AB-M**: manual [!UICONTROL A/B Test]</li><li>**AB-AA**: [!UICONTROL Auto-Allocate]</li><li>**AB-AT**: [!UICONTROL Auto-Target]</li><li>**AP**: [!UICONTROL Automated Personalization]</li><li>**XT**: [!UICONTROL Experience Targeting]</li><li>**MVT**: [!UICONTROL Multivariate Test]</li><li>**REC**: [!UICONTROL Recommendations]</li></ul>Para obtener más información sobre cada tipo, consulte [Tipos de actividades](#types) a continuación. |
| [!UICONTROL Name] | Nombre de la actividad. Haga clic en el icono **[!UICONTROL Quick Info]** ( ![icono de información rápida](/help/main/assets/icons/InfoOutline.svg) ) junto al nombre de cada actividad para ver más información acerca de esa actividad en una tarjeta emergente, que incluye [!UICONTROL Activity ID], [!UICONTROL Activity Objective], [!UICONTROL Activity Location], [!UICONTROL Goal] y [!UICONTROL Status].<P>Haga clic en el icono **[!UICONTROL More actions]** ( ![icono Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) junto al nombre de cada actividad para abrir un menú que le permita realizar acciones rápidas en una actividad. Las siguientes acciones están disponibles (según los permisos y el estado de la actividad): [!UICONTROL Edit], [!UICONTROL Activate], [!UICONTROL Deactivate], [!UICONTROL Copy], [!UICONTROL Delete] y [!UICONTROL Archive].<P>Para obtener más información sobre cada acción, consulte [Realizar acciones rápidas](#quick-actions) a continuación.<P>Haga clic en el encabezado de la tabla para ordenar la lista alfabéticamente en orden ascendente o descendente por nombre. |
| [!UICONTROL Status] | Las actividades pueden tener uno de los estados siguientes:<ul><li>**[!UICONTROL Live]**: la actividad se está ejecutando.</li><li>**[!UICONTROL Draft]**: se ha iniciado la configuración de la actividad, pero está en [modo de borrador](/help/main/c-activities/edit-activity.md) y aún no está lista para ejecutarse.</li><li>**[!UICONTROL Scheduled]**: la actividad está lista para activarse en la fecha y hora de inicio especificadas.</li><li>**[!UICONTROL Inactive]**: la actividad se ha pausado o desactivado.</li><li>**[!UICONTROL Syncing]**: la actividad se ha guardado y se está sincronizando con la red de entrega [!DNL Target].</li><li>**[!UICONTROL Ended]**: se han alcanzado la fecha y hora de finalización especificadas para la actividad y esta ya no se sirve.</li><li>**[!UICONTROL Archived]**: se archivó la actividad. Puede activar una actividad archivada para volver a usarla.</li></ul>**Nota**: Cuando realiza ciertas acciones, como activar una actividad fuera de la interfaz de usuario de [!DNL Target] mediante métodos API, la actualización puede tardar hasta diez minutos en propagarse a la interfaz de usuario de [!DNL Target]. |
| [!UICONTROL Last Updated] | La fecha y hora en que se actualizó la actividad por última vez y quién la actualizó.<P>Haga clic en el encabezado de la tabla para ordenar la lista en orden ascendente o descendente por fecha. |
| [!UICONTROL Priority] | La prioridad de la actividad.<P>La prioridad se utiliza si se asignan varias actividades a la misma ubicación con la misma audiencia. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.<P>La interfaz de usuario de [!DNL Target] y las opciones de [!UICONTROL Priority] varían en función de la configuración [1. ](/help/main/administrating-target/reporting.md) Puede usar la configuración heredada de [!UICONTROL Low], [!UICONTROL Medium] o [!UICONTROL High], o bien habilitar prioridades específicas de 0 a 999.<P>Para obtener más información acerca de la configuración de prioridad, consulte [Prioridad](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC) en *Configuración de actividades* en *Objetivos y configuración*. |
| [!UICONTROL Property] | Muestra la [propiedad](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) de la actividad.<P>Los permisos de usuario de Enterprise son una característica de [Target Premium](/help/main/c-intro/intro.md#premium). |
| [!UICONTROL Estimated Lift in Revenue] | Muestra el aumento previsto en ingresos si el 100 % de la audiencia ve la experiencia ganadora.<P>Se calcula mediante la fórmula siguiente:<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>El número se redondea con un decimal como máximo si la forma condensada tiene un solo dígito antes del decimal. Por ejemplo: 1,6 millones de dólares, 60 000 dólares, 900 dólares, 8500 dólares, 205 000 dólares<P>En esta columna se muestra &quot;---&quot; para las actividades que no tienen datos suficientes para convocar un concurso ganador o que no tienen una previsión del coste.<P>Para obtener más información, consulte [Alza estimada en ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md). |
| [!UICONTROL Source] | Muestra dónde se creó la actividad: [!DNL Adobe Target], [API de Adobe Target](https://experienceleague.adobe.com/en/docs/target-dev/developer/overview), [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=es), [Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=es) o [Adobe Mobile Services](https://developer.adobe.com/client-sdks/documentation/). |
| [!UICONTROL Author] | El nombre de la persona que creó la actividad. |
| [!UICONTROL Decisioning Method] | El método de toma de decisiones usado en cada actividad: [Del lado del servidor](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=es) o [Del lado del cliente](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html). |

<!--|[!UICONTROL Location]|The URL for the activity identifies where the activity is displayed. This column helps you quickly identify an activity and determine whether a particular page already has an activity running on it.<P>If an activity runs on multiple URLs, a link shows how many more URLs are used. Click the link to view the complete list of URLs for that activity.<P>You can search based on the URL. Use the drop-down list next to the search box and select [!UICONTROL URL].|-->

## Tipos de actividades.  {#types}

[!DNL Target] incluye varios tipos de actividades. En la tabla siguiente se proporciona una descripción general de cada tipo de actividad con vínculos para ayudarle a obtener más información. Para ayudarlo a elegir el mejor tipo de actividad según sus necesidades, use la [Guía de actividades de Adobe Target](/help/main/c-activities/target-activities-guide.md).

| Tipo de actividad | Descripción |
|--- |--- |
| [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md) | Las pruebas A/B comparan dos o más versiones del contenido de su sitio web para ver cuál mejora más las conversiones durante un período de prueba previamente establecido. |
| [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL Auto-Allocate], un tipo de prueba A/B, identifica un ganador entre dos o más experiencias y le reasigna automáticamente más tráfico para aumentar las conversiones mientras la prueba sigue ejecutándose y aprendiendo. |
| [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | La segmentación automática, un tipo de prueba A/B, utiliza aprendizaje automático avanzado para identificar varias experiencias de alto nivel de rendimiento definidas por expertos en marketing, y ofrece a cada visitante la experiencia más adaptada en función del perfil de cada cliente y del comportamiento de visitantes anteriores con perfiles similares, para personalizar el contenido y dirigir las conversiones. |
| [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] (MVT) compara combinaciones de ofertas de elementos en una página para determinar qué combinación ofrece el mejor rendimiento para una audiencia específica, además de identificar qué elemento tiene el mayor impacto en el éxito de la actividad. |
| [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL Experience Targeting] (XT) ofrece contenido a una audiencia específica en función de un conjunto de reglas y criterios definidos por expertos en marketing. |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] (AP) combina ofertas o mensajes, y utiliza aprendizaje automático avanzado para asignar diferentes variaciones a cada visitante en función de su perfil de cliente, para personalizar el contenido y dirigir las conversiones. |
| [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | Una recomendación determina el modo en que se sugiere un producto al visitante de un sitio web según las actividades que este realice en el sitio.<P>Por ejemplo, puede que quiera animar a los usuarios que compran una mochila a que consideren la opción de comprar botas y bastones de senderismo. Podría crear una recomendación que muestre artículos que a menudo se compran juntos, empleando el algoritmo “Otras personas que compraron esto también compraron aquello”. O puede que quiera animar a los visitantes a pasar más tiempo en su sitio multimedia mediante la recomendación de vídeos similares al vídeo que están viendo, empleando el algoritmo &quot;Otras personas que han visto esto también vieron aquello&quot;.<P>**NOTA**: También puede incluir recomendaciones dentro de las actividades [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] y [!UICONTROL Experience Targeting] (XT). Para obtener más información, consulte [Recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md). Para esta funcionalidad, es necesaria una [licencia de Target Premium](/help/main/c-intro/intro.md#premium). |

## Aplicar filtros a la lista Actividades {#filters}

Para obtener acceso a los filtros, haga clic en el icono **[!UICONTROL Show Filters]** ( ![Mostrar filtros](/help/main/assets/icons/Filter.svg) ), cerca de la parte superior de la lista.

El menú permite filtrar las actividades según los atributos siguientes:

| Atributo | Detalles |
| --- | --- |
| [!UICONTROL Type] | Filtrar por [tipo de actividad](#types). |
| [!UICONTROL Status] | Filtre por estado de actividad.<ul><li>**[!UICONTROL Live]**: la actividad se está ejecutando.</li><li>**[!UICONTROL Draft]**: se ha iniciado la configuración de la actividad, pero está en [modo de borrador](/help/main/c-activities/edit-activity.md) y aún no está lista para ejecutarse.</li><li>**[!UICONTROL Scheduled]**: la actividad está lista para activarse en la fecha y hora de inicio especificadas.</li><li>**[!UICONTROL Inactive]**: la actividad se ha pausado o desactivado.</li><li>**[!UICONTROL Syncing]**: la actividad se ha guardado y se está sincronizando con la red de entrega [!DNL Target].</li><li>**[!UICONTROL Ended]**: se han alcanzado la fecha y hora de finalización especificadas para la actividad y esta ya no se sirve.</li><li>**[!UICONTROL Archived]**: se archivó la actividad. Puede activar una actividad archivada para volver a usarla.</li></ul> |
| [!UICONTROL Reporting Source] | Filtrar por fuente de informes.<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md): mostrar actividades que usan [!UICONTROL Analytics for Target] (A4T) como origen de informes.</li><li>[[!DNL Target]](/help/main/c-reports/reports.md): mostrar actividades que usan [!DNL Target] como origen de informes.</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md): mostrar actividades que usan [!DNL Adobe Customer Analytics] como origen de informes.</li></ul> |
| [!UICONTROL Experience Composer] | Filtre por qué compositor de experiencias se utilizó durante la creación de la actividad:<ul><li>[Visual](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md): muestra las actividades creadas con el [!UICONTROL Visual Experience Composer] (VEC).</li><li>[Basado en formularios](/help/main/c-experiences/form-experience-composer.md): muestra las actividades creadas con [!UICONTROL Form-Based Experience Composer].</li></ul> |
| [!UICONTROL Metrics Type] | Filtro por el cual se eligió [métrica de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md) durante la creación de la actividad.<ul><li>[!UICONTROL Conversion]</li><li>[!UICONTROL Revenue]</li><li>[!UICONTROL Engagement]</li><li>[!UICONTROL Use an Analytics metric]</lI></ul> |
| [!UICONTROL Decisioning Method] | Filtre por el método de toma de decisiones utilizado en cada actividad.<ul><li>[Lado del servidor](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=es): muestra las actividades que usan la toma de decisiones del lado del servidor.</li><li>[Lado del cliente](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html): muestra las actividades que usan la toma de decisiones del lado del cliente.</li></ul> |
| [!UICONTROL Activity Source] | Filtre por el origen de actividad utilizado para crear cada actividad.<ul><li>[!DNL Adobe Target]</li><li>[[!DNL Adobe Target] API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=es)</li><li>[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/experience-platform.html?lang=es)</li><li>[[!DNL Adobe Experience Manager]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=es)</li><li>[[!DNL Adobe Mobile Services]](https://developer.adobe.com/client-sdks/home/)</li></ul> |
| [!UICONTROL Property] | Filtre por la [propiedad](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) en la que se creó la actividad. |

## Realizar acciones rápidas {#quick-actions}

Haga clic en el icono **[!UICONTROL More actions]** ( ![Menú de acciones más](/help/main/assets/icons/MoreVertical.svg) ) junto al nombre de cada actividad para abrir un menú que le permita realizar acciones rápidas en una actividad.

Las siguientes acciones están disponibles (según los permisos y el estado de la actividad):

| Acción | Descripción |
| --- | --- |
| [!UICONTROL Edit] | Cambia la actividad. Todas las actividades se pueden editar.<P>Para obtener más información sobre las distintas formas de editar actividades, consulte [Editar una actividad o guardarla como borrador](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL Deactivate] | Detiene una actividad activa o programada. Una actividad desactivada se puede reactivar o archivar.<P>Si desactiva o archiva una actividad y luego la reactiva más tarde, un visitante seguirá formando parte de esa actividad después de la reactivación si estaba en ella antes de la desactivación o del archivado. No se atribuirá a esa actividad ninguna métrica de conversión registrada durante el tiempo entre los dos eventos. |
| [!UICONTROL Activate] | Inicie una actividad inactiva o una actividad que esté lista para activarse. |
| [!UICONTROL Archive] | Enviar la actividad al archivo. De manera predeterminada, las actividades archivadas ya no aparecen en la lista [!UICONTROL Activities]. Cambie el filtro de la lista [!UICONTROL Activities] para incluir actividades archivadas y verlas. Puede activar una actividad archivada para volver a usarla.<P>Si desactiva o archiva una actividad y luego la reactiva más tarde, un visitante seguirá formando parte de esa actividad después de la reactivación si estaba en esa actividad antes de la desactivación o del archivado. No se atribuirá a esa actividad ninguna métrica de conversión registrada durante el tiempo entre los dos eventos. |
| [!UICONTROL Copy] | Copia una actividad. Se pueden copiar todas las actividades. Al copiar una actividad, se crea una nueva actividad con el mismo nombre y se anexa el texto “copia”. Por ejemplo, una prueba llamada “Ofertas de navegador” se copiará en “Ofertas de navegador copia”.<P>Las ofertas visuales se copian con la actividad. Puede editar las ofertas de forma segura en la copia sin que la actividad original se vea afectada. La única excepción son las imágenes y las ofertas guardadas en la carpeta Contenido/Recursos. |
| [!UICONTROL Delete] | Eliminar un borrador o una actividad.<P>**NOTA**: las actividades eliminadas no se pueden recuperar. A menos que esté seguro de que nunca necesitará esta actividad, use la acción [!UICONTROL Archive]. A continuación, puede reactivar la actividad si es necesario. |

## Consideraciones

Tenga en cuenta los siguientes detalles sobre la lista [!UICONTROL Activity]:

* Las actividades [!UICONTROL Archived] y [!UICONTROL Ended] no aparecen en la lista [!UICONTROL Activities]. Para ver estas actividades, filtra con el [icono Filtros](#filters) ( ![Icono Mostrar filtros](/help/main/assets/icons/Filter.svg) ) en la parte superior de la lista.
* Cuando una actividad creada originalmente en [!DNL Target Classic] se desactiva o elimina, se elimina de [!DNL Target Standard/Premium]. Las actividades eliminadas creadas originalmente en [!DNL Target Classic] no se envían a la carpeta [!UICONTROL Archive] en [!DNL Target Standard/Premium]. La funcionalidad de carpeta archivada se aplica solo a las actividades creadas en [!DNL Target Standard/Premium].
* Todos los tipos de actividades que no sean [!UICONTROL Automated Personalization] (AP), [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target] le dan la opción de usar [!DNL Target] o [!DNL Adobe Analytics] como origen de datos. [!UICONTROL Automated Personalization], [!UICONTROL Auto-Allocate] y [!UICONTROL Auto-Target] *siempre* usan datos de [!DNL Target].
* Las actividades están disponibles en varios canales:

   * Sitios web y móviles
   * Pantallas y dispositivos conectados a Internet, incluidos los quioscos y cajeros automáticos
   * Correo electrónico y otros canales de adquisición o sitios de socios
   * Aplicaciones móviles
   * Cualquier otro sitio donde se pueda publicar contenido etiquetado

## Limitaciones   {#section_049D4684403A4E07B998067EB8E9BE56}

Cada actividad [!DNL Target] tiene las siguientes limitaciones de contenido:

| Elemento | Límite |
|--- |--- |
| Selectores únicos | 300 si un selector se repite en otra experiencia, se cuenta una vez. Pero si se repite en la misma experiencia, se vuelve a contabilizar. |
| Ofertas en cada experiencia | 350 |
| Selectores de seguimiento de clics en métricas | 50 |
| Mboxes en métricas | 50 |
| Audiencias y ubicaciones | 50 combinaciones de audiencias y ubicaciones (mbox) no deben superar el límite de 50. |

La actividad no se puede guardar si supera alguno de estos límites.

Si aumenta el número de estos elementos en su actividad también aumentará el tiempo que se tarda en sincronizar la actividad en [!DNL Target].

Para ver los límites adicionales de [!UICONTROL Visual Experience Composer] (VEC), consulte [Limitaciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Atributos importados en [!DNL Target] para actividades actualizadas fuera de [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

Si las actividades creadas en [!DNL Target] se actualizan desde fuera de [!DNL Target] (por ejemplo, mediante API), los siguientes atributos de actividad se importan de nuevo en [!DNL Target]: `thirdpartyId`, `startDate`, `endDate`, `status`, `priority` y `marketingCloudMetadata(remoteModifiedBy)`.

Este trabajo de importación se ejecuta cuando se abre la lista [!UICONTROL Activities], con un retraso máximo de diez minutos.

