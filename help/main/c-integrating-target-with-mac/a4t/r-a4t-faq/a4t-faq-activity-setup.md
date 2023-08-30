---
keywords: preguntas más frecuentes;faq;analytics para target;a4T;configuración de actividades
description: Encuentre respuestas a preguntas acerca de la configuración de actividades al usar Analytics para [!DNL Target] (A4T). A4T le permite utilizar los informes de Analytics para [!DNL Target] actividades.
title: ¿Dónde puedo encontrar preguntas frecuentes acerca de la configuración de actividades de con A4T?
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 52dd26acfce77da0eea14be572708c069ba5e9ba
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 16%

---

# Configuración de actividades: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre la configuración y el uso de las actividades de [!DNL Analytics] como fuente de informes para [!DNL Target] (A4T).

## ¿Qué tipos de actividades son compatibles con Analytics como fuente de informes (A4T)? {#section_5E4F58CD25A5424E869E6FE0803968EF}

+++Respuesta Para obtener una lista completa, consulte &quot;Tipos de actividades compatibles&quot; en [Adobe Analytics como fuente de informes para Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

+++

## Al configurar mis Métricas de objetivo, ¿por qué no puedo acceder a Configuración avanzada?

+++Respuesta para actividades que utilizan [!DNL Analytics] como fuente de informes (A4T), la métrica de objetivo utiliza el[!UICONTROL Aumentar recuento y mantener el usuario en la actividad]&quot; y &quot;[!UICONTROL En cada impresión]Configuración de &quot;. Estos ajustes son *no* configurable.

Para obtener más información, consulte &quot;Al configurar las métricas de objetivo, ¿por qué no puedo acceder a las opciones de configuración avanzada?&quot; in [Definiciones de métricas: preguntas más frecuentes sobre A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## Acabo de crear una actividad. ¿Por qué no entran datos? {#section_9F8092BE4225442896F926540292F221}


+++Responder Cuando se crea una actividad, [!DNL Target] envía un archivo de clasificación a [!DNL Analytics]. Aunque [!DNL Analytics] está capturando y procesando los datos, no lo muestra en los informes hasta que se actualiza el archivo de clasificación. Este proceso puede tardar entre 24 y 72 horas en completarse. Si después de 72 horas no ve sus datos, [Contactar con Atención al cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). Como alternativa, si sabe que inicia una actividad, puede crearla con unos días de antelación y las clasificaciones se envían cuando se guarda la actividad. De este modo, aparecerán datos en el informe en cuanto se inicie la actividad. Tenga en cuenta que los datos tardan entre 45 y 90 minutos en procesarse en [!DNL Analytics].

+++

## ¿Por qué no puedo seleccionar Analytics como fuente de informes al crear una actividad? {#section_9F4F69C3085F4C2480AF439127EB27CD}

+++Respuesta Puede cambiar su [!UICONTROL Configuración de informes] opciones en [!UICONTROL Administration].

1. Entrada [!DNL Target], haga clic en **[!UICONTROL Administration]**.
1. En la lista desplegable **[!UICONTROL Solución de Experience Cloud utilizada para la creación de informes]**, haga clic en **[!UICONTROL Seleccionar por actividad]**.

![imagen de selección por actividad](assets/select-per-activity.png)

La lista desplegable **[!UICONTROL Fuente de informes]** está habilitada en la pantalla **[!UICONTROL Objetivo y configuración]** para crear y editar actividades.

Para usar siempre [!DNL Analytics] como fuente de informes, seleccione **[!UICONTROL Adobe Analytics]** de la lista desplegable en [!UICONTROL Administration].

+++

## ¿Puede un visitante cambiar entre experiencias segmentadas y controladas en diferentes visitas en una actividad de segmentación automática que utiliza A4T?

+++Respuesta Lo siguiente es verdadero suponiendo que visitorId no cambie para un visitante entre visitas.

Si el porcentaje de asignación de tráfico se ajusta a mitad de la actividad, es posible que un visitante pueda moverse entre las experiencias de segmentación y de control.

Si los porcentajes no se ajustan a mitad de la actividad, siempre se envía a un visitante que ve inicialmente el control. Un visitante que se envía a experiencias segmentadas siempre se envía a experiencias segmentadas.

* Después de estar en el &quot;bloque&quot; de tráfico objetivo, el visitante puede ser enviado a una experiencia diferente de visita en visita si los modelos de aprendizaje automático determinan que una experiencia diferente es relevante para la nueva visita.
* Después de asignarse al &quot;bloque&quot; de control de tráfico, un visitante siempre verá la misma experiencia porque la asignación de experiencias se basa en un hash seudoaleatorio determinístico del visitorId.

+++

## ¿Puedo usar un binomio? [!DNL Analytics] métrica con un segmento aplicado como objetivo de optimización en un [!UICONTROL Asignación automática] actividad? {#binomial}

+++Respuesta No se puede utilizar un [!DNL Analytics] métrica con un segmento aplicado como objetivo de optimización en un [!UICONTROL Asignación automática] actividad. Como solución alternativa, puede definir un Evento personalizado que logre el mismo objetivo y utilizarlo como métrica de objetivo de optimización.

+++