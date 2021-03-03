---
keywords: servidor de seguimiento de analytics;A4T;segmentos de analytics;grupos de informes;datos incorrectos;huérfanos;sdid;VisitorAPI.js;mboxMCSDID;fantasma;sin especificar
description: Explore los problemas comunes que los clientes han encontrado al usar Analytics for Target (A4T).
title: ¿Cómo puedo solucionar problemas de integración de Analytics y Target (A4T)?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: f48c54eb12a416312c3ceb6c1b36c3fc43496e78
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 42%

---


# Resolución de problemas de integración de Analytics y Target (A4T)

Este tema cubre algunos problemas comunes que se han encontrado al usar [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T).

## Las actividades no muestran datos en Analytics y aparecen como “sin especificar”.{#unspecified}

Existen varias razones por las que los datos se muestran como &quot;sin especificar&quot;:

* La clasificación no se ha procesado del todo en [!DNL Target].

   La clasificación generalmente tarda de 24 a 72 horas en clasificar los informes después del primer guardado.

* El grupo de informes no contiene datos, pero [!DNL Target] ha intentado clasificar las visitas. [!DNL Target] no puede clasificar los datos hasta que no se efectúa la primera visita.

   Compruebe que el grupo de informes ha recibido al menos una visita.

* La llamada de clasificación realizada de [!DNL Target] a [!DNL Analytics] ha fallado.

   [Póngase en contacto con el servicio de atención al cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para solicitar ayuda.

Si desglosa la fila &quot;sin especificar&quot; por la dimensión &quot;Analytics para Target&quot; y consiste en ID de actividad, significa que todo se clasifica correctamente. Si los ID de actividad se enumeran allí, sirve como indicación para un problema de clasificación.

>[!NOTE]
>
>En ocasiones, los datos se muestran correctamente en los informes, pero luego vuelven a aparecer como &quot;sin especificar&quot; porque se ha añadido una actividad nueva que no ha completado la clasificación. Recuerde que generalmente se tarda de 24 a 72 horas en clasificar los informes después del primer guardado.
>
>No se pierde ningún dato cuando aparece como “sin especificar”. Los datos se asignan correctamente a la actividad o experiencia apropiadas cuando se efectúa la clasificación.

## Los informes de actividad de A4T incluyen una fila con muchos eventos &quot;sin especificar&quot;. {#added_unspecified_events}

Puede haber una fila de eventos &quot;[!UICONTROL No especificados]&quot; en el informe, en función de la métrica con la que se usen para mostrar los datos.

Por lo general, esta fila se muestra si elige una métrica común en el informe que no sea [!DNL Target] específica (por ejemplo, [!UICONTROL Vistas de página], [!UICONTROL Visitas], [!UICONTROL Visitantes únicos], etc.). En este caso, la fila [!UICONTROL &quot;No especificado&quot;] incluye todas las [!UICONTROL Vistas de página], [!UICONTROL Visitas] y [!UICONTROL Visitantes únicos] que no están asociadas a las actividades [!DNL Target].

Esa fila no tendrá ninguna información asociada a [!DNL Target] (por ejemplo, ningún visitante, visita o impresiones). Para obtener más información, consulte [&quot;No especificado&quot;, &quot;Ninguno&quot;, &quot;Otro&quot; y &quot;Desconocido&quot; en Informes](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=en) en las *notas técnicas de Analytics*.

Si elige una métrica específica de [!DNL Target] en el informe, no se mostrará la fila [!UICONTROL &quot;No especificado&quot;]. La única manera de evitar que esto ocurra en el informe es establecer una [!DNL Target] llamada en cada solicitud enviada desde esa página, lo cual no es común ni necesario.

## Los datos de My Analytics muestran un recuento inflado de visitas o visitantes cuando se inicia A4T.    {#section_4BE374E573D44FB7918611699B74F58E}

Para obtener más información, consulte [Minimización de recuentos inflados de visitas y visitantes en A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## El alza estimada en la métrica de ingresos no muestra datos correctos. {#section_35D766E5E4D347C39E15D08AA883FBB0}

Los detalles de alza y confianza no están disponibles en Analytics. Sin embargo, están disponibles en los informes de Target.

## Las actividades no aparecen en los informes de Analytics.    {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

Las actividades de A4T requieren que se especifique un servidor de seguimiento. Consulte  [Usar un ](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) servidor de seguimiento de Analytics para asegurarse de que el servidor de seguimiento de Analytics está correctamente configurado.

>[!NOTE]
>
>No es necesario que especifique un servidor de seguimiento durante la creación de la actividad si utiliza la versión 61 (o posterior) de mbox.js o la versión 0.9.1 (o posterior) de at.js . La biblioteca mbox.js o at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. Durante la creación de la actividad, puede dejar vacío el campo [!UICONTROL Servidor de seguimiento] de la página [!UICONTROL Objetivos y configuración].

## Mis segmentos de Analytics no aparecen en Target.    {#section_DEE87F1557834F448E99381D3D02EEEF}

Asegúrese de tener los permisos adecuados antes de empezar a crear actividades de A4T:

* Pertenecer al grupo de acceso a servicios web de Adobe Analytics para poder usar Analytics como fuente de informes para Target
* Sea miembro de uno o varios grupos de Experience Cloud que tengan acceso a Analytics y Target.
* Compruebe que Analytics y Target están presentes en la sección Aplicaciones de marketing del menú de navegación izquierdo.

## Las métricas de tasas de salto, saltos y salidas aparecen como positivos en los informes.    {#section_B5C3D56EF0344407AE67ABEB93037F5A}

Estas métricas que aparecen como positivas en los informes son un problema conocido.

Aunque estas métricas son negativas, el alza se muestra como si fuera positiva en los informes de Target. Por ejemplo, aunque desee una tasa de salto más baja, la tasa de salto más alta se mostrará como ganadora con el alza más alta. Tenga en cuenta estas métricas y las similares, y si prefiere disminuir o incrementar los números, a la hora de tomar decisiones basadas en los informes.

## El grupo de informes que necesito no se muestra. {#section_BD8F956E41D6475B98B7BF0C74CC387C}

La lista de grupos de informes que aparece en [!DNL Target Standard/Premium] es la lista de grupos de informes que se han configurado para [!DNL Analytics] como fuente de informes para [!DNL Target] (A4T). Es posible que no vea todos los grupos de informes que tiene.

Si utiliza varias fuentes de informes, los grupos de informes también deben estar presentes en la fuente de informes predeterminada configurada en [!DNL Target]. Si los grupos de informes no están en la fuente de informes predeterminada, no se muestran.

Si todavía no ve el grupo de informes que está buscando, póngase en contacto con [Client Care](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para habilitarlo.

## En los informes no veo tantos datos como esperaba. {#section_75002584FA63456D8D9086172925DD8D}

Revise su implementación, especialmente en las páginas donde los visitantes cumplen los requisitos de las experiencias, y compruebe que los ID de datos suplementarios coincidan en las llamadas de [!DNL Target] y [!DNL Analytics]. 

* **at.js 1.x**: En la  [!DNL Target] llamada de , el ID suplementario se encuentra en el  `mboxMCSDID` parámetro . En la llamada de [!DNL Analytics], el ID suplementario se encuentra en el parámetro `sdid`.
* **at.js 2.x**: En la  [!DNL Target] llamada de , se devuelve el ID suplementario en el encabezado HTTP como valor para  `experienceCloud.analytics.supplementalDataId`. En la llamada de [!DNL Analytics], el ID suplementario se encuentra en el parámetro `sdid`.

La forma más sencilla de examinar el ID suplementario es mediante Adobe Experience Platform Debugger.

Si no ha instalado el depurador, consulte [Introducción a Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

![Depurador](/help/c-integrating-target-with-mac/a4t/assets/debugger.png)

Si no hay ningún ID de datos suplementario en la llamada de [!DNL Target], confirme que el archivo [!DNL VisitorAPI.js] se carga antes que [!DNL at.js] o [!DNL mbox.js]. Si no hay ningún ID de datos suplementario en la llamada de [!DNL Analytics], confirme que la llamada de [!DNL Target] se activa antes que la llamada de [!DNL Analytics].

Para obtener más información, consulte [Implementación de Analytics para Target](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A) o póngase en contacto con el [Servicio de atención al cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).
