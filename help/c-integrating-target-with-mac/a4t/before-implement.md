---
keywords: Recomendaciones
description: Conozca los requisitos de implementación de Analytics para [!DNL Target] (A4T) y qué debe tener en cuenta antes de implementar esta integración.
title: ¿Qué Debo Saber Antes De Implementar A4T?
feature: 'Analytics for Target (A4T) '
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 8c0cdfbe02e9159cf8348e68a782a4268a8df687
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Antes de implementar Analytics for Target (A4T) con at.js

Se producen varios cambios en el proceso de recopilación de datos al habilitar [!DNL Adobe Analytics] como fuente de informes para [!DNL Adobe Target] (A4T).

Antes de decidir si usará esta integración, lea el contenido de estas secciones y tenga en cuenta el impacto en sus procesos de creación de informes.

>[!NOTE]
>
>Este artículo se aplica solo a implementaciones de at.js .

## Requisitos de implementación {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Antes de empezar a usar A4T, debe solicitar que su cuenta esté aprovisionada para la integración. Utilice el [Formulario de aprovisionamiento de integraciones de Marketing Cloud](https://www.adobe.com/go/audiences) para solicitar el aprovisionamiento.

Esta integración con A4T requiere que implemente las siguientes versiones de las bibliotecas (o versiones más recientes), en función de si quiere redireccionar ofertas con A4T o no:

### Requisitos necesarios si *no* se utilizan ofertas de redireccionamiento con A4T

Esta integración requiere que implemente las siguientes versiones de la biblioteca (o versiones más recientes) si no planea utilizar ofertas de redireccionamiento con A4T. El orden de la lista es el orden de las operaciones.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versión 1.8.0
* [!DNL Adobe Target] (según su implementación): at.js versión 0.9.1 o mbox.js versión 61
* Adobe Analytics: appMeasurement.js versión 1.7.0

### Requisitos necesarios si se utilizan ofertas de redireccionamiento con A4T

Para utilizar ofertas de redireccionamiento con A4T, debe implementar las siguientes versiones de la biblioteca (o más recientes). El orden de la lista es el orden de las operaciones.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versión 2.3.0

   **Nota:**  at.js 1.8.0 o superior ya no funciona con versiones de API de visitante anteriores a la 2.5.0 para pasar parámetros  [!DNL Adobe Audeince Manager] (AAM).

* [!DNL Adobe Target]: Versión 1.6.2 de at.js

   **Nota**: La biblioteca mbox.js no admite ofertas de redireccionamiento con A4T. La implementación debe utilizar at.js.

* Adobe Analytics: appMeasurement.js versión 2.1

Las instrucciones de descarga e implementación se enumeran en [Implementación de Analytics para Target](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Cosas que hay que saber antes de implementar {#section_50D49CC52E11414089C89FB67F9B88F5}

* Esta integración se habilita en las nuevas actividades cuando selecciona usar [!DNL Analytics] como fuente de informes. Después de completar los cambios de implementación descritos en este documento, las actividades existentes no se verán afectadas.
* El proceso de configuración de [!DNL Analytics] como fuente de informes para [!DNL Target] incluye varios pasos de implementación, seguidos de un paso de aprovisionamiento. Le recomendamos que lea todo el proceso que se describe a continuación antes de comenzar la implementación. Después de completar estos pasos, estará listo para usar [!DNL Analytics] como fuente de informes cuando esté habilitada para usted. El proceso de aprovisionamiento puede tardar hasta cinco días hábiles.
* El [!DNL Visitor ID service] crea un [!DNL Visitor ID] compartido en el [!DNL Adobe Experience Cloud]. Aunque no reemplaza el [!DNL Target] mboxPC id ni el [!DNL Audience Manager] UUID, sí reemplaza la forma en que [!DNL Analytics] identifica a los nuevos visitantes. Si se configura correctamente, los visitantes que regresan [!DNL Analytics] también deben identificarse mediante su ID [!DNL Analytics] anterior. Del mismo modo, como el mboxPCid [!DNL Target] permanece intacto, no se pierden datos de perfil del visitante [!DNL Target] al actualizar a [!DNL Visitor ID service].
* El [!DNL Visitor ID service] debe ejecutarse antes del código de página [!DNL Analytics] y [!DNL Target]. Asegúrese de que `VisitorAPI.js` aparece encima de las etiquetas para todas las demás soluciones [!DNL Experience Cloud].

## Latencia {#section_9489BE6FD21641A4844E591711E3F813}

Una vez habilitada esta integración, experimentará una latencia adicional de 5 a 10 minutos en [!DNL Analytics]. Este aumento de la latencia permite almacenar los datos de [!DNL Analytics] y [!DNL Target] en la misma visita, lo que le permite desglosar las actividades por página y por sección de sitio.

Este aumento se refleja en todos los servicios y herramientas de [!DNL Analytics], incluidos el flujo en directo y los informes en tiempo real, y se aplica en los siguientes escenarios:

* Para el flujo en directo, los informes en tiempo real, las solicitudes de la API y todos los datos actuales para las variables de tráfico, solo se retrasan las visitas con un ID de datos suplementario.
* Para los datos actuales de las métricas de conversión, los datos finalizados y las fuentes de datos, todas las visitas se retrasan de 5 a 7 minutos más.

El aumento de la latencia se da después de implementar el servicio de ID de visitante [!DNL Experience Cloud], incluso aunque no haya implementado correctamente esta integración.

## ID suplementario.  {#section_2C1F745A2B7D41FE9E30915539226E3A}

Todas las llamadas [!DNL Target] utilizadas por una actividad de A4T para ofrecer contenido o registrar la métrica de objetivos deben tener una visita [!DNL Analytics] correspondiente que comparta el ID suplementario para A4T para que funcione correctamente.

Las visitas que contienen datos de [!DNL Analytics] y [!DNL Target] contienen un ID de datos suplementario. Puede ver este ID en [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) como parámetro `sdid`. Por ejemplo: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Este ID se genera cada vez que se cumplen los siguientes criterios:

* Se ha implementado el servicio de ID de visitante.
* Se ha implementado una versión de [!DNL mbox.js] que admite esta integración.

Cuando [solucione problemas](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), asegúrese de que el ID suplementario esté presente en las visitas [!DNL Analytics].

## Registro de Analytics en el lado del cliente {#client-side}

Si at.js, [!DNL Experience Cloud Visitor ID Service] y appMeasurement.js están en la página, [!DNL Analytics] y [!DNL Target] vinculan correctamente eventos para fines de informes y análisis en el backend, siempre y cuando se incluya el ID suplementario correcto desde la página. No es necesario administrar y realizar operaciones adicionales para A4T para funcionar correctamente.

Hay casos en los que es posible que desee tener más control sobre cuándo y cómo enviar datos de análisis relacionados con [!DNL Target] a [!DNL Analytics] con fines de informes. Es posible que tenga una herramienta de análisis interna que utilice con fines internos. Sin embargo, también desea enviar los datos de análisis a [!DNL Analytics] mediante el producto de análisis interno para que otros miembros de su organización puedan seguir utilizando [!DNL Analytics] como fuente de informes visual. Consulte [Paso 7: Agregar la referencia de at.js o mbox.js a todas las páginas del sitio](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) en *Implementación de Analytics para Target* para obtener más información.

## Audiencias compartidas

Al rellenar el [Formulario de aprovisionamiento de integraciones de Marketing Cloud](https://www.adobe.com/go/audiences), tenga en cuenta la siguiente información importante sobre la opción [!UICONTROL Audiencias compartidas] que aparece en &quot;[!UICONTROL ¿Para qué funcionalidades solicita el aprovisionamiento]?&quot;

![Formulario de solicitud](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

Cuando solicita [!UICONTROL Audiencias compartidas], habilita [!UICONTROL Target] y [!UICONTROL Adobe Audience Manager] (AAM) para compartir información, en este caso audiencias.

>[!IMPORTANT]
>
>Esta integración entre [!UICONTROL Target] y AAM incluye costes adicionales. Se le facturan todas las llamadas de [!UICONTROL Target] en AAM.
