---
keywords: Recommendations
description: Cuando se habilita Analytics como fuente de informes para Target (A4T), se producen varios cambios en el proceso de recopilación de datos.
title: Antes de implementar Adobe Analytics como fuente de sistema de informes para Adobe Target (A4T)
feature: a4t implementation
uuid: fe603a4b-bd61-49f4-b1b7-a0329aa905f5
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 53%

---


# Antes de la implementación{#before-you-implement}

Several changes occur in your data collection process when enabling [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

Antes de decidir si usará esta integración, lea el contenido de estas secciones y tenga en cuenta el impacto en sus procesos de creación de informes:

## Requisitos de implementación {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Antes de empezar a usar A4T, debe solicitar el aprovisionamiento de su cuenta para la integración. Utilice el formulario [de aprovisionamiento de integraciones de](https://www.adobe.com/go/audiences) Marketing Cloud para solicitar el aprovisionamiento.

Esta integración con A4T requiere que implemente las siguientes versiones de las bibliotecas (o versiones más recientes), en función de si quiere redireccionar ofertas con A4T o no:

### Requisitos necesarios si *no* se utilizan ofertas de redireccionamiento con A4T

Esta integración requiere que implemente las siguientes versiones de la biblioteca (o versiones más recientes) si no planea utilizar ofertas de redireccionamiento con A4T. El orden de la lista es el orden de las operaciones.

* [!DNL Experience Cloud Visitor ID Service]:: visitorAPI.js versión 1.8.0
* [!DNL Adobe Target] (según su implementación): at.js versión 0.9.1 o mbox.js versión 61
* Adobe Analytics: appMeasurement.js versión 1.7.0

### Requisitos necesarios si se utilizan ofertas de redireccionamiento con A4T

Para utilizar ofertas de redireccionamiento con A4T, debe implementar las siguientes versiones de la biblioteca (o más recientes). El orden de la lista es el orden de las operaciones.

* [!DNL Experience Cloud Visitor ID Service]:: visitorAPI.js versión 2.3.0
* [!DNL Adobe Target]:: Versión 1.6.2 de at.js

   **Nota:** La biblioteca mbox.js no admite ofertas de redireccionamiento con A4T. La implementación debe utilizar at.js.

* Adobe Analytics: appMeasurement.js versión 2.1

Download and deployment instructions are listed in [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Cosas que hay que saber antes de implementar {#section_50D49CC52E11414089C89FB67F9B88F5}

* This integration is enabled on new activities when you select to use [!DNL Analytics] as the reporting source. Después de completar los cambios de implementación descritos en este documento, las actividades existentes no se verán afectadas.
* The process of setting up [!DNL Analytics] as the reporting source for [!DNL Target] includes several implementation steps, followed by a provisioning step. Le recomendamos que lea todo el proceso que se describe a continuación antes de comenzar la implementación. After you complete these steps, you will be ready to use [!DNL Analytics] as your reporting source as soon as it is enabled for you. El proceso de aprovisionamiento puede tardar hasta cinco días hábiles.
* El [!DNL Visitor ID service] crea un elemento compartido [!DNL Visitor ID] en el [!DNL Adobe Experience Cloud]. Although it does not replace the [!DNL Target] mboxPC id or [!DNL Audience Manager] UUID, it does replace the way [!DNL Analytics] identifies new visitors. If set up properly, returning [!DNL Analytics] visitors should also be identified via their old [!DNL Analytics] ID to prevent visitor cliffing. Similarly, because the [!DNL Target] mboxPCid remains intact, no [!DNL Target] visitor profile data is lost when you upgrade to the [!DNL Visitor ID service].
* El [!DNL Visitor ID service] debe ejecutarse antes del código [!DNL Analytics] de página y [!DNL Target] . Make sure that `VisitorAPI.js` appears above the tags for all other [!DNL Experience Cloud] solutions.

## Latencia {#section_9489BE6FD21641A4844E591711E3F813}

Después de activar esta integración, se apreciará una latencia adicional de 5 a 10 minutos en [!DNL Analytics]. This latency increase allows data from [!DNL Analytics] and [!DNL Target] to be stored on the same hit, allowing you to break down activities by page and site section.

This increase is reflected in all [!DNL Analytics] services and tools, including the live-stream and real-time reporting, and applies in the following scenarios:

* Para el flujo en directo, los informes en tiempo real, las solicitudes de la API y todos los datos actuales para las variables de tráfico, solo se retrasan las visitas con un ID de datos suplementario.
* Para los datos actuales en las métricas de conversión, los datos finalizados y las fuentes de datos, todas las visitas se retrasan de 5 a 7 minutos más.

Be aware that the latency increase starts after you implement the [!DNL Experience Cloud] visitor ID service, even if you have not fully implemented this integration.

## ID suplementario.  {#section_2C1F745A2B7D41FE9E30915539226E3A}

All [!DNL Target] calls used by an A4T activity to deliver content or record the goal metric must have a corresponding [!DNL Analytics] hit that shares the same supplemental ID for A4T to work properly.

Hits that contain data from [!DNL Analytics] and [!DNL Target] contain a supplemental data ID. You can see this ID in the [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) as the `sdid` parameter. Por ejemplo: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Este ID se genera cada vez que se cumplen los siguientes criterios:

* Se ha implementado el servicio de ID de visitante.
* Se ha implementado una versión de [!DNL mbox.js] que admite esta integración.

When [troubleshooting](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), be sure to confirm that the supplemental ID is present on [!DNL Analytics] hits.

## Registro de Analytics en el lado del cliente {#client-side}

De forma predeterminada, cuando at.js, [!DNL Experience Cloud Visitor ID Service] y appMeasurement.js están en la página, [!DNL Analytics] y [!DNL Target] unen correctamente eventos para fines de informes y análisis en el backend, siempre y cuando se incluya el ID suplementario correcto desde la página, como se mencionó arriba. No tendrá que gestionar y realizar operaciones adicionales para A4T para funcionar correctamente.

Sin embargo, existen casos en los que es posible que desee tener más control sobre cuándo y cómo enviar datos de análisis relacionados con [!DNL Target] a [!DNL Analytics] para realizar informes. Puede que tenga una herramienta de análisis interna que aproveche con fines internos pero también desee enviar los datos de análisis a [!DNL Analytics] través del producto de análisis interno para que otros miembros de su organización puedan seguir utilizando [!DNL Analytics] como fuente de informes visual. Consulte [Paso 7: Agregar la referencia de at.js o mbox.js a todas las páginas del sitio](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) en *Implementación de Analytics para Target* para obtener más información.

## Audiencias compartidas

Al rellenar el formulario [de aprovisionamiento de integraciones de](https://www.adobe.com/go/audiences)Marketing Cloud, tenga en cuenta la siguiente información importante sobre la opción de Audiencias  compartidas que aparece en la sección &quot;¿[!UICONTROL Para qué capacidades solicita el aprovisionamiento]?&quot;

![Formulario de solicitud](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

Cuando solicita Audiencias compartidas, habilita [!UICONTROL Destinatario] y [!UICONTROL Adobe Audience Manager] (AAM) para compartir información, en este caso audiencias.

>[!IMPORTANT]
>
>Esta integración entre [!UICONTROL Destinatario] y AAM conlleva costes adicionales. Se le facturará por cada llamada de [!UICONTROL Destinatario] en AAM.
