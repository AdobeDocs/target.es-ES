---
keywords: Segmentación;análisis;servidor de seguimiento;análisis para destinatario;a4t
description: Obtenga información sobre cómo configurar una actividad en Adobe Target para utilizar Adobe Analytics como fuente de sistema de informes. Esta integración se denomina Analytics para Destinatario (A4T).
title: ¿Cómo puedo usar datos de Analytics en Destinatario?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 85%

---


# Usar datos de Analytics

Puede configurar una actividad en [!DNL Adobe Target] para que utilice [!DNL Adobe Analytics] como fuente de sistema de informes (A4T).

Para obtener información detallada sobre la configuración de Analytics como fuente de datos para Destinatario, consulte [Adobe Analytics como fuente de Sistema de informes para Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md).

Antes de configurar una actividad que use Analytics como fuente de informes, establezca el objetivo de la actividad, como mejorar los ingresos por visitante (RPV) o aumentar los clics en el carro de compras. Seleccione una métrica de éxito final para la campaña. Aunque puede seleccionar métricas adicionales en cualquier momento en Analytics, es necesario que especifique una métrica en particular en torno a la cual desea que gire la prueba.

>[!NOTE]
>
>La opción Adobe Analytics está disponible si ha vinculado su cuenta de Adobe Experience Cloud con Analytics y Target aunque no haya configurado la integración entre Target y Analytics en la cuenta.

Si selecciona Analytics como fuente de informes para Target, debe seleccionar también un grupo de informes de Analytics en el que recibir los datos de la actividad en Target. Para ello, elija primero una de las empresas de Analytics a la que esté asociada su cuenta y, a continuación, seleccione el grupo de informes adecuado para la actividad. Solo se podrán seleccionar los grupos de informes que estén aprovisionados para conectarse a Adobe Target. Si no ve los grupos de informes previstos, cierre la sesión y vuelva a iniciarla en Adobe Experience Cloud para probar de nuevo. Si aún no aparece el grupo de informes en la lista, póngase en contacto con el Servicio de atención al cliente.

Analytics for Target requiere un servidor de seguimiento para registrar los resultados correctamente. En el campo Servidor de seguimiento, aparecerá un servidor de seguimiento predeterminado. Si usa más de un servidor de seguimiento, debe asegurarse de incluir el servidor correcto en este campo. Consulte [Usar un servidor de seguimiento de Analytics](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para obtener más información.

>[!NOTE]
>
>Si usa Adobe Analytics como fuente de informes de la actividad, no es necesario que especifique un servidor de seguimiento durante la creación de la actividad en las versiones 61 (o posterior) de mbox.js y 0.9.1 (o posterior) de at.js. La biblioteca mbox.js o at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. Durante la creación de la actividad, puede dejar vacío el campo [!UICONTROL Servidor de seguimiento] de la página [!UICONTROL Objetivos y configuración].

Cuando se configura una actividad después de establecer Analytics como fuente de informes, ya no se pueden configurar audiencias para los informes. Los segmentos de Analytics se encuentran disponibles en el informe Actividades de Target.

Debe seleccionar una métrica de éxito que se utilizará como objetivo en cada prueba. El objetivo de la prueba es la actividad de conversión que nos indica una campaña de éxito. Se recomienda no ejecutar nunca una prueba sin tener como objetivo mejorarla de alguna manera específica. Puede elegir cualquier métrica de Analytics disponible en el selector de métricas de Analytics.

El hecho de definir un objetivo no significa que no se pueda utilizar otra métrica al evaluar los resultados de la prueba. Por el contrario, el objetivo es un recordatorio del aspecto que se desea mejorar con la prueba.

Una vez que un visitante consigue el objetivo, ya no se le vuelve a incluir en la campaña. Si el visitante volviera a incluirse en la campaña después de haber completado una actividad, se le contabilizará como nuevo visitante.
