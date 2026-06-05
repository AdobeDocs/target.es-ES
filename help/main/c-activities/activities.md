---
keywords: actividades;actividades;tipos de actividades;editar actividad;acciones de actividades;atributo de actividad;filtro de lista de actividades;limitaciones de actividades;personalizar;personalización;actividades
description: Personalice el contenido y pruebe los diseños de página para audiencias específicas con  [!DNL Adobe Target] actividades.
title: ¿Cómo puedo personalizar el contenido y probar los diseños de página con  [!DNL Target]?
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
TQID: https://experienceleague.adobe.com/q3-Z8r2eEWTISBkZBBJTJ8XarLi-lTa2qsqj961hhEQ
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 2633
ht-degree: 25%

---

# Información general sobre las actividades

Personalice el contenido y pruebe los diseños de página para audiencias específicas con [!DNL Adobe Target] actividades.

Por ejemplo, podría diseñar una actividad que pruebe dos páginas de destino diferentes: una que destaque información sobre calzado de verano de mujer y otra que destaque ropa de verano más general. La actividad determina las condiciones que controlan cuándo se muestra cada una de estas páginas de aterrizaje y las métricas que determinan qué página tiene más éxito. La actividad está configurada para comenzar y finalizar cuando se cumplen condiciones específicas, como entre fechas específicas. O puede elegir comenzar cuando se apruebe la actividad y finalizar cuando se desactive.

Al diseñar una actividad, debería planificarla con mucho cuidado. Determine cuándo se inicia la actividad y cuánto dura. A continuación, enumere las ofertas y asigne un público destinatario a cada una de ellas.

## Lista de actividades {#section_DE8E2DB30D534962A931EF8BB48240F5}

La lista [!UICONTROL Actividades] es la vista predeterminada al abrir [!DNL Target]. Puede crear actividades desde esta página y administrar las actividades existentes.

También puede mostrar la lista [!UICONTROL Actividades] haciendo clic en la ficha [!UICONTROL Actividades] en la parte superior de la interfaz de usuario de [!DNL Target].

La lista [!UICONTROL Actividades] proporciona una descripción general de todas las actividades de su implementación de [!DNL Target] y le permite realizar diversas acciones.

La siguiente tabla le ayuda a comprender varios elementos de la lista [!UICONTROL Actividades] en la interfaz de usuario de [!DNL Target]:

| Elemento | Descripción |
|--- |--- |
| [!UICONTROL Mostrar filtros] icono<P>![Icono Mostrar filtros](/help/main/assets/icons/Filter.svg) | Obtenga acceso a los filtros haciendo clic en el icono **[!UICONTROL Mostrar filtros]** cerca de la parte superior de la lista para filtrar actividades por [!UICONTROL Tipo], [!UICONTROL Estado], [!UICONTROL Source de informes], [!UICONTROL Compositor de experiencias], [!UICONTROL Tipo de métricas], [!UICONTROL Source de decisiones], [!UICONTROL Source de actividades] y [!UICONTROL Propiedades].<P>Los filtros que configure son persistentes en la sesión actual.<P>Para obtener más información, consulte [Aplicar filtros a la lista [!UICONTROL Actividades]](#filters) a continuación. |
| Buscar campos | Encuentre rápidamente una actividad o reduzca el número de actividades mostradas en la lista [!UICONTROL Actividad]. Puede buscar por [!UICONTROL Nombre de actividad], [!UICONTROL URL] o [!UICONTROL ID] mediante la lista desplegable.<P>Las opciones de búsqueda configuradas son persistentes en la sesión actual. |
| [!UICONTROL Crear actividad] | Cree una actividad.<P>Para obtener más información sobre la creación de los distintos tipos de actividades, consulte: <ul><li>[Crear una actividad [!UICONTROL Prueba A/B]](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[Crear una actividad [!UICONTROL de asignación automática]](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[Crear una actividad de [!UICONTROL Segmentación automática]](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[Crear una actividad [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[Crear una actividad de [!UICONTROL Segmentación de experiencias]](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[Crear una actividad](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[Crear una actividad [!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)</li></ul>Para obtener más información sobre cada tipo, consulte [Tipos de actividades](#types) a continuación. |
| [!UICONTROL Crear vínculo de vista previa para móviles]<P>![Menú de acciones más](/help/main/assets/icons/MoreVertical.svg) | Use [vínculos de vista previa para móviles](https://experienceleague.adobe.com/en/docs/target-dev/developer/mobile-apps/target-mobile-preview) para realizar sencillos controles de calidad integrales de las actividades de aplicaciones móviles.<P>Haga clic en el icono **Más opciones**, seleccione **Crear vínculo de vista previa para móviles** y, a continuación, elija las actividades que desea probar en dispositivos móviles. |
| Personalizar tabla<P>![Icono Personalizar tabla](/help/main/assets/icons/ColumnSetting.svg) | Para cambiar qué columnas se muestran en la lista [!UICONTROL Actividad], haga clic en el icono **[!UICONTROL Personalizar tabla]** en la parte superior derecha de la página y, a continuación, seleccione o anule la selección de las columnas que desee.<P>Los cambios se aplicarán a su cuenta y permanecerán activos incluso después de que cierre la sesión de [!DNL Target]. |
| Casillas de verificación de operaciones masivas<P>![Icono de operaciones en lotes](/help/main/assets/icons/Rectangle.svg) | Realizar operaciones masivas en todas las actividades o en las actividades seleccionadas.<P>Para obtener una lista de las acciones disponibles (según sus permisos y el estado de la actividad), consulte [Realizar acciones rápidas](#quick-actions) a continuación. |
| [!UICONTROL Tipo] | El tipo de actividad. La columna [!UICONTROL Tipo] le permite identificar rápidamente cada actividad por tipo. <ul><li>**AB-M**: manual [!UICONTROL Prueba A/B]</li><li>**AB-AA**: [!UICONTROL Asignación automática]</li><li>**AB-AT**: [!UICONTROL Segmentación automática]</li><li>**AP**: [!UICONTROL Automated Personalization]</li><li>**XT**: [!UICONTROL Segmentación de experiencias]</li><li>**MVT**: [!UICONTROL Prueba multivariable]</li><li>**REC**: [!UICONTROL Recommendations]</li></ul>Para obtener más información sobre cada tipo, consulte [Tipos de actividades](#types) a continuación. |
| [!UICONTROL Nombre] | El nombre de la actividad. Haga clic en el icono **[!UICONTROL Información rápida]** (![Icono de información rápida](/help/main/assets/icons/InfoOutline.svg) ) junto a cada nombre de actividad para ver más información sobre esa actividad en una tarjeta emergente, incluidos el [!UICONTROL ID de actividad], [!UICONTROL Objetivo de actividad], [!UICONTROL Ubicación de la actividad], [!UICONTROL Objetivo] y [!UICONTROL Estado].<P>Haga clic en el icono **[!UICONTROL Más acciones]** ( ![Icono de Más acciones](/help/main/assets/icons/MoreSmallList.svg) ) junto a cada nombre de actividad para abrir un menú que le permita realizar acciones rápidas en una actividad. Las siguientes acciones están disponibles (según sus permisos y el estado de la actividad): [!UICONTROL Editar], [!UICONTROL Activar], [!UICONTROL Desactivar], [!UICONTROL Copiar], [!UICONTROL Eliminar] y [!UICONTROL Archivar].<P>Para obtener más información sobre cada acción, consulte [Realizar acciones rápidas](#quick-actions) a continuación.<P>Haga clic en el encabezado de la tabla para ordenar la lista alfabéticamente en orden ascendente o descendente por nombre. |
| [!UICONTROL Estado] | Las actividades pueden tener uno de los estados siguientes:<ul><li>**[!UICONTROL Activo]**: la actividad se está ejecutando.</li><li>**[!UICONTROL Programada]**: la actividad está lista para activarse cuando lleguen la fecha y la hora de inicio especificadas.</li><li>**[!UICONTROL Inactiva]**: la actividad se ha pausado o desactivado.</li><li>**[!UICONTROL Finalizado]**: se han alcanzado la fecha y hora de finalización especificadas para la actividad y esta ya no se sirve.</li><li>**[!UICONTROL Archivada]**: se archivó la actividad. Puede activar una actividad archivada para volver a usarla.</li></ul>**Nota**: Cuando realiza ciertas acciones, como activar una actividad fuera de la interfaz de usuario de [!DNL Target] mediante métodos API, la actualización puede tardar hasta diez minutos en propagarse a la interfaz de usuario de [!DNL Target]. |
| [!UICONTROL Última actualización] | La fecha y hora en que se actualizó la actividad por última vez y quién la actualizó.<P>Haga clic en el encabezado de la tabla para ordenar la lista en orden ascendente o descendente por fecha. |
| [!UICONTROL Prioridad] | La prioridad de la actividad.<P>La prioridad se utiliza si se asignan varias actividades a la misma ubicación con el mismo público. Si se asignan dos o más actividades a una ubicación, se mostrará la actividad con la prioridad más alta.<P>La interfaz de usuario [!DNL Target] y las opciones de [!UICONTROL Prioridad] varían en función de tu [configuración](/help/main/administrating-target/reporting.md). Puede usar la configuración heredada de [!UICONTROL Low], [!UICONTROL Medium] o [!UICONTROL High], o bien habilitar prioridades específicas de 0 a 999.<P>Para obtener más información acerca de la configuración de prioridad, consulte [Prioridad](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC) en *Configuración de actividades* en *Objetivos y configuración*. |
| [!UICONTROL Propiedad] | Muestra la [propiedad](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) de la actividad.<P>Los permisos de usuario de Enterprise son una característica de [Target Premium](/help/main/c-intro/intro.md#premium). |
| [!UICONTROL Alza estimada en los ingresos] | Muestra el aumento previsto en ingresos si el 100 % de la audiencia ve la experiencia ganadora.<P>Se calcula mediante la fórmula siguiente:<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>El número se redondea con un decimal como máximo si la forma condensada tiene un solo dígito antes del decimal. Por ejemplo: 1,6 millones de dólares, 60 000 dólares, 900 dólares, 8500 dólares, 205 000 dólares<P>En esta columna se muestra &quot;---&quot; para las actividades que no tienen datos suficientes para convocar un concurso ganador o que no tienen una previsión del coste.<P>Para obtener más información, consulte [Alza estimada en ingresos](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md). |
| [!UICONTROL Source] | Muestra dónde se creó la actividad: [!DNL Adobe Target], [API de Adobe Target](https://experienceleague.adobe.com/en/docs/target-dev/developer/overview), [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=es), [Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=es) o [Adobe Mobile Services](https://developer.adobe.com/client-sdks/documentation/). |
| [!UICONTROL Autor] | El nombre de la persona que creó la actividad. |
| [!UICONTROL Método de toma de decisiones] | El método de toma de decisiones usado en cada actividad: [Del lado del servidor](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=es) o [Del lado del cliente](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html). |

<!--|[!UICONTROL Location]|The URL for the activity identifies where the activity is displayed. This column helps you quickly identify an activity and determine whether a particular page already has an activity running on it.<P>If an activity runs on multiple URLs, a link shows how many more URLs are used. Click the link to view the complete list of URLs for that activity.<P>You can search based on the URL. Use the drop-down list next to the search box and select [!UICONTROL URL].|-->

## Tipos de actividades. {#types}

[!DNL Target] incluye varios tipos de actividades. En la tabla siguiente se proporciona una descripción general de cada tipo de actividad con vínculos para ayudarle a obtener más información. Para ayudarlo a elegir el mejor tipo de actividad según sus necesidades, use la [Guía de actividades de Adobe Target](/help/main/c-activities/target-activities-guide.md).

| Tipo de actividad | Descripción |
|--- |--- |
| [[!UICONTROL Prueba A/B]](/help/main/c-activities/t-test-ab/test-ab.md) | Las pruebas A/B comparan dos o más versiones del contenido de su sitio web para ver cuál mejora más las conversiones durante un período de prueba previamente establecido. |
| [[!UICONTROL Asignación automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL Asignación automática], un tipo de prueba A/B, identifica un ganador entre dos o más experiencias y le reasigna automáticamente más tráfico para aumentar las conversiones mientras la prueba sigue ejecutándose y aprendiendo. |
| [[!UICONTROL Segmentación automática]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | La segmentación automática, un tipo de prueba A/B, utiliza aprendizaje automático avanzado para identificar varias experiencias de alto nivel de rendimiento definidas por expertos en marketing, y ofrece a cada visitante la experiencia más adaptada en función del perfil de cada cliente y del comportamiento de visitantes anteriores con perfiles similares, para personalizar el contenido y dirigir las conversiones. |
| [[!UICONTROL Prueba multivariable]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | [!UICONTROL Multivariate Testing] (MVT) compara combinaciones de ofertas de elementos en una página para determinar qué combinación ofrece el mejor rendimiento para una audiencia específica, además de identificar qué elemento tiene el mayor impacto en el éxito de la actividad. |
| [[!UICONTROL Segmentación de experiencias]](/help/main/c-activities/t-experience-target/experience-target.md) | [!UICONTROL Segmentación de experiencias] (XT) ofrece contenido a una audiencia específica en función de un conjunto de reglas y criterios definidos por expertos en marketing. |
| [[!UICONTROL Personalización automatizada]](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | [!UICONTROL Automated Personalization] (AP) combina ofertas o mensajes, y usa aprendizaje automático avanzado para asignar diferentes variaciones a cada visitante en función de su perfil de cliente, para personalizar el contenido y dirigir las conversiones. |
| [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | Una recomendación determina el modo en que se sugiere un producto al visitante de un sitio web según las actividades que este realice en el sitio.<P>Por ejemplo, puede que quiera animar a los usuarios que compran una mochila a que consideren la opción de comprar botas y bastones de senderismo. Podría crear una recomendación que muestre artículos que a menudo se compran juntos, empleando el algoritmo “Otras personas que compraron esto también compraron aquello”. O puede que quiera animar a los visitantes a pasar más tiempo en su sitio multimedia mediante la recomendación de vídeos similares al vídeo que están viendo, empleando el algoritmo &quot;Otras personas que han visto esto también vieron aquello&quot;.<P>**NOTA**: También puede incluir recomendaciones dentro de las actividades de [!UICONTROL Prueba A/B], [!UICONTROL Asignación automática], [!UICONTROL Segmentación automática] y [!UICONTROL Segmentación de experiencias] (XT). Para obtener más información, consulte [Recomendaciones como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md). Para esta funcionalidad, es necesaria una [licencia de Target Premium](/help/main/c-intro/intro.md#premium). |

## Aplicar filtros a la lista Actividades {#filters}

Para acceder a los filtros, haga clic en el icono **[!UICONTROL Mostrar filtros]** ( ![Mostrar filtros](/help/main/assets/icons/Filter.svg) ), cerca de la parte superior de la lista.

El menú permite filtrar las actividades según los atributos siguientes:

| Atributo | Detalles |
| --- | --- |
| [!UICONTROL Tipo] | Filtrar por [tipo de actividad](#types). |
| [!UICONTROL Estado] | Filtre por estado de actividad.<ul><li>**[!UICONTROL Activo]**: la actividad se está ejecutando.</li><li>**[!UICONTROL Programada]**: la actividad está lista para activarse cuando lleguen la fecha y la hora de inicio especificadas.</li><li>**[!UICONTROL Inactiva]**: la actividad se ha pausado o desactivado.</li><li>**[!UICONTROL Finalizado]**: se han alcanzado la fecha y hora de finalización especificadas para la actividad y esta ya no se sirve.</li><li>**[!UICONTROL Archivada]**: se archivó la actividad. Puede activar una actividad archivada para volver a usarla.</li></ul>Consulte la nota debajo de esta tabla para obtener más información sobre los estados obsoletos [!UICONTROL Guardar como borrador] y [!UICONTROL Sincronizando]. |
| [!UICONTROL Source de informes] | Filtrar por fuente de informes.<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md): mostrar actividades que usan [!UICONTROL Analytics for Target] (A4T) como fuente de informes.</li><li>[[!DNL Target]](/help/main/c-reports/reports.md): mostrar actividades que usan [!DNL Target] como origen de informes.</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md): mostrar actividades que usan [!DNL Adobe Customer Analytics] como origen de informes.</li></ul> |
| [!UICONTROL Compositor de experiencias] | Filtre por qué compositor de experiencias se utilizó durante la creación de la actividad:<ul><li>[Visual](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md): muestra las actividades que se crearon con el [!UICONTROL Compositor de experiencias visuales] (VEC).</li><li>[Basado en formularios](/help/main/c-experiences/form-experience-composer.md): muestra las actividades creadas con [!UICONTROL Compositor de experiencias basadas en formularios].</li></ul> |
| [!UICONTROL Tipo de métrica] | Filtro por el cual se eligió [métrica de éxito](/help/main/c-activities/r-success-metrics/success-metrics.md) durante la creación de la actividad.<ul><li>[!UICONTROL Conversión]</li><li>[!UICONTROL Ingresos]</li><li>[!UICONTROL Participación]</li><li>[!UICONTROL Usar una métrica de Analytics]</lI></ul> |
| [!UICONTROL Método de toma de decisiones] | Filtre por el método de toma de decisiones utilizado en cada actividad.<ul><li>[Lado del servidor](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=es): muestra las actividades que usan la toma de decisiones del lado del servidor.</li><li>[Lado del cliente](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html): muestra las actividades que usan la toma de decisiones del lado del cliente.</li></ul> |
| [!UICONTROL Activity Source] | Filtre por el origen de actividad utilizado para crear cada actividad.<ul><li>[!DNL Adobe Target]</li><li>[[!DNL Adobe Target] API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=es)</li><li>[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/experience-platform.html?lang=es)</li><li>[[!DNL Adobe Experience Manager]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=es)</li><li>[[!DNL Adobe Mobile Services]](https://developer.adobe.com/client-sdks/home/)</li></ul> |
| [!UICONTROL Propiedad] | Filtre por la [propiedad](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) en la que se creó la actividad. |


>[!NOTE]
>
>**Actualización de los estados de las actividades en la IU actualizada**: con las últimas actualizaciones de la interfaz de usuario, los estados [!UICONTROL Guardar como borrador] y [!UICONTROL Sincronizando] ya no están disponibles. Esto se debe a que todas las actividades de creación y edición ahora se realizan directamente en el sistema de entrega back-end [!DNL Target] mediante la capa de GraphQL, lo que garantiza un proceso más ágil y eficiente.
>
>Anteriormente, las actividades se guardaban primero en el front-end [!DNL Target] y luego se sincronizaban con el sistema de entrega back-end [!DNL Target], que requería esos estados intermedios. Como ya no es así, se han eliminado esos estados.
>
>[!DNL Adobe] entiende que algunos clientes han expresado interés en la función [!UICONTROL Guardar como borrador]. Aunque agradecemos estos comentarios, esta funcionalidad no es compatible actualmente.

## Realizar acciones rápidas {#quick-actions}

Haga clic en el icono **[!UICONTROL Más acciones]** ( ![Menú de más acciones](/help/main/assets/icons/MoreVertical.svg) ) junto a cada nombre de actividad para abrir un menú que le permita realizar acciones rápidas en una actividad.

Las siguientes acciones están disponibles (según los permisos y el estado de la actividad):

| Acción | Descripción |
| --- | --- |
| [!UICONTROL Editar] | Cambia la actividad. Todas las actividades se pueden editar.<P>Para obtener más información sobre las distintas formas de editar actividades, consulte [Editar una actividad o guardarla como borrador](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL Desactivar] | Detiene una actividad activa o programada. Una actividad desactivada se puede reactivar o archivar.<P>Si desactiva o archiva una actividad y luego la reactiva más tarde, un visitante seguirá formando parte de esa actividad después de la reactivación si estaba en ella antes de la desactivación o del archivado. No se atribuirá a esa actividad ninguna métrica de conversión registrada durante el tiempo entre los dos eventos. |
| [!UICONTROL Activar] | Inicie una actividad inactiva o una actividad que esté lista para activarse. |
| [!UICONTROL Archivar] | Enviar la actividad al archivo. De manera predeterminada, las actividades archivadas ya no aparecen en la lista [!UICONTROL Actividades]. Cambie el filtro de la lista [!UICONTROL Actividades] para incluir actividades archivadas y poder verlas. Puede activar una actividad archivada para volver a usarla.<P>Si desactiva o archiva una actividad y luego la reactiva más tarde, un visitante seguirá formando parte de esa actividad después de la reactivación si estaba en esa actividad antes de la desactivación o del archivado. No se atribuirá a esa actividad ninguna métrica de conversión registrada durante el tiempo entre los dos eventos. |
| [!UICONTROL Copiar] | Copia una actividad. Se pueden copiar todas las actividades. Al copiar una actividad, se crea una nueva actividad con el mismo nombre y se anexa el texto “copia”. Por ejemplo, una prueba llamada “Ofertas de navegador” se copiará en “Ofertas de navegador copia”.<P>Las ofertas visuales se copian con la actividad. Puede editar las ofertas de forma segura en la copia sin que la actividad original se vea afectada. La única excepción son las imágenes y las ofertas guardadas en la carpeta Contenido/Recursos. |
| [!UICONTROL Eliminar] | Eliminar un borrador o una actividad.<P>**NOTA**: las actividades eliminadas no se pueden recuperar. A menos que esté seguro de que nunca necesitará esta actividad, use la acción [!UICONTROL Archivar]. A continuación, puede reactivar la actividad si es necesario. |

## Consideraciones

Tenga en cuenta los siguientes detalles sobre la lista [!UICONTROL Actividad]:

* Las actividades [!UICONTROL Archived] y [!UICONTROL Ended] no aparecen en la lista [!UICONTROL Activities]. Para ver estas actividades, filtra con el [icono Filtros](#filters) ( ![Icono Mostrar filtros](/help/main/assets/icons/Filter.svg) ) en la parte superior de la lista.
* Cuando una actividad creada originalmente en [!DNL Target Classic] se desactiva o elimina, se elimina de [!DNL Target Standard/Premium]. Las actividades eliminadas creadas originalmente en [!DNL Target Classic] no se envían a la carpeta [!UICONTROL Archivo] en [!DNL Target Standard/Premium]. La funcionalidad de carpeta archivada se aplica solo a las actividades creadas en [!DNL Target Standard/Premium].
* Todos los tipos de actividades que no sean [!UICONTROL Automated Personalization] (AP), [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] le dan la opción de usar [!DNL Target] o [!DNL Adobe Analytics] como fuente de datos. [!UICONTROL Automated Personalization], [!UICONTROL Asignación automática] y [!UICONTROL Segmentación automática] *siempre* usan datos de [!DNL Target].
* Las actividades están disponibles en varios canales:

   * Sitios web y móviles
   * Pantallas y dispositivos conectados a Internet, incluidos los quioscos y cajeros automáticos
   * Correo electrónico y otros canales de adquisición o sitios de socios
   * Aplicaciones móviles
   * Cualquier otro sitio donde se pueda publicar contenido etiquetado

## Limitaciones {#section_049D4684403A4E07B998067EB8E9BE56}

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

Para obtener límites adicionales de [!UICONTROL Compositor de experiencias visuales] (VEC), consulte [Limitaciones del Compositor de experiencias visuales](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Atributos importados en [!DNL Target] para actividades actualizadas fuera de [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

Si las actividades creadas en [!DNL Target] se actualizan desde fuera de [!DNL Target] (por ejemplo, mediante API), los siguientes atributos de actividad se importan de nuevo en [!DNL Target]: `thirdpartyId`, `startDate`, `endDate`, `status`, `priority` y `marketingCloudMetadata(remoteModifiedBy)`.

Este trabajo de importación se ejecuta cuando se abre la lista [!UICONTROL Actividades], con un retraso máximo de diez minutos.

