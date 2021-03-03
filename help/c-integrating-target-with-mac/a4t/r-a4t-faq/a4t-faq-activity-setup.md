---
keywords: preguntas más frecuentes;faq;analytics para target;a4T;configuración de actividades
description: Encuentre respuestas a preguntas sobre la configuración de actividades al usar Analytics for Target (A4T). A4T le permite utilizar los informes de Analytics para actividades de Target.
title: ¿Dónde puedo encontrar preguntas más frecuentes sobre la configuración de actividades con A4T?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: e45f0d2d2370f9c7aba2c2bd26afdd4c0e401db8
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 25%

---


# Configuración de actividades: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre la configuración de actividades y el uso de [!DNL Analytics] como fuente de informes para [!DNL Target] (A4T).

## ¿Qué tipos de actividades son compatibles con Analytics como fuente de informes (A4T)?{#section_5E4F58CD25A5424E869E6FE0803968EF}

Para obtener una lista completa, consulte “Tipos de actividades compatibles” en [Adobe Analytics como Fuente de informes para Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Al configurar las métricas de objetivo, ¿por qué no puedo acceder a la Configuración avanzada?

En el caso de las actividades que usan [!DNL Analytics] como fuente de informes (A4T), la métrica de objetivos usa las opciones &quot;[!UICONTROL Aumentar recuento y mantener al usuario en la actividad]&quot; y &quot;[!UICONTROL En cada impresión]&quot;. Estos ajustes *no* se pueden configurar.

Para obtener más información, consulte &quot;Al configurar las métricas de objetivo, ¿por qué no puedo acceder a las opciones de Configuración avanzada?&quot; en [Definiciones de métricas: preguntas más frecuentes sobre A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## Acabo de crear una actividad. ¿Por qué no entran datos? {#section_9F8092BE4225442896F926540292F221}

Cuando se crea una actividad, [!DNL Target] envía un archivo de clasificación a [!DNL Analytics]. Aunque [!DNL Analytics] está capturando y procesando los datos, no lo muestra en los informes hasta que se actualiza el archivo de clasificación. Este proceso puede tardar hasta 24 horas. Si al cabo de 48 horas no ve los datos, [contacte con ClientCare](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). Alternativamente, si sabe que va a iniciar una actividad, puede crearla con unos días de antelación y las clasificaciones se envían cuando se guarda la actividad. De este modo, aparecerán datos en el informe en cuanto se inicie la actividad. Tenga en cuenta que los datos tardan entre 45 y 90 minutos en procesarse en [!DNL Analytics].

## ¿Por qué no puedo seleccionar Analytics como fuente de informes cuando creo una actividad? {#section_9F4F69C3085F4C2480AF439127EB27CD}

Puede cambiar las opciones de [!UICONTROL Configuración de informes] en [!UICONTROL Administración].

1. En [!DNL Target], haga clic en **[!UICONTROL Administración]**.
1. En la lista desplegable **[!UICONTROL Solución de Experience Cloud utilizada para la creación de informes]**, haga clic en **[!UICONTROL Seleccionar por actividad]**.

![](assets/select-per-activity.png)

La lista desplegable **[!UICONTROL Fuente de informes]** está habilitada en la pantalla **[!UICONTROL Objetivo y configuración]** para crear y editar actividades.

Para usar siempre [!DNL Analytics] como fuente de informes, seleccione **[!UICONTROL Adobe Analytics]** en la lista desplegable de [!UICONTROL Administration].

## ¿Puede un visitante cambiar entre experiencias segmentadas y controladas en diferentes visitas en una actividad de segmentación automática que utiliza A4T?

Lo siguiente es verdadero, suponiendo que visitorId no cambie para un visitante entre visitas.

Si el porcentaje de asignación de tráfico se ajusta a mitad de la actividad, es posible que un visitante pueda moverse entre las experiencias de segmentación y de control.

Si los porcentajes no se ajustan a mitad de la actividad, un visitante que vea inicialmente el control siempre se envía al control. Un visitante que se envía a experiencias segmentadas siempre se envía a experiencias segmentadas.

* Después de estar en el &quot;bloque&quot; de tráfico segmentado, el visitante puede ser enviado a una experiencia diferente de la visita a la visita si los modelos de aprendizaje automático determinan que una experiencia diferente es relevante para la nueva visita.
* Después de asignarse al &quot;bloque&quot; de tráfico de control, un visitante siempre verá la misma experiencia, ya que la asignación de experiencias se basa en un hash pseudoaleatorio determinístico del visitorId.
