---
keywords: preguntas más frecuentes;faq;analytics para target;a4T;configuración de actividades
description: En este tema encontrará respuestas a preguntas que se plantean a menudo sobre la configuración de actividades y el uso de Analytics como fuente de informes para Target (A4T).
title: 'Configuración de actividad: Preguntas más frecuentes sobre A4T'
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 39%

---


# Configuración de actividades: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre la configuración de actividades y el uso de [!DNL Analytics] como fuente de sistema de informes para [!DNL Target] (A4T).

## ¿Qué tipos de actividades son compatibles con Analytics como fuente de informes (A4T)?{#section_5E4F58CD25A5424E869E6FE0803968EF}

Para obtener una lista completa, consulte “Tipos de actividades compatibles” en [Adobe Analytics como Fuente de informes para Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Al configurar mis métricas de objetivo, ¿por qué no puedo acceder a la Configuración avanzada?

En el caso de actividades que utilicen [!DNL Analytics] como fuente de sistema de informes (A4T), la métrica de objetivos siempre usará la configuración &quot;[!UICONTROL Aumentar recuento y mantener al usuario en Actividad]&quot; y &quot;[!UICONTROL En cada impresión]&quot;. Esto *no se puede configurar*.

Para obtener más información, consulte &quot;Al configurar mis métricas de objetivo, ¿por qué no puedo acceder a las opciones de Configuración avanzada?&quot; en [Definiciones de métricas: Preguntas más frecuentes de A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## Acabo de crear una actividad. ¿Por qué no entran datos? {#section_9F8092BE4225442896F926540292F221}

Cuando se crea una actividad, [!DNL Target] envía un archivo de clasificación a [!DNL Analytics]. Aunque [!DNL Analytics] está capturando y procesando los datos, no se muestran en los informes hasta que se actualiza el archivo de clasificación. Este proceso puede tardar hasta 24 horas. Si al cabo de 48 horas no ve los datos, [contacte con ClientCare](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). De forma alternativa, si sabe que va a iniciar una actividad, puede crearla con unos días de antelación y el archivo de clasificación se enviará cuando se guarde la actividad. De este modo, aparecerán datos en el informe en cuanto se inicie la actividad. Tenga en cuenta que los datos tardan entre 45 y 90 minutos en procesarse en [!DNL Analytics].

## ¿Por qué no puedo seleccionar Analytics como fuente de informes cuando creo una actividad nueva?    {#section_9F4F69C3085F4C2480AF439127EB27CD}

Puede cambiar las opciones de [!UICONTROL Configuración de Sistema de informes] en [!UICONTROL Administración].

1. En [!DNL Target], haga clic en **[!UICONTROL Administración]**.
1. En la lista desplegable **[!UICONTROL Solución de Experience Cloud utilizada para la creación de informes]**, haga clic en **[!UICONTROL Seleccionar por actividad]**.

![](assets/select-per-activity.png)

La lista desplegable **[!UICONTROL Fuente de informes]** está habilitada en la pantalla **[!UICONTROL Objetivo y configuración]** para crear y editar actividades.

Para utilizar siempre [!DNL Analytics] como fuente de sistema de informes, seleccione **[!UICONTROL Adobe Analytics]** en la lista desplegable en [!UICONTROL Administración].

## ¿Puede un visitante cambiar entre experiencias segmentadas y controladas en diferentes visitas en una actividad de Destinatario automático que utilice A4T?

Lo siguiente es true si visitorId no cambia para un visitante entre visitas.

Si el porcentaje de asignación de tráfico se ajusta a mitad de actividad, es posible que un visitante pueda moverse entre las experiencias de destino y de control.

Si los porcentajes no se ajustan en la mitad de la actividad, siempre se enviará al control un visitante que vea inicialmente el control. Un visitante que se envía a las experiencias objetivo siempre se envía a las experiencias objetivo.

* Después de estar en el &quot;bloque&quot; de tráfico objetivo, el visitante se puede enviar a una experiencia diferente de una visita a otra si los modelos de aprendizaje automático determinan que una experiencia diferente es relevante para la nueva visita.
* Después de asignarlo al &quot;bloque&quot; de control del tráfico, un visitante siempre verá la misma experiencia porque la asignación de experiencia se basa en un hash determinístico pseudoaleatorio del visitorId del visitante.
