---
keywords: Recommendations
description: Conozca los requisitos de implementación de Analytics para [!DNL Target] (A4T) y qué considerar antes de implementar esta integración.
title: ¿Qué debo saber antes de implementar A4T?
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 30%

---

# Antes de implementar Analytics for Target (A4T) con at.js

Al habilitar la recopilación de datos, se producen varios cambios en el proceso [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T).

Antes de decidir si usará esta integración, lea el contenido de estas secciones y tenga en cuenta el impacto en sus procesos de creación de informes.

>[!NOTE]
>
>Este artículo se aplica solo a las implementaciones de at.js.

## Requisitos de implementación {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Para poder empezar a utilizar A4T, debe solicitar el aprovisionamiento de su cuenta para la integración. Utilice el [Formulario de aprovisionamiento de integraciones de Marketing Cloud](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank} para solicitar el aprovisionamiento.

Esta integración con A4T requiere que implemente las siguientes versiones de las bibliotecas (o versiones más recientes), en función de si quiere redireccionar ofertas con A4T o no.

>[!NOTE]
>
>Los siguientes requisitos enumeran las *minimum* Las versiones de at.js necesarias para implementar A4T. El [!DNL Target] El equipo de mantiene solo dos versiones de [!DNL at.js]: la versión actual y la segunda versión más reciente. Actualice [!DNL at.js] cuando sea posible para garantizar que dispone de una versión compatible. Para obtener información detallada sobre los cambios en cada versión de at.js, consulte [Detalles de las versiones de at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}.

### Requisitos necesarios si *no* se utilizan ofertas de redireccionamiento con A4T

Esta integración requiere que implemente las siguientes versiones de la biblioteca (o versiones más recientes) si no planea utilizar ofertas de redireccionamiento con A4T. El orden de la lista es el orden de las operaciones.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versión 1.8.0
* [!DNL Adobe Target]: Versión 0.9.1 de at.js
* Adobe Analytics: appMeasurement.js versión 1.7.0

Para obtener información sobre la implementación de A4T con [!DNL Platform Web SDK], consulte [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

### Requisitos necesarios si se utilizan ofertas de redireccionamiento con A4T

Para utilizar ofertas de redireccionamiento con A4T, debe implementar las siguientes versiones de la biblioteca (o más recientes). El orden de la lista es el orden de las operaciones.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versión 2.3.0

   >[!NOTE]
   >
   >Las versiones de at.js 1.8.0 y posteriores, así como at.js 2.x y posteriores, ya no funcionan con versiones de la API de visitante anteriores a la 2.5.0 para pasar parámetros de Adobe Audience Manager (AAM).

* [!DNL Adobe Target]: Versión 1.6.2 de at.js

* Adobe Analytics: appMeasurement.js versión 2.1

Las instrucciones de descarga e implementación se enumeran en [Implementación de Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

Para obtener información sobre la implementación de A4T con [!DNL Platform Web SDK], consulte [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

## Cosas que hay que saber antes de implementar {#section_50D49CC52E11414089C89FB67F9B88F5}

* Esta integración se activa en las nuevas actividades cuando selecciona usar [!DNL Analytics] como fuente de informes. Después de completar los cambios de implementación descritos en este documento, las actividades existentes no se verán afectadas.
* El proceso de configuración [!DNL Analytics] como fuente de informes para [!DNL Target] incluye varios pasos de implementación, seguidos de un paso de aprovisionamiento. Le recomendamos que lea todo el proceso que se describe a continuación antes de comenzar la implementación. Después de completar estos pasos, está listo para usar [!DNL Analytics] como fuente de informes cuando esté habilitada. El proceso de aprovisionamiento puede tardar hasta cinco días hábiles.
* El [!DNL Visitor ID service] crea un recurso compartido [!DNL Visitor ID] a través de [!DNL Adobe Experience Cloud]. Aunque no reemplaza al [!DNL Target] id de mboxPC o [!DNL Audience Manager] UUID, reemplaza la forma [!DNL Analytics] identifica nuevos visitantes. Si se configura correctamente, volver [!DNL Analytics] los visitantes también deben identificarse a través de su antiguo [!DNL Analytics] ID. Del mismo modo, debido a que la variable [!DNL Target] mboxPCid permanece intacto, no [!DNL Target] los datos del perfil del visitante se pierden al actualizar a [!DNL Visitor ID service].
* El [!DNL Visitor ID service] debe ejecutarse antes de que [!DNL Analytics] y [!DNL Target] código de página. Asegúrese de que `VisitorAPI.js` aparece encima de las etiquetas del resto de [!DNL Experience Cloud] soluciones.

## Latencia {#section_9489BE6FD21641A4844E591711E3F813}

Después de habilitar esta integración, experimentará 5-10 minutos más de latencia en [!DNL Analytics]. Este aumento de latencia permite el uso de datos de [!DNL Analytics] y [!DNL Target] se almacenarán en la misma visita, lo que le permite desglosar las actividades por página y sección de sitio.

Este aumento se refleja en todos los [!DNL Analytics] servicios y herramientas, incluidos los informes de flujo en directo y en tiempo real, y se aplica en los siguientes casos:

* Para el flujo en directo, los informes en tiempo real, las solicitudes de la API y todos los datos actuales para las variables de tráfico, solo se retrasan las visitas con un ID de datos suplementario.
* Para los datos actuales en las métricas de conversión, los datos finalizados y las fuentes de datos, todas las visitas se retrasan de 5 a 7 minutos más.

El aumento de la latencia se da después de implementar el [!DNL Experience Cloud] servicio de ID de visitante aunque no haya implementado completamente esta integración.

## ID suplementario.  {#section_2C1F745A2B7D41FE9E30915539226E3A}

Todo [!DNL Target] las llamadas que utiliza una actividad de A4T para entregar contenido o registrar la métrica de objetivo deben tener un correspondiente [!DNL Analytics] visita de que comparte el ID suplementario para A4T con el fin de funcionar correctamente.

Visitas que contienen datos de [!DNL Analytics] y [!DNL Target] contener un ID de datos suplementario. Puede ver este ID en la [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) como el `sdid` parámetro. Por ejemplo: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Este ID se genera cada vez que se cumplen los siguientes criterios:

* Se ha implementado el servicio de ID de visitante.

Cuándo [solución de problemas](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), asegúrese de que el ID suplementario esté presente en [!DNL Analytics] visitas.

## Registro de Analytics en el lado del cliente {#client-side}

Si at.js, la variable [!DNL Experience Cloud Visitor ID Service]y appMeasurement.js se encuentran en la página, [!DNL Analytics], y [!DNL Target] vincula correctamente eventos para fines de informes y análisis en el backend, siempre y cuando se incluya el ID suplementario correcto desde la página. No es necesario que administre y realice operaciones adicionales para A4T para funcionar correctamente.

Hay casos en los que es posible que desee tener más control sobre cuándo y cómo enviar datos de análisis relacionados con [!DNL Target] hasta [!DNL Analytics] para fines de informes. Es posible que tenga una herramienta de análisis interna que utilice con fines internos. Sin embargo, también desea enviar los datos de análisis a [!DNL Analytics] a través de su producto interno de analytics para que otros miembros de su organización puedan seguir utilizando [!DNL Analytics] como fuente de informes visual. Consulte [Paso 7: Agregar la referencia de at.js a todas las páginas del sitio](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) in *Implementación de Analytics for Target* para obtener más información.

## Audiencias compartidas

Al rellenar el [Formulario de aprovisionamiento de integraciones de Marketing Cloud](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}, tenga en cuenta la siguiente información importante relativa a [!UICONTROL Audiencias compartidas] opción enumerada en &quot;[!UICONTROL ¿Para qué capacidades solicita aprovisionamiento?]?&quot;

![Formulario de solicitud](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

Al solicitar [!UICONTROL Audiencias compartidas], habilite [!UICONTROL Target] y [!UICONTROL Adobe Audience Manager] AAM () para compartir información, en este caso audiencias.

>[!IMPORTANT]
>
>Esta integración entre [!UICONTROL Target] AAM y viene con costes adicionales. Se le factura por cada [!UICONTROL Target] AAM llame a en el servicio de atención al cliente.
