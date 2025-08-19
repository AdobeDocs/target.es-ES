---
keywords: Automated Personalization;aplicación;cargar datos;datos sin conexión;algoritmo de personalización;segmentación automática;segmentación automática;prácticas recomendadas
description: Obtenga información sobre cómo cargar datos sin conexión al crear modelos de personalización en actividades  [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target].
title: ¿Cómo puedo cargar datos para algoritmos de Personalization?
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 10%

---

# Cargar datos para los algoritmos de personalización de [!DNL Target]

Los datos sin conexión, como información de CRM o puntuaciones de inclinación de cancelación por parte del cliente, pueden ser muy valiosos al crear modelos de personalización en actividades [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target].

Hay varias formas de introducir datos en los algoritmos de personalización [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Auto-Target]. Además de los métodos de [Métodos para obtener datos en Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=es){target=_blank}, también se usan [!DNL Experience Cloud] audiencias compartidas ([!UICONTROL Adobe Analytics], [!DNL Audience Manager]) y audiencias de informes de actividad en [!DNL Target] algoritmos.

Para obtener información acerca de los datos que los algoritmos de personalización [!UICONTROL Automated Personalization] y [!UICONTROL Auto-Target] recopilan y usan automáticamente, consulte [Recopilación de datos de Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Prácticas recomendadas   {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

La siguiente lista presenta las prácticas recomendadas para cargar datos para los algoritmos de personalización de [!DNL Target]:

* Cuantos más datos de alta calidad haya disponibles para los algoritmos de personalización de [!DNL Target], mejor será la calidad de los modelos resultantes en las actividades [!UICONTROL Automated Personalization] y [!UICONTROL Auto-Target].
* Limite el uso de múltiples scripts de perfil y atributos que tengan el mismo propósito.
* No pase un ID único, como un ID de sesión, si no es necesario.
* Revise qué datos [!DNL Target] recopila automáticamente ([Recopilación de datos para los algoritmos de Personalization de Target](/help/main/c-activities/t-automated-personalization/ap-data.md)) para que no envíe información duplicada. Por ejemplo, [!DNL Target] utiliza direcciones IP para determinar el código postal de los visitantes. No es necesario pasar esta información como variable independiente.
* No pase varios valores en el mismo atributo o variable. Si se concatenan varias variables, los algoritmos de personalización de [!DNL Target] tratan cada cadena como un valor único, lo que reduce el valor de la información para la personalización.
* Use una convención de nombres significativa y fácil de recordar para que sus [informes de Personalization Insights](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) sean más comprensibles.
