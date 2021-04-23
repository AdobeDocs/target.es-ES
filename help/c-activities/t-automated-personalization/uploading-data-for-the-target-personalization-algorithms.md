---
keywords: Automated Personalization;ap;cargar datos;datos sin conexión;algoritmo de personalización;segmentación automática;prácticas recomendadas
description: Aprenda a cargar datos sin conexión, como información de CRM, al crear modelos de personalización en actividades de Adobe [!DNL Target] Automated Personalization (AP).
title: ¿Cómo puedo cargar datos para algoritmos de personalización?
feature: Personalización automatizada
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 75%

---

# Carga de datos para los algoritmos de personalización [!DNL Target]

Los datos sin conexión, como la información CRM o las puntuaciones de inclinación de cancelación por parte del cliente, pueden ser muy valiosos al crear modelos de personalización en actividades [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP).

Hay muchas maneras de introducir datos en los algoritmos de personalización de [!UICONTROL Personalización automatizada](AP) y de [!UICONTROL Segmentación automática. ] Además de los métodos indicados en   [Métodos para obtener los datos en Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17), en nuestros algoritmos también utilizamos las audiencias compartidas de Experience Cloud (Adobe Analytics, Gestión de público) y las audiencias de informes de actividad.

Para obtener información sobre los datos que los algoritmos de Personalización automatizada y de Segmentación automática recopilan y utilizan automáticamente, consulte [Recopilación de datos de personalización automatizada](/help/c-activities/t-automated-personalization/ap-data.md).

## Prácticas recomendadas {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

En la siguiente lista se presentan prácticas recomendadas para la carga de datos en los algoritmos de personalización de Target:

* Cuantos más datos de calidad tengan a su disposición los algoritmos de personalización de Target, mayor será la calidad de los modelos resultantes en las actividades de AP y Segmentación automática.
* Limite el uso de múltiples scripts de perfil y atributos que tengan el mismo propósito.
* No pase ID únicos (como un ID de sesión) si no es necesario.
* Revise qué datos recopila Target automáticamente (   [Recopilación de datos para los algoritmos de personalización de Target](/help/c-activities/t-automated-personalization/ap-data.md)) con el fin de no enviar información duplicada. Por ejemplo: Target utiliza direcciones IP para determinar el código postal de los visitantes. No es necesario pasar esta información como variable independiente.
* No pase varios valores en el mismo atributo o variable. Si se concatenan múltiples variables, los algoritmos de personalización de Target tratan cada cadena como un valor único, lo que reduce el valor de la información para la personalización.
* Utilice una nomenclatura significativa y fácil de recordar para que los   [Informes de Perspectivas de personalización](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) resulten más comprensibles.
