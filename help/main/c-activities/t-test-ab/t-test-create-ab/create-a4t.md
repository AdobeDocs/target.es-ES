---
keywords: Segmentación;analytics;servidor de seguimiento;analytics for target;a4t
description: Obtenga información sobre cómo configurar una actividad en [!DNL Adobe Target] para que use [!DNL Adobe Analytics] como fuente de informes (A4T).
title: ¿Cómo puedo usar los datos de [!DNL Analytics] en [!DNL Target]?
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
TQID: 'https://experienceleague.adobe.com/x38YsYI4a6-92oOr6Fs3RfKrJHbSaLNj0cki5CInPPg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: 891742a5-242d-5099-966a-ca76c17cd2d2
    internal-label: Analytics for Target (A4T)
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%
---
# Usando datos de [!DNL Adobe Analytics] {#create-a4t}

>[!BEGINSHADEBOX]

**En esta página:** Obtenga información sobre cómo configurar una actividad para que use [!DNL Adobe Analytics] como fuente de informes (A4T), qué se debe preparar antes de comenzar y cómo elegir el objetivo de la actividad.

>[!ENDSHADEBOX]

Analytics for Target (A4T) mide los resultados de una actividad [!DNL Adobe Target] con los datos y las métricas de [!DNL Adobe Analytics]. Para usar A4T, configure la actividad para que [!DNL Analytics] sea su fuente de informes. Para obtener información detallada sobre la configuración de [!DNL Analytics] como origen de datos para [!DNL Target], consulte [Adobe Analytics como Source de informes para Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

## Antes de empezar {#before-you-begin}

>[!NOTE]
>
>La opción **[!UICONTROL Adobe Analytics]** está disponible cuando su cuenta de [!DNL Adobe Experience Cloud] está vinculada a [!DNL Analytics] y a [!DNL Target], aunque no se haya configurado la integración entre [!DNL Target] y [!DNL Analytics] para su cuenta.

Antes de crear la actividad, establezca su objetivo, por ejemplo, mejorar los ingresos por visitante (RPV) o aumentar los clics en el carro de compras. A continuación, elija la métrica de éxito final que mide este objetivo. Se pueden seleccionar métricas adicionales en [!DNL Analytics] en cualquier momento, pero aun así debe especificar la métrica a la que se espera que afecte esta prueba.

## Seleccione Analytics como fuente de informes {#select-reporting-source}

>[!NOTE]
>
>Si usa la versión 0.9.1 o posterior de at.js, no es necesario que especifique un servidor de seguimiento al crear una actividad que use [!DNL Adobe Analytics] como fuente de informes. La biblioteca at.js envía automáticamente los valores del servidor de seguimiento a [!DNL Target]. El campo **[!UICONTROL Servidor de seguimiento]** de la página **[!UICONTROL Objetivos y configuración]** puede permanecer vacío.

La fuente de informes está seleccionada en la página **[!UICONTROL Objetivos y configuración]** de la actividad. En esta página, elige una empresa de [!DNL Analytics] y el grupo de informes que recibe los datos de actividad de [!DNL Target] y verifica el servidor de seguimiento.

➡️ Para ver los pasos, los requisitos del grupo de informes y los detalles del servidor de seguimiento, consulte [Informes de Source](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reporting-source).

Cuando [!DNL Analytics] es la fuente de informes, la actividad no ofrece la opción de configurar audiencias para los informes. [!DNL Analytics] segmentos están disponibles en el informe [!DNL Target] **[!UICONTROL Actividades]** en su lugar.

## Establecer el objetivo de la actividad {#set-goal}

Cada actividad requiere una métrica de éxito como objetivo. El objetivo es la actividad de conversión que indica una actividad de éxito. Se puede utilizar cualquier métrica disponible en el selector de métricas [!DNL Analytics]. La práctica recomendada es no ejecutar nunca una prueba sin un objetivo de mejora específico.

La definición de un objetivo no impide el uso de otras métricas para evaluar los resultados de la prueba. Sin embargo, el objetivo identifica lo único que desea mejorar con la prueba.

Una vez que un visitante completa su objetivo, ese visitante ya no se incluye en la actividad. Si el visitante vuelve a entrar en la actividad después de completarla, se cuenta como un visitante nuevo.
