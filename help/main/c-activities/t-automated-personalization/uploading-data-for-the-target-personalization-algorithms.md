---
keywords: Automated Personalization;aplicación;cargar datos;datos sin conexión;algoritmo de personalización;segmentación automática;segmentación automática;prácticas recomendadas
description: Obtenga información sobre cómo cargar datos sin conexión al crear modelos de personalización en [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación automática] actividades.
title: ¿Cómo puedo cargar datos para algoritmos de personalización?
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 25%

---

# Carga de datos para [!DNL Target] algoritmos de personalización

Los datos sin conexión, como información de CRM o puntuaciones de inclinación de cancelación por parte del cliente, pueden ser muy valiosos al crear modelos de personalización en [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación automática] actividades.

Hay muchas maneras de introducir datos en los algoritmos de personalización de [!UICONTROL Personalización automatizada](AP) y de [!UICONTROL Segmentación automática. ] Además de los métodos indicados en [Métodos para obtener los datos en Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}, [!DNL Experience Cloud] audiencias compartidas ([!UICONTROL Adobe Analytics], [!DNL Audience Manager]) y las audiencias de informes en la actividad también se usan en [!DNL Target] algoritmos.

Para obtener información sobre los datos que los algoritmos de [!UICONTROL Personalización automatizada] y de [!UICONTROL Segmentación automática] recopilan y utilizan automáticamente, consulte [Recopilación de datos de personalización automatizada](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Prácticas recomendadas   {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

La siguiente lista presenta las prácticas recomendadas para cargar datos de [!DNL Target] algoritmos de personalización:

* Los datos de mayor calidad disponibles para [!DNL Target] algoritmos de personalización, cuanto mejor sea la calidad de los modelos resultantes en su [!UICONTROL Automated Personalization] y [!UICONTROL Segmentación automática] actividades.
* Limite el uso de múltiples scripts de perfil y atributos que tengan el mismo propósito.
* No pase un ID único, como un ID de sesión, si no es necesario.
* Revisar qué datos [!DNL Target] registra automáticamente ( [Recopilación de datos para los algoritmos de personalización de Target](/help/main/c-activities/t-automated-personalization/ap-data.md)) para que no envíe información duplicada. Por ejemplo, [!DNL Target] utiliza direcciones IP para determinar el código postal de los visitantes. No es necesario pasar esta información como variable independiente.
* No pase varios valores en el mismo atributo o variable. Si se concatenan varias variables, [!DNL Target] los algoritmos de personalización tratan cada cadena como un valor único, lo que reduce el valor de la información para la personalización.
* Utilice una nomenclatura significativa y fácil de recordar para que los   [Informes de Perspectivas de personalización](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) resulten más comprensibles.
