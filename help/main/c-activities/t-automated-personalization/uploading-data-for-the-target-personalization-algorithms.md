---
keywords: Automated Personalization;aplicación;cargar datos;datos sin conexión;algoritmo de personalización;segmentación automática;segmentación automática;prácticas recomendadas
description: Aprenda a cargar datos sin conexión al crear modelos de personalización en [!DNL Adobe Target] actividades de [!UICONTROL Automated Personalization] (AP) y [!UICONTROL Segmentación automática].
title: ¿Cómo puedo cargar datos para algoritmos de Personalization?
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=es#premium newtab=true" tooltip="Consulte qué se incluye en Target Premium."
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
TQID: 'https://experienceleague.adobe.com/B1vwWrii4DfQzXftwcmgzbhBkDAZFo5mDRn3a7dULj0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
    internal-label: Shared audiences
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: ddd4fa83540294ee229b87f041bc2245ba9a3464
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 7%
---
# Cargar datos para los algoritmos de personalización de [!DNL Target] {#upload-data-personalization}

>[!BEGINSHADEBOX]

**En esta página:** Aprenda a enviar datos sin conexión y personalizados a los algoritmos **[!UICONTROL Automated Personalization]** y **[!UICONTROL Segmentación automática]**, y a las prácticas recomendadas que se deben seguir.

>[!ENDSHADEBOX]

Los datos sin conexión, como información de CRM o puntuaciones de inclinación de cancelación por parte del cliente, pueden ser muy valiosos al crear modelos de personalización en las actividades [!DNL Adobe Target] **[!UICONTROL Automated Personalization]** (AP) y **[!UICONTROL Segmentación automática]**.

Hay varias formas de introducir datos en los algoritmos de personalización **[!UICONTROL Automated Personalization]** (AP) y **[!UICONTROL Segmentación automática]**. Además de los métodos de [Métodos para obtener datos en Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=es){target=_blank}, en los algoritmos [!DNL Target] se usan también [!DNL Experience Cloud] audiencias compartidas (**[!UICONTROL Adobe Analytics]**, [!DNL Audience Manager]) y audiencias de informes de actividad.

Para obtener información sobre los datos que los algoritmos de personalización **[!UICONTROL Automated Personalization]** y **[!UICONTROL Segmentación automática]** recopilan y usan automáticamente, consulte [Recopilación de datos de Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Prácticas recomendadas {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

Siga estas prácticas recomendadas al cargar datos para los algoritmos de personalización de [!DNL Target]:

* Cuantos más datos de alta calidad estén disponibles para los algoritmos de personalización de [!DNL Target], mejor será la calidad de los modelos resultantes en sus actividades **[!UICONTROL Automated Personalization]** y **[!UICONTROL Segmentación automática]**.
* Limite el uso de varios scripts o atributos de perfil que tengan el mismo propósito.
* No pase un ID único, como un ID de sesión, si no es necesario.
* Revise qué datos [!DNL Target] recopila automáticamente ([Recopilación de datos para algoritmos de Personalization de Target](/help/main/c-activities/t-automated-personalization/ap-data.md)) para que no envíe información duplicada. Por ejemplo, [!DNL Target] usa direcciones IP para determinar los códigos postales de los visitantes. No es necesario pasar esta información como variable independiente.
* No pase varios valores en el mismo atributo o variable. Si se concatenan varias variables, los algoritmos de personalización de [!DNL Target] tratan cada cadena como un valor único, lo que reduce el valor de la información para la personalización.
* Use una convención de nombres significativa y fácil de recordar para que sus [informes de Personalization Insights](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md) sean más comprensibles.
