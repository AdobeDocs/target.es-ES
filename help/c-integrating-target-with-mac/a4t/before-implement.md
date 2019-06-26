---
description: Cuando se habilita Analytics como fuente de informes para Target (A4T), se producen varios cambios en el proceso de recopilación de datos.
keywords: Recommendations
seo-description: Cuando se habilita Analytics como fuente de informes para Target (A4T), se producen varios cambios en el proceso de recopilación de datos.
seo-title: Antes de la implementación  Adobe Analytics como fuente de informes para Adobe Target (A4T)
solution: Target
title: Antes de la implementación
topic: Premium
uuid: fe603a4b-bd61-49f4-b1b7-a0329aa905f5
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Antes de la implementación{#before-you-implement}

Cuando se habilita Analytics como fuente de informes para Target (A4T), se producen varios cambios en el proceso de recopilación de datos.

Antes de decidir si usará esta integración, lea el contenido de estas secciones y tenga en cuenta el impacto en sus procesos de creación de informes:

## Requisitos de implementación {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Antes de empezar a usar A4T, debe solicitar el aprovisionamiento de su cuenta para la integración. Rellene [este formulario](https://www.adobe.com/go/audiences) para solicitar el aprovisionamiento.

Esta integración con A4T requiere que implemente las siguientes versiones de las bibliotecas (o versiones más recientes), en función de si quiere redireccionar ofertas con A4T o no:

### Requisitos necesarios si *no* se utilizan ofertas de redireccionamiento con A4T

Esta integración requiere que implemente las siguientes versiones de la biblioteca (o versiones más recientes) si no planea utilizar ofertas de redireccionamiento con A4T. El orden de la lista es el orden de las operaciones.

* Servicio ID de visitante de Experience Cloud: visitorAPI.js versión 1.8.0
* Adobe Target (según su implementación): at.js versión 0.9.1 o mbox.js versión 61
* Adobe Analytics: appMeasurement.js versión 1.7.0

### Requisitos necesarios si se utilizan ofertas de redireccionamiento con A4T

Para utilizar ofertas de redireccionamiento con A4T, debe implementar las siguientes versiones de la biblioteca (o más recientes). El orden de la lista es el orden de las operaciones.

* Servicio ID de visitante de Experience Cloud: visitorAPI.js versión 2.3.0
* Adobe Target: versión 1.6.2 de at.js

   **Nota:** La biblioteca mbox.js no admite ofertas de redireccionamiento con A4T. La implementación debe utilizar at.js.

* Adobe Analytics: appMeasurement.js versión 2.1

Las instrucciones de descarga e implementación aparecen en [Implementación de Adobe para Target](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_a4timplementation.html).

## Cosas que hay que saber antes de implementar {#section_50D49CC52E11414089C89FB67F9B88F5}

* Esta integración se habilita en las nuevas actividades al seleccionar Analytics como fuente de informes. Después de completar los cambios de implementación descritos en este documento, las actividades existentes no se verán afectadas.
* El proceso de configurar Analytics como fuente de informes para Target conlleva realizar varios pasos de implementación, seguidos de un paso de aprovisionamiento. Le recomendamos que lea todo el proceso que se describe a continuación antes de comenzar la implementación. Cuanto termine de realizar estos pasos, estará listo para usar Analytics como fuente de informes en cuanto esté activado. El proceso de aprovisionamiento puede tardar hasta cinco días hábiles.
* El servicio ID de visitante crea un ID de visitante compartido en todo Experience Cloud. Aunque no sustituye al ID de mboxPC de Target ni al UUID de Audience Manager, sí sustituye la forma en la que Analytics identifica a los visitantes nuevos. Si se configura bien, los visitantes de Analytics que vuelven también se deben identificar con sus ID anteriores de Analytics para evitar que haya usuarios sin identificar. De modo similar, como mboxPCid de Target no sufre cambios, no se pierden datos de perfil de ningún visitante de Target al actualizar al servicio de ID de visitante.
* El servicio ID de visitante debe ejecutarse antes del código de página de Analytics y de Target. Asegúrese de que `VisitorAPI.js` aparece antes de las etiquetas del resto de los productos de Experience Cloud.

## Latencia {#section_9489BE6FD21641A4844E591711E3F813}

Después de activar esta integración, se apreciará una latencia adicional de 5 a 10 minutos en Adobe Analytics. Este aumento de la latencia permite almacenar los datos de Analytics y Target en la misma visita, lo que le permite desplegar las pruebas por página y por sección de sitio.

Este aumento se ve reflejado en todos los servicios y herramientas de Adobe Analytics, incluido el flujo en directo y los informes en tiempo real, y se aplica a estos escenarios:

* Para el flujo en directo, los informes en tiempo real, las solicitudes de la API y todos los datos actuales para las variables de tráfico, solo se retrasan las visitas con un ID de datos suplementario.
* Para los datos actuales en las métricas de conversión, los datos finalizados y las fuentes de datos, todas las visitas se retrasan de 5 a 7 minutos más.

Tenga en cuenta que el aumento de la latencia empieza después de implementar el servicio de ID de visitante de Experience Cloud, incluso aunque no haya implementado correctamente esta integración.

## ID suplementario  {#section_2C1F745A2B7D41FE9E30915539226E3A}

Todas las llamadas de Target que se utilicen en una actividad de A4T para ofrecer contenido o registrar la métrica de objetivos deben tener una coincidencia en Analytics que comparta el mismo ID complementario para que A4T funcione correctamente.

Las visitas que contienen datos de Analytics y Target contienen un ID de datos suplementario. Puede consultar este ID en [Adobe Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=debugger) como el parámetro `sdid`. Por ejemplo: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Este ID se genera cada vez que se cumplen los siguientes criterios:

* Se ha implementado el servicio de ID de visitante.
* Se ha implementado una versión de [!DNL mbox.js] que admite esta integración.

Cuando solucione problemas, asegúrese de que el ID suplementario esté presente en las visitas de Analytics.

## Client-side Analytics logging {#client-side}

By default, when at.js, the [!DNL Experience Cloud Visitor ID Service], and appMeasurement.js are on the page, [!DNL Adobe Analytics] and [!DNL Target] correctly stitch events for reporting and analytics purposes in the backend as long as the correct supplemental ID is included from the page, as mentioned above. No tendrá que gestionar y realizar operaciones adicionales para A 4 T para funcionar correctamente.

However, there are cases when you might want to have more control on when and how to send analytics data related to [!DNL Target] to [!DNL Analytics] for reporting purposes. You might have an in-house analytics tool that you leverage for internal purposes but also want to send the analytics data to [!DNL Analytics] via your in-house analytics product so that other members of your organization can continue to utilize [!DNL Analytics] as a visual reporting source. See [Step 7: Reference at.js or mbox.js on all site pages](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) in *Analytics for Target Implementation* for more information.
