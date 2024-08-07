---
keywords: servidor de seguimiento de analytics;A4T;segmentos de analytics;grupos de informes;datos incorrectos;huérfanos;sdid;VisitorAPI.js;mboxMCSDID;fantasma;sin especificar
description: Explorar los problemas comunes que los clientes han encontrado al usar Analytics for  [!DNL Target]  (A4T).
title: ¿Cómo puedo solucionar problemas de integración de Analytics y  [!DNL Target]  (A4T)
feature: Analytics for Target (A4T)
exl-id: 7d155cbe-e799-43b5-afc2-1aea43f432ba
source-git-commit: 0be54d82e25eb919102f6098c1b1db76ab291675
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 88%

---

# Solución de problemas de la integración de Analytics y [!DNL Target] (A4T)

Este tema cubre algunos problemas comunes que se han encontrado al usar [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T).

## Las actividades no muestran datos en Analytics y aparecen como “sin especificar”. {#unspecified}

Existen varias razones por las que los datos se muestran como “sin especificar”:

* La clasificación no se ha procesado del todo en [!DNL Target].

  Los informes suelen tardar entre 24 y 72 horas en clasificarse después del primer guardado.

* El grupo de informes no contiene datos, pero [!DNL Target] ha intentado clasificar las visitas. [!DNL Target] no puede clasificar los datos hasta que no se efectúa la primera visita.

  Compruebe que el grupo de informes ha recibido al menos una visita.

* La llamada de clasificación realizada de [!DNL Target] a [!DNL Analytics] ha fallado.

  [Póngase en contacto con el servicio de atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para solicitar ayuda.

Si desglosa la fila “sin especificar” por la dimensión “Analytics for Target” y consiste en ID de actividad, significa que todo se clasifica correctamente. Si los ID de actividad se enumeran allí, sirve como indicación para un problema de clasificación.

>[!NOTE]
>
>En ocasiones, los datos se muestran correctamente en los informes, pero luego vuelven a aparecer como “sin especificar” porque se ha añadido una actividad nueva que no ha completado la clasificación. Recuerde que generalmente se tarda entre 24 y 72 horas en clasificar los informes después del primer guardado.
>
>No se pierde ningún dato cuando aparece como “sin especificar”. Los datos se asignan correctamente a la actividad o experiencia apropiadas cuando se efectúa la clasificación.

## Los informes de actividad de A4T incluyen una fila con muchos eventos “sin especificar”. {#added_unspecified_events}

Puede haber una fila de eventos &quot;[!UICONTROL Unspecified]&quot; que se muestra en el informe, según la métrica con la que se usen para mostrar los datos.

Normalmente, esta fila se muestra si elige una métrica común en el informe que no sea específico de [!DNL Target] (por ejemplo, [!UICONTROL Page Views], [!UICONTROL Visits], [!UICONTROL Unique Visitors], etc.). En este caso, la fila [!UICONTROL "Unspecified"] incluye todas las [!UICONTROL Page Views], [!UICONTROL Visits] y [!UICONTROL Unique Visitors] que no están asociadas a las actividades [!DNL Target].

Esa fila no tendrá ninguna información asociada con [!DNL Target] (por ejemplo, no tendrá visitantes, visitas ni impresiones). Para obtener más información, consulte [“Sin especificar”, “Ninguno”, “Otro” y “Desconocido” en la creación de informes](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=es) en las *Notas técnicas de Analytics*.

Si elige una métrica específica de [!DNL Target] en el informe, no se mostrará esa fila [!UICONTROL "Unspecified"]. La única manera de evitar que esto ocurra en el informe es establecer una llamada de [!DNL Target] en cada solicitud enviada desde esa página, lo que no es común ni necesario.

## El alza estimada en la métrica de ingresos no muestra datos correctos. {#section_35D766E5E4D347C39E15D08AA883FBB0}

Los detalles de alza y confianza no están disponibles en Analytics. Sin embargo, están disponibles en los informes de Target.

## Las actividades no aparecen en los informes de Analytics.   {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

Las actividades de A4T requieren que se especifique un servidor de seguimiento. Consulte [Uso de un servidor de seguimiento de Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para asegurarse de que el servidor de seguimiento de Analytics esté configurado correctamente.

>[!NOTE]
>
>No es necesario que especifique un servidor de seguimiento durante la creación de la actividad si utiliza la versión 0.9.1 (o posterior) de at.js. La biblioteca at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. Durante la creación de la actividad, puede dejar vacío el campo [!UICONTROL Tracking Server] en la página [!UICONTROL Goals & Settings].

## Mis segmentos de Analytics no aparecen en Target.   {#section_DEE87F1557834F448E99381D3D02EEEF}

Asegúrese de tener los permisos adecuados antes de empezar a crear actividades de A4T:

* Para poder usar Analytics como la fuente de informes para Target, debe pertenecer al grupo de acceso a servicios web de Adobe Analytics
* Debe ser miembro de uno o más grupos de Experience Cloud que tengan acceso a Analytics y a Target.
* Compruebe que Analytics y Target están presentes en la sección Aplicaciones de marketing del menú de navegación izquierdo.

## Las métricas de tasas de salto, saltos y salidas aparecen como positivos en los informes.   {#section_B5C3D56EF0344407AE67ABEB93037F5A}

Estas métricas que aparecen como positivas en los informes son un problema conocido.

Aunque estas métricas son negativas, el alza se muestra como si fuera positiva en los informes de Target. Por ejemplo, aunque desee una tasa de salto más baja, la tasa de salto más alta se mostrará como ganadora con el alza más alta. Tenga en cuenta estas métricas y las similares, y si prefiere disminuir o incrementar los números, a la hora de tomar decisiones basadas en los informes.

## El grupo de informes que necesito no aparece. {#section_BD8F956E41D6475B98B7BF0C74CC387C}

La lista de grupos de informes que aparece en [!DNL Target Standard/Premium] es la lista de grupos de informes que se han configurado para [!DNL Analytics] como fuente de informes para [!DNL Target] (A4T). Es posible que no vea todos los grupos de informes que tiene.

Si utiliza varias fuentes de informes, los grupos de informes deben estar presentes en la fuente de informes predeterminada establecida en [!DNL Target] también. Si los grupos de informes no están en la fuente de informes predeterminada, no se muestran.

Si sigue sin poder ver el grupo de informes que está buscando, debe comunicarse con [Atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitarlo.

## En los informes no veo tantos datos como esperaba. {#section_75002584FA63456D8D9086172925DD8D}

Revise su implementación, especialmente en las páginas donde los visitantes cumplen los requisitos de las experiencias, y compruebe que los ID de datos suplementarios coincidan en las llamadas de [!DNL Target] y [!DNL Analytics]. 

* **at.js 1.x**: en la llamada de [!DNL Target], el ID suplementario se encuentra en el parámetro `mboxMCSDID`. En la llamada de [!DNL Analytics], el ID suplementario se encuentra en el parámetro `sdid`.
* **at.js 2.x**: en la llamada de [!DNL Target], el ID suplementario se devuelve en el encabezado HTTP como el valor de `experienceCloud.analytics.supplementalDataId`. En la llamada de [!DNL Analytics], el ID suplementario se encuentra en el parámetro `sdid`.

La forma más sencilla de examinar el ID suplementario es mediante Adobe Experience Platform Debugger.

Si no ha instalado Debugger, consulte [Introducción a Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html?lang=es).

![Depurador](/help/main/c-integrating-target-with-mac/a4t/assets/debugger.png)

Si no hay ningún ID de datos suplementario en la llamada de [!DNL Target], confirme que el archivo [!DNL VisitorAPI.js] se carga antes que [!DNL at.js]. Si no hay ningún ID de datos suplementario en la llamada de [!DNL Analytics], confirme que la llamada de [!DNL Target] se activa antes que la llamada de [!DNL Analytics].

Para obtener más información, consulte [Implementación de Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A) o póngase en contacto con el [Servicio de atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).
