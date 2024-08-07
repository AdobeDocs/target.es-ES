---
keywords: faq;preguntas frecuentes;analytics para target;a4t;aprovisionamiento;adobe Experience Cloud
description: Encuentre respuestas a preguntas que se plantean a menudo sobre el aprovisionamiento de Analytics para  [!DNL Target] (A4T), que le permite usar los informes de Analytics para  [!DNL Target] actividades.
title: ¿Dónde puedo encontrar información sobre el aprovisionamiento inicial de A4T?
feature: Analytics for Target (A4T)
exl-id: 4b098444-3e5b-45e3-b635-1857c2c8d183
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 46%

---

# Aprovisionamiento inicial: preguntas más frecuentes sobre A4T

En este tema encontrará respuestas a preguntas que se plantean a menudo sobre el aprovisionamiento de [!DNL Adobe Analytics] como origen de informes para [!DNL Adobe Target] (A4T).

## ¿Cómo puedo configurar una actividad de A4T de varias páginas?

+++Respuesta
Para implementar un caso de uso de A4T básico de varias páginas:

* Implemente las bibliotecas JavaScript tanto para Target como para Analytics en la dirección URL o la página de aterrizaje de la actividad. Al implementar ambas soluciones, los datos de Target se acoplan con los datos de cada visitante de Analytics. Estos datos permanecen en Analytics hasta que alcanzan la fecha de caducidad predeterminada establecida en 90 días.

* Para las páginas restantes del sitio, donde solo se rastrean las métricas de Analytics, implemente Analytics en esas páginas. No es necesario implementar Target en esas páginas. Las métricas de Analytics registradas en esas páginas se vinculan automáticamente a la actividad de Target para la que el usuario estaba cualificado inicialmente, según la información de Target adjunta a ese visitante desde la viñeta anterior.

+++

## ¿Cómo puedo saber si A4T está habilitado en mi cuenta de [!DNL Target]? {#section_4437D284448F4313BF953D4B6EDBACA6}

+++Respuesta
Para poder seleccionar un grupo de informes al definir una actividad de Analytics, necesita una cuenta de usuario de Analytics y una cuenta de usuario de Target. Sus cuentas de usuario deben estar configuradas tal como se describe en la documentación. Consulte [Requisitos de permisos de usuario](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083).

Una vez que sea miembro de uno o más grupos de Experience Cloud que tienen acceso a Analytics y Target y que tenga acceso a todos los grupos de informes, debería ver la opción para crear una prueba A/B con Analytics en **[!UICONTROL Create Activity]**.

Si hay problemas de aprovisionamiento, compruebe si A4T se está aprovisionando correctamente.

+++

## ¿Por qué no se cargan los grupos de informes?   {#section_6CC8B2B3568A46C499895EB9811FDC2E}

+++Respuesta
Compruebe lo siguiente si se produce alguno de estos problemas:

* Asegúrese de que las cuentas de Analytics y Target estén vinculadas en el Experience Cloud.
* Algunos clientes utilizan varios inicios de sesión de empresa de Analytics en la misma empresa de Experience Cloud. Si utiliza varios inicios de sesión, asegúrese de que la última empresa de Analytics en la que inició sesión sea la que esté vinculada a la cuenta de Target para la integración.
* Si lleva varias horas con la sesión iniciada en Experience Cloud, en ocasiones la sesión de Analytics puede caducar. Cierre sesión y vuelva a iniciarla para intentarlo de nuevo.

+++

## ¿Por qué no veo las opciones de Analytics en Target?   {#section_EDD996AFB08B4DB196DD934BE55BF48D}

+++Respuesta
Consulte ¿Por qué no se cargan los grupos de informes? Arriba. La causa raíz de este problema es la misma.

+++

## ¿Por qué no veo los informes de A4T en Analytics?   {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

+++Respuesta
Consulte ¿Por qué no se cargan los grupos de informes? (arriba). La causa raíz de este problema es la misma.

+++

## ¿Por qué mis informes de [!DNL Target] están vacíos? {#section_3837104757464CB488C5A83014A669A1}

+++Respuesta
Consulte ¿Por qué no se cargan los grupos de informes? (arriba). La causa raíz de este problema es la misma.

+++
