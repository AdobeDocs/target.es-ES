---
description: Lista de las preguntas más frecuentes sobre los informes en Target.
keywords: resolución de problemas;discrepancias entre métricas;preguntas más frecuentes;informes
seo-description: Lista de las preguntas más frecuentes sobre los informes en Target.
seo-title: Preguntas más frecuentes sobre la creación de informes
solution: Target
title: Preguntas más frecuentes sobre la creación de informes
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: 74a6f402bc0c9dae6f89cbdb632d7dbc53743593

---


# Preguntas más frecuentes sobre la creación de informes{#reporting-faq}

Lista de las preguntas más frecuentes sobre los informes en Target.

## ¿Por qué el número de visitas es menor en Target que en otras soluciones de Experience Cloud?{#section_7E626FDB417E41B8B58BBF30FB207409}

Los números de las métricas que recoge [!DNL Target], como las visitas, siempre serán menores que los números recogidos en otras soluciones de [!DNL Experience Cloud] por varios motivos:

* [!DNL Target] solo cuenta las visitas de las personas que cumplen los requisitos de la actividad. Otras soluciones cuentan las visitas de las personas que muestran la página sea cual sea la actividad que los trajo a la página.
* Pueden darse casos en que distintas actividades compitan por la misma ubicación (que se excluyan mutuamente). Como resultado, los visitantes ven contenido distinto en una página web, lo cual afecta a los números de las métricas que [!DNL Target] recaba.

## ¿Por qué no hay datos disponibles en el informe de mi actividad?{#section_E4722F6445884130951DF79981C8289B}

Si el contenido de una actividad se entregó correctamente a los usuarios, pero el informe no contiene datos, compruebe si el entorno (grupo de hosts) correcto está seleccionado en la configuración del informe.

Si tiene seleccionado un entorno de desarrollo, puede que vea el siguiente mensaje de error: “No hay datos disponibles para la configuración de informe seleccionada”.

Para cambiar el entorno en el informe de una actividad:

1. Haga clic en **[!UICONTROL Actividades]**, en la actividad que quiera de la lista y luego en la ficha **Informes[!UICONTROL .]**
1. Haga clic en el icono del engranaje para definir la configuración del informe.

   ![](assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >El icono del engranaje no está disponible para informes de Personalización automatizada.

1. En la lista desplegable **[!UICONTROL Entornos]**, seleccione **[!UICONTROL Producción]**.

   Puede que no haya datos de informe disponibles si ha seleccionado un entorno de desarrollo.

1. Haga clic en **[!UICONTROL Guardar configuración]**.

Para obtener más información sobre los entornos, consulte [Hosts](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).
