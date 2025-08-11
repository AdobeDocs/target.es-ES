---
keywords: Recommendations
description: Conozca los requisitos de implementación de Analytics para  [!DNL Target] (A4T) y qué debe tener en cuenta antes de implementar esta integración.
title: ¿Qué debo saber antes de implementar A4T?
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 656f728ba890f1f5afc0404e22f6acb1a2565fe6
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 24%

---

# Antes de implementar Analytics for Target (A4T) con at.js

Se producen varios cambios en el proceso de recopilación de datos al habilitar [!DNL Adobe Analytics] como origen de informes para [!DNL Adobe Target] (A4T).

Antes de decidir utilizar esta integración, revise las siguientes secciones y tenga en cuenta el impacto en los procesos de creación de informes.

>[!NOTE]
>
>Este artículo se aplica solo a las implementaciones de at.js. Para obtener información acerca de la implementación de [!UICONTROL Analytics for Target] (A4T) con [!DNL Adobe Experience Platform Web SDK], vea el registro de [Adobe Analytics for Target (A4T) en Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/a4t/overview-a4t.html){target=_blank}.

## Requisitos de implementación {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Para poder empezar a utilizar A4T, debe solicitar el aprovisionamiento de su cuenta para la integración. Use el [Formulario de aprovisionamiento de integraciones de Marketing Cloud](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank} para solicitar el aprovisionamiento.

Esta integración con A4T requiere que implemente las siguientes versiones de las bibliotecas (o versiones más recientes), en función de si quiere redireccionar ofertas con A4T o no.

>[!NOTE]
>
>Los siguientes requisitos enumeran las *versiones mínimas* de at.js necesarias para implementar A4T. El equipo [!DNL Target] mantiene solamente dos versiones de [!DNL at.js]: la actual y la penúltima. Actualice [!DNL at.js] cuando sea posible para garantizar que dispone de una versión compatible. Para obtener información detallada sobre los cambios en cada versión de at.js, consulte [Detalles de las versiones de at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=es){target=_blank}.

### Requisitos necesarios si *no* se utilizan ofertas de redireccionamiento con A4T

Esta integración requiere que implemente las siguientes versiones de la biblioteca (o versiones más recientes) si no planea utilizar ofertas de redireccionamiento con A4T. El orden de la lista es el orden de las operaciones.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versión 1.8.0
* [!DNL Adobe Target]: versión 0.9.1 de at.js
* Adobe Analytics: appMeasurement.js versión 1.7.0

Para obtener información sobre la implementación de A4T con [!DNL Platform Web SDK], consulte [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=es){target=_blank}.

### Requisitos necesarios si se utilizan ofertas de redireccionamiento con A4T

Para utilizar ofertas de redireccionamiento con A4T, debe implementar las siguientes versiones de la biblioteca (o más recientes). El orden de la lista es el orden de las operaciones.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versión 2.3.0

  >[!NOTE]
  >
  >Las versiones de at.js 1.8.0 y posteriores, así como at.js 2.x y posteriores, ya no funcionan con versiones de la API de visitante anteriores a la 2.5.0 para pasar parámetros de Adobe Audience Manager (AAM).

* [!DNL Adobe Target]: versión 1.6.2 de at.js

* Adobe Analytics: appMeasurement.js versión 2.1

Las instrucciones de descarga e implementación se enumeran en [Implementación de Analytics para Target](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

Para obtener información sobre la implementación de A4T con [!DNL Platform Web SDK], consulte [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=es){target=_blank}.

## Cosas que hay que saber antes de implementar {#section_50D49CC52E11414089C89FB67F9B88F5}

* Esta integración está habilitada en las nuevas actividades cuando selecciona usar [!DNL Analytics] como fuente de informes. Después de completar los cambios de implementación descritos en este documento, las actividades existentes no se verán afectadas.
* El proceso de configurar [!DNL Analytics] como el origen de informes de [!DNL Target] incluye varios pasos de implementación, seguidos de un paso de aprovisionamiento. Le recomendamos que lea todo el proceso que se describe a continuación antes de comenzar la implementación. Después de completar estos pasos, está listo para usar [!DNL Analytics] como fuente de informes cuando esté habilitado para usted. El proceso de aprovisionamiento puede tardar hasta cinco días hábiles.
* El [!DNL Visitor ID service] crea un(a) [!DNL Visitor ID] compartido(a) en el(la) [!DNL Adobe Experience Cloud]. Aunque no reemplaza el id de mboxPC [!DNL Target] ni el UUID [!DNL Audience Manager], sí reemplaza la forma en que [!DNL Analytics] identifica a los nuevos visitantes. Si se configura correctamente, los visitantes que regresan [!DNL Analytics] también se deben identificar mediante su ID de [!DNL Analytics] antiguo. Del mismo modo, como el mboxPCid [!DNL Target] permanece intacto, no se pierden datos del perfil del visitante [!DNL Target] al actualizar a [!DNL Visitor ID service].
* [!DNL Visitor ID service] debe ejecutarse antes del código de página [!DNL Analytics] y [!DNL Target]. Asegúrese de que `VisitorAPI.js` aparece encima de las etiquetas del resto de las soluciones de [!DNL Experience Cloud].

## Latencia {#section_9489BE6FD21641A4844E591711E3F813}

Después de habilitar esta integración, se apreciará una latencia adicional de 5 a 10 minutos en [!DNL Analytics]. Este aumento de la latencia permite almacenar los datos de [!DNL Analytics] y [!DNL Target] en la misma visita, lo que le permite desglosar las actividades por página y sección de sitio.

Este aumento se ve reflejado en todos los servicios y herramientas de [!DNL Analytics], incluidos los informes de flujo en vivo y en tiempo real, y se aplica a los siguientes escenarios:

* Para el flujo en directo, los informes en tiempo real, las solicitudes de la API y todos los datos actuales para las variables de tráfico, solo se retrasan las visitas con un ID de datos suplementario.
* Para los datos actuales en las métricas de conversión, los datos finalizados y las fuentes de datos, todas las visitas se retrasan de 5 a 7 minutos más.

El aumento de la latencia comienza después de implementar el servicio de ID de visitante [!DNL Experience Cloud], aunque no haya implementado correctamente esta integración.

## ID suplementario.  {#section_2C1F745A2B7D41FE9E30915539226E3A}

Todas las llamadas de [!DNL Target] utilizadas por una actividad de A4T para entregar contenido o registrar la métrica de objetivo deben tener una visita de [!DNL Analytics] correspondiente que comparta el ID suplementario para A4T para funcionar correctamente.

Las visitas que contienen datos de [!DNL Analytics] y [!DNL Target] contienen un id. de datos suplementario. Puede ver este identificador en [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) como el parámetro `sdid`. Por ejemplo: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Este ID se genera cada vez que se cumplen los siguientes criterios:

* Se ha implementado el servicio de ID de visitante.

Cuando [solucione problemas](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), asegúrese de confirmar que el ID suplementario esté presente en [!DNL Analytics] visitas.

## Registro de Analytics en el cliente {#client-side}

Si at.js, [!DNL Experience Cloud Visitor ID Service] y appMeasurement.js están en la página, [!DNL Analytics] y [!DNL Target] vinculan correctamente eventos para fines de informes y análisis en el backend, siempre y cuando se incluya el ID suplementario correcto desde la página. No es necesario que administre y realice operaciones adicionales para A4T para funcionar correctamente.

Hay casos en los que es posible que desee tener más control sobre cuándo y cómo enviar datos de análisis relacionados con [!DNL Target] a [!DNL Analytics] con fines de creación de informes. Es posible que tenga una herramienta de análisis interna que utilice con fines internos. Sin embargo, también desea enviar los datos de análisis a [!DNL Analytics] a través del producto de análisis interno para que otros miembros de su organización puedan seguir usando [!DNL Analytics] como fuente de informes visual. Consulte [Paso 7: Agregar la referencia de at.js a todas las páginas del sitio](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) en *Implementación de Analytics para Target* para obtener más información.

## Audiencias compartidas

Al rellenar el [Formulario de aprovisionamiento de integraciones de Marketing Cloud](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}, tenga en cuenta la siguiente información importante acerca de la opción [!UICONTROL Shared Audiences] que aparece en &quot;[!UICONTROL For which capabilities are you requesting provisioning]?&quot;

![Formulario de solicitud](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

Al solicitar [!UICONTROL Shared Audiences], habilita [!UICONTROL Target] y [!UICONTROL Adobe Audience Manager] (AAM) para compartir información, en este caso audiencias.

>[!IMPORTANT]
>
>Esta integración entre [!UICONTROL Target] y AAM conlleva costos adicionales. Se le factura por cada llamada de [!UICONTROL Target] en AAM.
