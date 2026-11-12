---
keywords: url de actividad;url;url diferente
description: Descubra cómo establecer la [!UICONTROL URL de actividad] en una actividad A/B, de segmentación de experiencias o de prueba multivariable para definir páginas de prueba y garantizar un diseño de prueba preciso.
title: ¿Qué es la URL de actividad en una actividad A/B, de segmentación de experiencias o de prueba multivariable?
feature: A/B Tests
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
reason: republish
TQID: 'https://experienceleague.adobe.com/arQWsSfBKYtrayq9AI8ejU1T-Uor-oL5j2Sp2JKKXZE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: aad553690f1f399177214c94a2276d038f46d9cb
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 25%
---
# Dirección URL de actividad {#ab-activity-url}

>[!BEGINSHADEBOX]

**En esta página:** Obtenga información sobre cómo especificar la dirección URL de actividad de una actividad A/B, de segmentación de experiencias (XT) o de prueba multivariable (MVT), cómo mostrar una página diferente y cómo agregar reglas para más páginas o secciones.

>[!ENDSHADEBOX]

La [!UICONTROL URL de actividad] determina la página que se usa en la actividad. Esta es la página que se abre en [!UICONTROL Compositor de experiencias visuales] (VEC) o en [!UICONTROL Compositor de experiencias basadas en formularios] cuando la actividad está diseñada en [!DNL Adobe Target].

## Especifique la URL de la actividad {#specify-url}

Cuando se le pida durante la creación de la actividad, indique la dirección URL de la actividad. Escriba la dirección URL completa (incluido `https://`) y haga clic en **[!UICONTROL Crear]**.

>[!NOTE]
>
>[!DNL Target] no diferencia entre los protocolos de URL ([!DNL https] y [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] y [!DNL `https://www.adobe.com`] coinciden.

Si especifica una dirección URL para un sitio que no incluye la biblioteca JavaScript [!DNL Target] [at.js o  [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html){target=_blank}, no podrá seleccionar elementos de página.

## Mostrar una página diferente {#different-page}

De manera predeterminada, el VEC o el [Compositor de experiencias basadas en formularios](/help/main/c-experiences/form-experience-composer.md) abre la página que se ha especificado en la [configuración del Compositor de experiencias visuales](/help/main/administrating-target/visual-experience-composer-set-up.md). Puede especificar una página diferente durante la creación de la actividad.

Para mostrar una página diferente después de que se abra el VEC:

1. En la página **[!UICONTROL Experiencias]**, haga clic en **[!UICONTROL Configurar]** en la parte superior de la página y, a continuación, seleccione **[!UICONTROL Entrega de páginas]**.

1. Especifique la dirección URL en el campo **[!UICONTROL URL]**.

1. Haga clic en **[!UICONTROL Guardar]** cuando haya finalizado.

De manera predeterminada, el VEC no permite realizar cambios en elementos que contengan JavaScript, como banners giratorios. Puede desactivar **[!UICONTROL Render usando JavaScript]** si desea poder modificar esos elementos usando el VEC.

>[!NOTE]
>
>Si cambia la dirección URL después de realizar cambios en una página para una o más experiencias, la experiencia se restablecerá con la nueva página y se perderán los cambios que haya realizado.

## Agregar reglas para más páginas o secciones {#add-rules}

Para agregar más páginas o secciones a la actividad, haz clic en **[!UICONTROL Agregar regla]** en la configuración de **[!UICONTROL Entrega de páginas]** y, a continuación, haz clic en **[!UICONTROL Guardar]** cuando hayas finalizado.

Las reglas adicionales pueden basarse en cualquiera de los siguientes aspectos:

* Dirección URL
* Dominio
* Ruta
* Fragmento hash (#)
* Consulta
* Parámetro de mbox
* Personalizado

Se pueden unir reglas adicionales a la dirección URL de la actividad con AND u OR. Todas las reglas que agregue se evalúan entre sí con Y.
