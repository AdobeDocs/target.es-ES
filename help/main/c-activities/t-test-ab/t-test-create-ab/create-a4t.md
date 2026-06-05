---
keywords: Segmentación;analytics;servidor de seguimiento;analytics for target;a4t
description: Aprenda a configurar una actividad en  [!DNL Adobe Target] para que use [!DNL Adobe Analytics] como fuente de informes (A4T).
title: ¿Cómo puedo usar  [!DNL Analytics] datos en [!DNL Target]?
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
TQID: https://experienceleague.adobe.com/x38YsYI4a6-92oOr6Fs3RfKrJHbSaLNj0cki5CInPPg
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 492
ht-degree: 19%

---

# Usando datos de [!DNL Adobe Analytics]

Puede configurar una actividad en [!DNL Adobe Target] para que use [!DNL Adobe Analytics] como fuente de informes (A4T).

Para obtener información detallada sobre la configuración de [!DNL Analytics] como origen de datos para [!DNL Target], consulte [Adobe Analytics como Source de informes para Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

Antes de configurar una actividad que usa [!DNL Analytics] como fuente de informes, establezca el objetivo de la actividad, como mejorar los ingresos por visitante (RPV) o aumentar los clics en el carro de compras. Seleccione una métrica de éxito final para la actividad. Aunque puede seleccionar métricas adicionales en cualquier momento en [!DNL Analytics], debe especificar una métrica concreta a la que espera que afecte esta prueba.

>[!NOTE]
>
>La opción [!DNL Adobe Analytics] está disponible si ha vinculado su cuenta de [!DNL Adobe Experience Cloud] con [!DNL Analytics] y [!DNL Target], aunque no se haya configurado la integración entre [!DNL Target] y [!DNL Analytics] para su cuenta.

Al seleccionar [!DNL Analytics] como fuente de informes para [!DNL Target], selecciona un grupo de informes [!DNL Analytics] para recibir [!DNL Target] datos de actividad. Para especificar una fuente de informes, primero elija una de las [!DNL Analytics] empresas a la cual esté asociada su cuenta y luego seleccione el grupo de informes apropiado para la actividad. Solo los grupos de informes que se hayan aprovisionado para conectarse a [!DNL Adobe Target] están disponibles para su selección. Si no ve el grupo de informes que espera, primero cierre la sesión y vuelva a iniciarla en [!DNL Adobe Experience Cloud] para intentarlo de nuevo. Si el grupo de informes sigue sin aparecer en la lista, póngase en contacto con el Servicio de atención al cliente.

[!UICONTROL Analytics for Target] (A4T) requiere un servidor de seguimiento para informar correctamente sobre los resultados. Aparece un servidor de seguimiento predeterminado en el campo [!UICONTROL Servidor de seguimiento]. Si utiliza más de un servidor de seguimiento, asegúrese de incluir el servidor de seguimiento correcto en este campo. Consulte [Uso de un servidor de seguimiento de Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para obtener más información.

>[!NOTE]
>
>Si usa [!DNL Adobe Analytics] como fuente de informes de la actividad, no es necesario que especifique un servidor de seguimiento durante la creación de la actividad en la versión 0.9.1 (o posterior) de at.js. La biblioteca at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. Durante la creación de la actividad, puede dejar vacío el campo [!UICONTROL Servidor de seguimiento] de la página [!UICONTROL Objetivos y configuración].

Al configurar una actividad después de configurar [!DNL Analytics] como fuente de informes, no hay ninguna opción para configurar audiencias para los informes. [!DNL Analytics] segmentos están disponibles en el informe [!DNL Target] [!UICONTROL Actividades].

Debe seleccionar una métrica de éxito para utilizarla como objetivo para cada actividad. El objetivo de actividad es la actividad de conversión que indica que una actividad ha tenido éxito. Se recomienda no ejecutar nunca una prueba sin tener como objetivo mejorarla de alguna manera específica. Puede elegir cualquier métrica [!DNL Analytics] disponible en el selector de métricas [!DNL Analytics].

El hecho de definir un objetivo no significa que no se pueda utilizar otra métrica al evaluar los resultados de la prueba. Por el contrario, el objetivo es un recordatorio del aspecto que se desea mejorar con la prueba.

Una vez que un visitante completa su objetivo, ese visitante ya no se incluye en la actividad. Si el visitante vuelve a entrar en su actividad después de completar una actividad de, ese visitante se cuenta como un visitante nuevo.
