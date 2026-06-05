---
keywords: Automated Personalization;aplicación;cargar datos;datos sin conexión;algoritmo de personalización;segmentación automática;segmentación automática;prácticas recomendadas
description: Aprenda a cargar datos sin conexión al crear modelos de personalización en las actividades  [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación automática].
title: ¿Cómo puedo cargar datos para algoritmos de Personalization?
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
TQID: https://experienceleague.adobe.com/B1vwWrii4DfQzXftwcmgzbhBkDAZFo5mDRn3a7dULj0
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 323
ht-degree: 12%

---

# Cargar datos para los algoritmos de personalización de [!DNL Target]

Los datos sin conexión, como información de CRM o puntuaciones de inclinación de cancelación por parte del cliente, pueden ser muy valiosos al crear modelos de personalización en [!DNL Adobe Target] actividades [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación automática].

Hay varias formas de introducir datos en los algoritmos de personalización [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación automática]. Además de los métodos de [Métodos para obtener datos en Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=es){target=_blank}, también se usan las audiencias compartidas de [!DNL Experience Cloud] ([!UICONTROL Adobe Analytics], [!DNL Audience Manager]) y las audiencias de informes de actividad en los algoritmos de [!DNL Target].

Para obtener información sobre los datos que los algoritmos de personalización [!UICONTROL Automated Personalization] y [!UICONTROL Segmentación automática] recopilan y usan automáticamente, consulte [Recopilación de datos de Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Prácticas recomendadas {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

La siguiente lista presenta las prácticas recomendadas para cargar datos para los algoritmos de personalización de [!DNL Target]:

* Cuantos más datos de alta calidad haya disponibles para los algoritmos de personalización de [!DNL Target], mejor será la calidad de los modelos resultantes en las actividades [!UICONTROL Automated Personalization] y [!UICONTROL Segmentación automática].
* Limite el uso de múltiples scripts de perfil y atributos que tengan el mismo propósito.
* No pase un ID único, como un ID de sesión, si no es necesario.
* Revise qué datos [!DNL Target] recopila automáticamente ([Recopilación de datos para los algoritmos de Personalization de Target](/help/main/c-activities/t-automated-personalization/ap-data.md)) para que no envíe información duplicada. Por ejemplo, [!DNL Target] utiliza direcciones IP para determinar el código postal de los visitantes. No es necesario pasar esta información como variable independiente.
* No pase varios valores en el mismo atributo o variable. Si se concatenan varias variables, los algoritmos de personalización de [!DNL Target] tratan cada cadena como un valor único, lo que reduce el valor de la información para la personalización.
* Use una convención de nombres significativa y fácil de recordar para que sus [informes de Personalization Insights](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) sean más comprensibles.
