---
description: Los datos sin conexión, como información de CRM o puntuaciones de inclinación de cancelación por parte del cliente, pueden ser muy valiosos al crear modelos de personalización.
seo-description: Los datos sin conexión, como información de CRM o puntuaciones de inclinación de cancelación por parte del cliente, pueden ser muy valiosos al crear modelos de personalización.
seo-title: Carga de datos para los algoritmos de personalización de Target
solution: Target
title: Carga de datos para los algoritmos de personalización de Target
topic: Premium
uuid: eb0938b9-7f35-4bb5-ac4b-260b2144db5b
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Carga de datos para los algoritmos de personalización de Target{#upload-data-for-target-s-personalization-algorithms}

Los datos sin conexión, como información de CRM o puntuaciones de inclinación de cancelación por parte del cliente, pueden ser muy valiosos al crear modelos de personalización.

Hay muchas maneras de introducir datos en los algoritmos de personalización de Personalización automatizada(AP) y de Segmentación automática. Además de los métodos indicados en  [Métodos para obtener los datos en Target](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17), en nuestros algoritmos también utilizamos las audiencias compartidas de Experience Cloud (Adobe Analytics, Gestión de público) y las audiencias de informes de actividad.

Para obtener información sobre los datos que los algoritmos de Personalización automatizada y de Segmentación automática recopilan y utilizan automáticamente, consulte [Recopilación de datos de personalización automatizada](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

## Prácticas recomendadas {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

En la siguiente lista se presentan prácticas recomendadas para la carga de datos en los algoritmos de personalización de Target:

* Cuantos más datos de calidad tengan a su disposición los algoritmos de personalización de Target, mayor será la calidad de los modelos resultantes en las actividades de AP y Segmentación automática.
* Limite el uso de múltiples scripts de perfil y atributos que tengan el mismo propósito.
* No pase ID exclusivos (como un ID de sesión) si no es necesario.
* Revise qué datos recopila Target automáticamente (  [Recopilación de datos para los algoritmos de personalización de Target](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058)) con el fin de no enviar información duplicada. Por ejemplo: Target utiliza direcciones IP para determinar el código postal de los visitantes. No es necesario pasar esta información como variable independiente.
* No pase varios valores en el mismo atributo o variable. Si se concatenan múltiples variables, los algoritmos de personalización de Target tratan cada cadena como un valor exclusivo, lo que reduce el valor de la información para la personalización.
* Utilice una nomenclatura significativa y fácil de recordar para que los  [Informes de Perspectivas de personalización](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) resulten más comprensibles.

