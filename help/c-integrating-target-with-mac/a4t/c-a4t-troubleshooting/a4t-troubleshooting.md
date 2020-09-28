---
keywords: analytics tracking server;A4T;analytics segments;report suites;incorrect data;orphaned;sdid;VisitorAPI.js;mboxMCSDID;phantom;unspecified
description: Este tema cubre algunos problemas comunes que se han encontrado al usar Analytics como fuente de informes para Target (A4T).
title: Resolución de problemas de integración de Analytics y Target (A4T)
feature: a4t troubleshooting
subtopic: Multivariate Test
topic: Standard
uuid: a5aa3be5-68a2-4f12-8226-f32a76136bbd
translation-type: tm+mt
source-git-commit: f6b83af17b8d98dbf565b02fb9b82f63946580bb
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 90%

---


# Resolución de problemas de integración de Analytics y Target (A4T){#troubleshoot-the-analytics-and-target-integration-a-t}

Este tema cubre algunos problemas comunes que se han encontrado al usar Analytics como fuente de informes para Target (A4T).

## Las actividades no muestran datos en Analytics y aparecen como “sin especificar”.{#unspecified}

Esto puede deberse a varios motivos:

* La clasificación no se ha procesado del todo en [!DNL Target].

   Los informes suelen tardar entre 24 y 72 horas en clasificarse después del primer guardado.

* El grupo de informes no contiene datos, pero [!DNL Target] ha intentado clasificar las visitas. [!DNL Target] no puede clasificar los datos hasta que no se efectúa la primera visita.

   Compruebe que el grupo de informes ha recibido al menos una visita.

* La llamada de clasificación realizada de [!DNL Target] a [!DNL Analytics] ha fallado.

   [Póngase en contacto con el servicio de atención al cliente](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para solicitar ayuda.

>[!NOTE]
>
>En ocasiones, los datos se muestran correctamente en los informes, pero luego vuelven a aparecer como “sin especificar” porque se ha añadido una actividad nueva que no ha completado la clasificación. Recuerde que generalmente se tarda entre 24 y 72 horas en clasificar los informes después del primer guardado.
>
>No se pierde ningún dato cuando aparece como “sin especificar”. Los datos se asignan correctamente a la actividad o experiencia apropiadas cuando se efectúa la clasificación.

## Los datos de My Analytics muestran un recuento inflado de visitas o visitantes cuando se inicia A4T.   {#section_4BE374E573D44FB7918611699B74F58E}

Para obtener más información, consulte [Minimización de recuentos inflados de visitas y visitantes en A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## El alza estimada en la métrica de ingresos no muestra datos correctos. {#section_35D766E5E4D347C39E15D08AA883FBB0}

Los detalles de alza y confianza no están disponibles en Analytics. Sin embargo, están disponibles en los informes de Target.

## Las actividades no aparecen en los informes de Analytics.   {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

Las actividades de A4T requieren que se especifique un servidor de seguimiento. Consulte [Usar un servidor de seguimiento de Analytics](../../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para comprobar si el servidor de seguimiento de Analytics está correctamente configurado.

>[!NOTE]
>
>Si usa Adobe Analytics como fuente de informes de la actividad, no es necesario que especifique un servidor de seguimiento durante la creación de la actividad en las versiones 61 (o posterior) de mbox.js y 0.9.1 (o posterior) de at.js. La biblioteca mbox.js o at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. Durante la creación de la actividad, puede dejar vacío el campo [!UICONTROL Servidor de seguimiento] de la página [!UICONTROL Objetivos y configuración].

## Mis segmentos de Analytics no aparecen en Target.   {#section_DEE87F1557834F448E99381D3D02EEEF}

Asegúrese de tener los permisos adecuados antes de empezar a crear actividades de A4T:

* Para poder usar Analytics como la fuente de informes para Target, debe pertenecer al grupo de acceso a servicios web de Adobe Analytics.
* Debe ser miembro de uno o más grupos de Experience Cloud que tengan acceso a Analytics y a Target.
* Compruebe que Analytics y Target están presentes en la sección Aplicaciones de marketing del menú de navegación izquierdo.

## Las métricas de tasas de salto, saltos y salidas aparecen como positivos en los informes.   {#section_B5C3D56EF0344407AE67ABEB93037F5A}

Este es un problema conocido.

Aunque estas métricas son negativas, el alza se muestra como si fuera positiva en los informes de Target. Por ejemplo, aunque desee una tasa de salto más baja, la tasa de salto más alta se mostrará como ganadora con el alza más alta. Tenga en cuenta estas métricas y las similares, y si prefiere disminuir o incrementar los números, a la hora de tomar decisiones basadas en los informes.

## El grupo de informes que necesito no aparece.   {#section_BD8F956E41D6475B98B7BF0C74CC387C}

La lista de grupos de informes que aparece en Target Standard/Premium es la lista de grupos de informes que se han configurado para Analytics como fuente de informes para Target. Esto significa que podría no ver todos los grupos de informes que tiene. Si no ve el grupo de informes que está buscando, debe comunicarse con ClientCare para habilitarlo.

## En los informes no veo tantos datos como esperaba. {#section_75002584FA63456D8D9086172925DD8D}

Revise su implementación, especialmente en las páginas donde los visitantes cumplen los requisitos de las experiencias, y compruebe que los ID de datos suplementarios coincidan en las llamadas de [!DNL Target] y [!DNL Analytics]. 

* **at.js 1.x**: En la [!DNL Target] llamada, el ID suplementario se encuentra en el `mboxMCSDID` parámetro. En la llamada de [!DNL Analytics], el ID suplementario se encuentra en el parámetro `sdid`.
* **at.js 2.x**: El ID suplementario se devuelve en el encabezado HTTP como valor para `experienceCloud.analytics.supplementalDataId`.

La forma más sencilla de examinar el ID suplementario es mediante Adobe Experience Platform Debugger.

Si no ha instalado el depurador, consulte [Introducción al depurador](https://docs.adobe.com/content/help/en/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html)de Adobe Experience Platform.

![Depurador](/help/c-integrating-target-with-mac/a4t/assets/debugger.png)

Si no hay ningún ID de datos suplementario en la llamada de [!DNL Target], confirme que el archivo [!DNL VisitorAPI.js] se carga antes que [!DNL at.js] o [!DNL mbox.js]. Si no hay ningún ID de datos suplementario en la llamada de [!DNL Analytics], confirme que la llamada de [!DNL Target] se activa antes que la llamada de [!DNL Analytics].

Para obtener más información, consulte [Implementación de Analytics para Target](../../../c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A) o póngase en contacto con el [Servicio de atención al cliente](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).