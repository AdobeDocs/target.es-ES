---
description: Lista de las preguntas más frecuentes sobre los informes en Target.
keywords: resolución de problemas;discrepancias entre métricas;preguntas más frecuentes;informes
seo-description: Lista de preguntas más frecuentes sobre la creación de informes en Adobe Target.
seo-title: Preguntas más frecuentes sobre informes para Adobe Target
solution: Target
title: Preguntas más frecuentes sobre la creación de informes
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: a6f2eceaddf67653b36a1687ba071f7226169516

---


# Preguntas más frecuentes sobre la creación de informes{#reporting-faq}

Lista de las preguntas más frecuentes sobre los informes en [!DNL Target].

## ¿Por qué los informes de [!UICONTROL Segmentación] de experiencias (XT) contienen métricas para las experiencias de control?

Las actividades XT siempre deben tener una experiencia de control. Si está utilizando una actividad XT de forma similar a una actividad de prueba [!UICONTROL A/] B, que es un escenario bastante común, los datos de experiencia de control son útiles. Puede ignorar los datos de la experiencia de control si los informes no le resultan útiles.

## Why are the number of visits lower in [!DNL Target] than in other [!DNL Adobe Experience Cloud] solutions? {#section_7E626FDB417E41B8B58BBF30FB207409}

Los números de las métricas que recoge [!DNL Target], como las visitas, siempre serán menores que los números recogidos en otras soluciones de [!DNL Experience Cloud] por varios motivos:

* [!DNL Target] solo cuenta las visitas de las personas que cumplen los requisitos de la actividad. Otras soluciones cuentan las visitas de las personas que muestran la página sea cual sea la actividad que los trajo a la página.
* Podría haber situaciones en las que distintas actividades compitan por la misma ubicación (mutuamente excluyentes). Como resultado, los visitantes ven contenido distinto en una página web, lo cual afecta a los números de las métricas que [!DNL Target] recaba.

## ¿Por qué no hay datos disponibles en el informe de mi actividad?{#section_E4722F6445884130951DF79981C8289B}

If an activity's content was successfully delivered to users but its report contains no data, ensure that you have the correct environment ([host group](/help/administrating-target/hosts.md)) selected in the report's settings.

Si tiene seleccionado un entorno de desarrollo, puede que vea el siguiente mensaje de error: “No hay datos disponibles para la configuración de informe seleccionada”.

Para cambiar el entorno en el informe de una actividad:

1. Haga clic en **[!UICONTROL Actividades]**, en la actividad que quiera de la lista y luego en la ficha **Informes[!UICONTROL .]**
1. Haga clic en el icono del engranaje para definir la configuración del informe.

   ![Cuadro de diálogo Configuración A/B](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >The gear icon is not available for [!UICONTROL Automated Personalization] (AP) reports.

1. En la lista desplegable **[!UICONTROL Entornos]**, seleccione **[!UICONTROL Producción]**.

   Puede que no haya datos de informe disponibles si ha seleccionado un entorno de desarrollo.

1. Haga clic en **[!UICONTROL Guardar]**.

Para obtener más información sobre los entornos, consulte [Hosts](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).
