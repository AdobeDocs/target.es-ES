---
keywords: Segmentación;analytics;servidor de seguimiento;analytics for target;a4t
description: Obtenga información sobre cómo configurar una actividad en [!DNL Adobe Target] para utilizar [!DNL Adobe Analytics] como fuente de informes (A4T).
title: ¿Cómo puedo usar [!DNL Analytics] Datos en [!DNL Target]?
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 19%

---

# Uso de [!DNL Adobe Analytics] datos

Puede configurar una actividad en [!DNL Adobe Target] para utilizar [!DNL Adobe Analytics] como fuente de informes (A4T).

Para obtener información detallada sobre la configuración de [!DNL Analytics] como fuente de datos para [!DNL Target], consulte [Adobe Analytics como fuente de informes para Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

Antes de configurar una actividad que utiliza [!DNL Analytics] como fuente de informes, establezca el objetivo de la actividad (por ejemplo, mejorar los ingresos por visitante (RPV) o aumentar los clics en el carro de compras). Seleccione una métrica de éxito final para la actividad. Aunque puede seleccionar métricas adicionales en cualquier momento en [!DNL Analytics]No obstante, debe especificar una métrica concreta a la que espere que afecte esta prueba.

>[!NOTE]
>
>El [!DNL Adobe Analytics] La opción está disponible si ha vinculado su [!DNL Adobe Experience Cloud] cuenta con ambos [!DNL Analytics] y [!DNL Target], incluso si la integración entre [!DNL Target] y [!DNL Analytics] no se ha configurado para su cuenta.

Al seleccionar [!DNL Analytics] como fuente de informes para [!DNL Target], seleccione una [!DNL Analytics] grupo de informes que recibir [!DNL Target] datos de actividad. Para especificar una fuente de informes, elija primero una de las siguientes opciones [!DNL Analytics] asocia su cuenta a y, a continuación, selecciona el grupo de informes correspondiente a la actividad. Solo los grupos de informes que estén aprovisionados para conectarse a [!DNL Adobe Target] están disponibles para su selección. Si no ve el grupo de informes que espera, primero cierre la sesión y vuelva a iniciarla en [!DNL Adobe Experience Cloud] para intentarlo de nuevo. Si el grupo de informes sigue sin aparecer en la lista, póngase en contacto con el Servicio de atención al cliente.

[!UICONTROL Analytics for Target] (A4T) requiere un servidor de seguimiento para informar correctamente de los resultados. Aparece un servidor de seguimiento predeterminado en la [!UICONTROL Servidor de seguimiento] field. Si utiliza más de un servidor de seguimiento, asegúrese de incluir el servidor de seguimiento correcto en este campo. Consulte [Uso de un servidor de seguimiento de Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para obtener más información.

>[!NOTE]
>
>Si utiliza [!DNL Adobe Analytics] como fuente de informes de la actividad, no es necesario que especifique un servidor de seguimiento durante la creación de la actividad si utiliza la versión 0.9.1 (o posterior) de at.js. La biblioteca at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. Durante la creación de la actividad, puede dejar vacío el campo [!UICONTROL Servidor de seguimiento] de la página [!UICONTROL Objetivos y configuración].

Al configurar una actividad después de configurarla [!DNL Analytics] como fuente de informes, no hay opción de configurar audiencias para los informes. [!DNL Analytics] Los segmentos de están disponibles en [!DNL Target] [!UICONTROL Actividades] informe.

Debe seleccionar una métrica de éxito para utilizarla como objetivo para cada actividad. El objetivo de actividad es la actividad de conversión que indica que una actividad ha tenido éxito. La práctica recomendada es no ejecutar nunca una prueba sin tener como objetivo mejorar de una manera específica. Puede elegir cualquier [!DNL Analytics] métrica disponible en el [!DNL Analytics] selector de métricas.

El hecho de definir un objetivo no significa que no se pueda utilizar otra métrica al evaluar los resultados de la prueba. Por el contrario, el objetivo es un recordatorio del aspecto que se desea mejorar con la prueba.

Una vez que un visitante completa su objetivo, ese visitante ya no se incluye en la actividad. Si el visitante vuelve a entrar en su actividad después de completar una actividad de, ese visitante se cuenta como un visitante nuevo.
